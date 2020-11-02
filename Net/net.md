#NAT
##介绍
NAT是network address translation的缩写，网络地址转换的缩写。
因为IP地址有限，所以需要多人共用一个公网IP来访问互联网。当需要访问互联网时，网络边界设备（路由器，防火墙等）将各个主机的私网IP地址，转成公网IP地址。
即，将数据包中的IP地址替换为其他IP地址的功能。
##实现方式
###静态NAT
一个公网IP对应一个私网IP，一对一转换。
###动态NAT
在路由器上配置一个公网IP池，当私有IP要进行外部通信时，从池中选择一个公网IP，并将他们的关系绑定到NAT表中。通信结束后，这个公网IP才会被释放，供其他私有IP使用。

###NAPT 
端口地址复用技术。是最常用的，提供一对多的方式。对外只有一个公网IP地址，内部通过端口来区分不同的私网IP主机数据。

##NAT如何区分不同私网的host呢？
对于TCP/UDP使用
私网host + port <---> 公网host + port 

对于ICMP使用
私网host + sessionID <----> 公网host + sessionID

对于其他协议，NAT使用的也是类似的转换规则，选择将host能轻易区分出来的字段作为key值，动态创建映射表项，做双向地址+key的转换。



#TCP
链路层：  
以太网：采用CSMA/CD的媒体接入方法。速率为10Mb/s，mac地址为48bit  
IEEE802：


封装格式：  
802.3:  
| 目的地址 6 ｜ 源地址 6 | 长度 2 | DSAP  1 | SSAP 1 | cntl 1 | org code 3 | 类型 2 ｜ 数据 38-1492 ｜ CRC 4 ｜  

以太网：  
| 目的地址 6 | 源地址 6 | 类型 2 | 数据 46-1500| CRC 4|  

IP协议：  
类型     IP数据报  
0800 

ARP协议：  
｜类型 ｜ ARP请求/应答 ｜ PAD ｜  
｜0806 ｜    26      ｜ 18

以太网头部： 目的地址  源地址 类型  
类型字段中，放协议，如上面的IP协议
以太网要求数据部分最少要求46字节，不足46字节的要用PAD补齐，超出1500字节的，要分页。  

应用层 FTP  21
传输层 TCP UDP
网络层 IP ICMP
数据层 


#TCP UDP区别

#TCP keep-alive机制

#HTTP1 2 3区别

#HTTPS

#三次握手

#四次挥手


#TCP滑动窗口，ACK机制

#tcp报文结构


#HTTP重定向机制

#TCP粘包


#Session，Cookie区别


#网络协议栈


#HTTPS工作过程


#HTTP请求报文格式



#一次URL发生了什么


#close-wait作用


#对称加密和非对称加密


#osi七层模型


#tcp能建立多少链接


#post get 区别


#DNS协议解析过程




