# similar_codis_impl
参考codis实现思路，使用c++实现其中的各个服务，可以作为一个学习的demo

# 一些约定
- 设定slot数为8
- 设定2台ChunkServer，并构成两个分组group1, group2。每个group单副本
- slot和group的关系：[0-3]-group1, [4-7]-group2
- 

# 组成部分
- ProxyServer  
  *1、处理请求*  
  *2、缓存配置信息*  
  *3、提供路由算法*  
- ChunkServer  
  *1、维护单机存储功能*  
  *2、维护ConfigServer与其通信的命令实现和响应，包括自定义协议解析*  
  *3、维护ProxyServer与其通信的命令实现和响应，包括自定义协议解析*  
  *4、监听固定端口，处理外部链接*
- ConfigServer  
  *1、维护slot状态信息*  
  *2、负责与ChunkServer通信*  
  *3、负责与ProxyServer通信*  
