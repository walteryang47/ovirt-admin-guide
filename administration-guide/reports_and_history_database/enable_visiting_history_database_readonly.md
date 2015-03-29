# 允许只读访问历史数据库

**概述**

您可以创建一个只读的 PostgreSQL 用户，这个用户只能登录到 **ovirt_engine_history** 数据库中并对其进行读操作，而不能进行写操作。以下步骤必须在历史数据库所在的系统上进行操作。

**对历史数据库的只读访问**
1. 创建对历史数据库有只读权限的用户：

```
# psql -U postgres -c "CREATE ROLE [user name] WITH LOGIN ENCRYPTED PASSWORD '[password]';" -d ovirt_engine_history
```
2. 授予新用户连接到历史数据库的权限：

```
# psql -U postgres -c "GRANT CONNECT ON DATABASE ovirt_engine_history TO [user name];"
```
3. 授予新用户使用 **public** schema 的权限：

```
# psql -U postgres -c "GRANT USAGE ON SCHEMA public TO [user name];" ovirt_engine_history
```
4. 生成新用户所需要的其它权限，并将它们保存到一个文件中：

```
# psql -U postgres -c "SELECT 'GRANT SELECT ON ' || relname || ' TO [user name];' FROM pg_class JOIN pg_namespace ON pg_namespace.oid = pg_class.relnamespace WHERE nspname = 'public' AND relkind IN ('r', 'v');" --pset=tuples_only=on  ovirt_engine_history > grant.sql
```
5. 使用您在上一步创建的文件来为新用户添加权限：

```
# psql -U postgres -f grant.sql ovirt_engine_history
```
6. 删除您为新用户授予权限所使用的文件：

```
# rm grant.sql
```

**结果**

您现在可以使用下面的命令以新创建的用户的身份访问 **ovirt_engine_history** 数据库：

```# psql -U [user name] ovirt_engine_history```

对 **ovirt_engine_history** 数据库的表和视图的 **SELECT** 命令会成功进行，而修改的命令会失败。
