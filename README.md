### WebService技术研究

<pre>
Webservice:

      以HTTP协议为基础，使用xml进行客户端/服务器通信的框架。

      关键点：
            1）服务端提供的功能，通过xml描述。
            2）步骤1中描述的功能，嵌入到HTTP协议中，使得能够通过HTTP协议进行通信。（SOAP）
</pre>

![](https://i.imgur.com/TkOhc3G.png)

<pre>
Webservice采用这两个技术的目的：
      1）跨平台，支持HTTP协议的主机和服务器，都能建立通信连接，并且大部分的主机和服务器都
                支持HTTP,不同目标主机之间的通信，需要通过防火墙，打开某个端口，HTTP协议
                的优势在于，防火墙一般不会封掉80端口，这样就可以方便，安全的通信。
      2）跨语言, 任何语言，都支持xml文本解析，这个目的是为了实现不同语言之间的通信，通信
                的内容，是被xml限制的，因此这样进行通信，能跨域语言障碍，即Java开发的
                服务端，客户端可以用C访问，可以用Java，VB等访问，反之亦然。
</pre>

![](https://i.imgur.com/ZdhdSnP.png)

<pre>
基本步骤：
      1）Provider节点提供好服务后，首先注册到节点Registry
      2) Requester节点到Registry节点查询信息，找到需要的Provider及其提供的Service
      3）Requester使用Provider提供的服务。
</pre>

![](https://i.imgur.com/BlkTb0y.png)

<pre>
WebService 的整个原理流程:

		1 Client 有需要，想调用一个服务，但不知道哪里去调用 . 但知道 UDDI Registry 上可以查到。
		2.果然 UDDI 记录了某个一个叫做 Web Server A 的服务器能提供这样的服务。
		
		3.于是 Client 去 Web Server A, 询问确切的调用方法。
		
		4.Web Server A 看到 Client 提出的“确切方法查询”之后， 立即返回给它一个 WSDL 描述的 xml 文档这里记录他能提供的各类方法接口 .
		
		5.Client 了解到这些之后，将这些 xml 的接口方法，封装成为 HTTP 请求 , 发给 Web Server A. 这些封装方式采用的是标准的 SOAP 方式 , 实质是满足 HTTP 协议的一些 SOAP 的报文消息。
		
		6.Web Server A 回应的也是 HTTP 协议的 SOAP 包 . 这样双方的请求 - 响应完全畅通
</pre>

![](https://i.imgur.com/JJC2B0C.png)

![](https://i.imgur.com/3UlDKe9.png)

![](https://i.imgur.com/PfooviC.png)

![](https://i.imgur.com/ZovyxYa.png)

![](https://i.imgur.com/rIMhVxv.png)

打开命令行窗口，切换到src目录，执行
"wsimport -keep http://192.168.1.100:8888/WebService?wsdl"生成客户端代码

![](https://i.imgur.com/ceYoz89.png)