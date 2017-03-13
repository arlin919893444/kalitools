##dnmap软件包描述

dnmap是一种在多个客户端之间分布nmap扫描的框架。它使用nmap命令读取已创建的文件，并将这些命令发送到与其连接的每个客户端。

该框架使用客户端/服务器体系结构。服务器知道做什么，客户端做它。所有逻辑和统计信息都在服务器中管理。Nmap输出存储在服务器和客户端上。

通常你会想要这个，如果你必须扫描一大组的主机，你有几个不同的互联网连接（或朋友，想帮助你）。

**来源**：http://mateslab.weebly.com/dnmap-the-distributed-nmap.html 

[dnmap首页] (http://sourceforge.net/projects/dnmap/)| [Kali dnmap Repo](http://git.kali.org/gitweb/?p=packages/dnmap.git;a=summary)

- 作者：www.mateslab.com.ar

- 许可证：GPLv3

##dnmap软件包中包含的工具

###dnmap_client - 分布式nmap框架（客户端）

```
root @ kali：〜＃dnmap_client -h 
+ ---------------------------------------- ------------------------------ + 
| dnmap客户端版本0.6 | 
| 这个程序是免费软件; 你可以重新分配它和/或修改| 
| 它根据|发布的GNU通用公共许可证的条款 
| 自由软件基金会; 许可证的版本2或| 
| （可选）任何更新的版本。| 
| | 
| 作者：Garcia Sebastian，eldraco@gmail.com | 
| www.mateslab.com.ar | 
+ ------------------------------------------------- --------------------- + 

usage：/ usr / bin / dnmap_client <options> 
选项：
  -s，--server-ip dnmap服务器的IP地址。
  -p，--server-port dnmap服务器的端口。Dnmap端口默认为46001 
  -a，--alias您的名字别名，所以我们可以给你的信任，为您的帮助。可选
  -d，--debug调试。
  -m，--max-rate强制nmaps命令最多使用此速率。有用于慢nmap下。添加--max-rate参数。
  ```
  
  ##dnmap_server - 分布式nmap框架（服务器）
  
  ```
  root @ kali：〜＃dnmap_server -h 
+ ---------------------------------------- ------------------------------ + 
| dnmap_server Version 0.6 | 
| 这个程序是免费软件; 你可以重新分配它和/或修改| 
| 它根据|发布的GNU通用公共许可证的条款 
| 自由软件基金会; 许可证的版本2或| 
| （可选）任何更新的版本。| 
| | 
| 作者：Garcia Sebastian，eldraco@gmail.com | 
| www.mateslab.com.ar | 
+ ------------------------------------------------- --------------------- + 

usage：/ usr / bin / dnmap_server <options> 
选项：
  -f，--nmap-commands Nmap命令文件
  -p， -port TCP端口，其中我们侦听连接。
  -L，--log-file日志文件。默认为/var/log/dnmap_server.conf。
  -l，--log-level日志级别。默认为info。
  -v，--verbose_level详细级别。给出介于1和5之间的数字。默认为1.级别0表示安静。
  -t，--client-timeout在将客户端标记为脱机之前，我们应该等待多少时间。我们仍然记住它的价值观，以防万一它回来。
  -s，--sort对静态值排序的字段。您可以选择：
  用于TLS连接的别名，#Commands，UpTime，RunCmdXMin，AvrCmdXMin，Status -P，--pem文件pem文件。默认情况下，我们使用当前目录中的服务器提供的server.pem文件。

dnmap_server使用'<nmap-commands-file-name> .dnmaptrace'文件知道它必须继续读取nmap命令文件。如果你想重新开始，
只需删除'<nmap-commands-file-name> .dnmaptrace'文件
```

##dnmap_server用法示例

创建一个包含客户端将运行的nmap命令的文本文件。传递文件**dnmap.txt（-f）**以启动服务器：

```
root @ kali：〜＃echo“nmap -F 192.168.1.0/24 -v -n -oA sub1”>> dnmap.txt 
root @ kali：〜＃echo“nmap -F 192.168.0.0/24 -v -n- oA sub0“>> dnmap.txt 
root @ kali：〜＃dnmap_server -f dnmap.txt 
+ ----------------------------- ----------------------------------------- + 
| dnmap_server Version 0.6 | 
| 这个程序是免费软件; 你可以重新分配它和/或修改| 
| 它根据|发布的GNU通用公共许可证的条款 
| 自由软件基金会; 许可证的版本2或| 
| （可选）任何更新的版本。| 
| | 
| 作者：Garcia Sebastian，eldraco@gmail.com | 
| www.mateslab.com.ar | 
+ ------------------------------------------------- --------------------- + 

= | MET：0：00：00.000544 | 在线客户数：0 | =
```

##dnmap_client用法示例

使用别名dnmap-client1（-a）连接到服务器**192.168.1.15（-s ）：**

```
root @ kali：〜＃dnmap_client -s 192.168.1.15 -a dnmap-client1 
+ -------------------------------- -------------------------------------- + 
| dnmap客户端版本0.6 | 
| 这个程序是免费软件; 你可以重新分配它和/或修改| 
| 它根据|发布的GNU通用公共许可证的条款 
| 自由软件基金会; 许可证的版本2或| 
| （可选）任何更新的版本。| 
| | 
| 作者：Garcia Sebastian，eldraco@gmail.com | 
| www.mateslab.com.ar | 
+ ------------------------------------------------- --------------------- + 

Client Started ... 
存储在'nmap_output'目录中的Nmap输出文件... 
正在启动连接... 
客户端已成功连接... 
正在等待更多命令.... 
        命令执行：nmap -F 192.168.1.0/24 -v -n -oA sub1
```
