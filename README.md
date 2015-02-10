# similar_codis_impl
参考codis实现思路，使用c++实现其中的各个服务，可以作为一个学习的demo

# 组成部分
- ProxyServer  
  *1、处理请求*  
  *2、缓存配置信息*  
- ChunkServer  
  *1、维护单机存储功能*  
  *2、维护ConfigServer与其通信的命令实现和响应，包括自定义协议解析*  
  *3、维护ProxyServer与其通信的命令实现和响应，包括自定义协议解析*  
- ConfigServer  
  *1、维护slot状态信息*  
  *2、负责与ChunkServer通信*  
  *3、负责与ProxyServer通信*  
