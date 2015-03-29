# 搜索卷

以下表格描述了卷可用的搜索选项。

**卷可用的搜索选项**

|属性（资源本身的或者与其关联的其它资源类型的）|类型|说明（参考）|
|----------------------------------------------|----|------------|
|Volume.*集群属性*|根据属性类型而不同|卷所在的集群的属性|
|Cluster|字符串|卷所在的集群的名称|
|name|字符串|卷的名称|
|type|字符串|为 distribute、replicate、distributed\_replicate、stripe 或者 distributed\_stripe 中之一|
|transport\_type|字符串|为 tcp 或者 rdma|
|replica\_count|整形数|replica 数|
|stripe\_count|整形数|stripe 数|
|status|字符串|卷的状态。为 Up 或者 Down|
|sortby|列表|根据资源属性对返回结果进行排序|
|page|整形数|每页显示的搜索结果数目|

*示例*.
*Volumes: transport\_type = rdma AND stripe\_count \>= 2*

将返回一个卷列表，其中的每个卷都具有以下特点：

-   传输类型为 RDMA；并且

-   stripe 数大于等于 2
