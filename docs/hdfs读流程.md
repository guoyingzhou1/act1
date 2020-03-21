## hdfs读流程

![](../pictures/hdfs读流程.png)

1. Client通过 DistributedFileSystem 向 NameNode请求需要下载的文件；
2. NameNode返回目标文件的元数据（文件各个块儿的位置信息等等）；
3. Client将连接到最近的DataNode，开始从 DataNode 并行读取数据；
4. 当Client获得了所有必须的 block，它就会将这些 block 组合起来形成一个文件。
