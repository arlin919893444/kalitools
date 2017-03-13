##copy-router-config包描述

从运行SNMP的思科设备复制配置文件。

[copy-router-config首页](http://www.offensive-security.com/) | [Kali copy-router-config Repo](http://git.kali.org/gitweb/?p=packages/copy-router-config.git;a=summary)

- 作者：muts

- 许可证：GPLv2

##copy-router-config包中包含的工具

###copy-router-config.pl - 通过SNMP复制Cisco配置

```
root @ kali：〜＃copy-router-config.pl 

##################################### #################＃
复制Cisco路由器配置 - 使用SNMP 
＃由muts入侵 - muts@offensive-security.com 
############ ########################################## 

用法：./copy-copy -config.pl <router-ip> <tftp-serverip> <community> 

确保TFTP服务器设置，最好从/ tmp运行！
```

[/ toggle] [toggle title =“merge-router-config.pl - 通过SNMP合并Cisco配置”variation =“deepblue”]

```
root @ kali：〜＃merge-router-config.pl 

##################################### ################## 
合并思科路由器配置 - 使用SNMP 
＃由muts入侵 - muts@offensive-security.com 
############ ########################################## 

用法：./merge-copy -config.pl <router-ip> <tftp-serverip> <community> 

确保TFTP服务器设置，最好从/ tmp运行！
```

##copy-router-config用法示例

将配置从路由器（**192.168.1.1**）复制到TFTP服务器（**192.168.1.15**），使用团体字符串（**私有**）进行认证：

```
root @ kali：〜＃copy-router-config.pl 192.168.1.1 192.168.1.15 private
```

##merge-router-config用法示例

使用社区字符串（**私人**）将配置与路由器（**192.168.1.1**）合并，从TFTP服务器（**192.168.1.15**）复制：

```
root @ kali：〜＃merge-router-config.pl 192.168.1.1 192.168.1.15 private
```
