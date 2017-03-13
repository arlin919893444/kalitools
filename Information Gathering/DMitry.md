DMitry

DMitry包描述

DMitry（Deepmagic信息收集工具）是以C编码的UNIX /（GNU）Linux命令行应用程序.DMitry能够收集关于主机的尽可能多的信息。基本功能能够收集可能的子域，电子邮件地址，正常运行时间信息，tcp端口扫描，whois查找等。

以下是当前功能的列表：

- 开源项目。
- 执行Internet号码whois查找。
- 检索可能的正常运行时间数据，系统和服务器数据。
- 在目标主机上执行SubDomain搜索。
- 在目标主机上执行电子邮件地址搜索。
- 在主机目标上执行TCP端口扫描。
- A模块化程序允许用户指定模块

**来源**：http://mor-pah.net/software/dmitry-deepmagic-information-gathering-tool/ 

[梅德首页](http://mor-pah.net/software/dmitry-deepmagic-information-gathering-tool/) | [Kali DMitry Repo](http://git.kali.org/gitweb/?p=packages/dmitry.git;a=summary)

- 作者：James Greig

- 许可证：GPLv3

##dmitry包中包含的工具

###dmitry - Deepmagic信息收集工具

```
root @ kali：〜＃
dmitry -h Deepmagic信息收集工具
“有一些深的魔法继续” 

dmitry：invalid option - 'h' 
用法：dmitry [-winsepfb] [-t 0-9] [-o％host .txt] host 
-o将输出保存到％host.txt或由-o文件指定的文件
-i对主机的IP地址
执行whois查询-w 对主机的域名执行whois查找
-n检索NetWorker在主机上的信息
-s执行搜索可能的子域名--e 
执行搜索可能的电子邮件地址
-p在主机上执行TCP端口扫描
* -f 在主机上执行TCP端口扫描，显示输出报告过滤的端口
* -b读取从扫描端口接收的横幅
* -t 0-9设置扫描TCP端口时的TTL（以秒为单位）（默认值2）
*需要传递-p标志
```

dmitry用法示例

运行**域名Whois查询（W）** ，一个**IP的whois查询（我）**，检索**Netcraft的信息（N）** ，
搜索**子域（S）** ，搜索**电子邮件地址（E）**，做一个TCP端口扫描**（P）** ，并保存输出到**example.txt（o）**
域**example.com**：

```
root @ kali：〜＃dmitry -winsepo example.txt 
example.com Deepmagic信息收集工具
“有一些深的魔法继续” 

将输出写入“example.txt” 

HostIP：93.184.216.119 
HostName：example.com 

收集Inet-whois信息93.184.216.119 
---------------------------------
```
