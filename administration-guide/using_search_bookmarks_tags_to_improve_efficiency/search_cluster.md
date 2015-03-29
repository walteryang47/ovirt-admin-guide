# 搜索集群

以下表格描述了集群可用的搜索选项。

**集群可用的搜索选项**

|属性（资源本身的或者与其关联的其它资源类型的）|类型|说明（参考）|
|----------------------------------------------|----|------------|
|Datacenter.*数据中心属性*|根据属性类型而不同|集群所在的数据中心的属性|
|Datacenter|字符串|集群所在的数据中心|
|name|字符串|在网络上用以识别该集群的唯一名字|
|description|字符串|集群的描述|
|initialized|字符串|表示集群的状态的值，为 True 或者 False|
|sortby|列表|根据资源属性对返回结果进行排序|
|page|整形数|每页显示的搜索结果数目|

*示例*.
*Clusters: initialized = True OR name = Default*

将返回一个集群列表，其中的每个集群都具有以下特点：

-   已初始化；或者

-   名称为 Default