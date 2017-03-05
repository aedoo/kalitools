# **lbd软件包描述** #
lbd（负载平衡检测器）检测给定的域是否使用DNS和/或HTTP负载平衡（通过服务器：和日期：头和服务器答案之间的差异）。

资料来源：[http://ge.mine.nu/code/lbd](http://ge.mine.nu/code/lbd)

[lbd首页](http://ge.mine.nu/code/lbd)| [Kali lbd Repo](http://git.kali.org/gitweb/?p=packages/lbd.git;a=summary)


- 作者：Stefan Behte

- 许可证：GPLv2

## lbd中包含的工具 ##

###lbd - 负载平衡器检测器

    root@kali:~# lbd 
    
    lbd - load balancing detector 0.4 - Checks if a given domain uses load-balancing.
    Written by Stefan Behte (http://ge.mine.nu)
    Proof-of-concept! Might give false positives.
    usage: /usr/bin/lbd domain [port] {https}

## lbd使用示例 ##

测试目标网域（***example.com***）是否使用负载平衡器：
    root@kali:~# lbd example.com
    
    lbd - load balancing detector 0.4 - Checks if a given domain uses load-balancing.
    Written by Stefan Behte (http://ge.mine.nu)
    Proof-of-concept! Might give false positives.
    
    Checking for DNS-Loadbalancing: NOT FOUND
    Checking for HTTP-Loadbalancing [Server]: 
     FOUND
    
    Checking for HTTP-Loadbalancing [Date]: 13:40:17, 13:40:18, 13:40:18, 13:40:19, 13:40:19, 13:40:20, 13:40:20, 13:40:21, 13:40:21, 13:40:22, 13:40:22, 13:40:23, 13:40:23, 13:40:24, 13:40:24, 13:40:25, 13:40:25, 13:40:26, 13:40:27, 13:40:28, 13:40:29, 13:40:30, 13:40:32, 13:40:34, 13:40:34, 13:40:35, 13:40:36, 13:40:36, 13:40:37, 13:40:38, 13:40:38, 13:40:39, 13:40:39, 13:40:40, 13:40:40, 13:40:41, 13:40:41, 13:40:42, 13:40:42, 13:40:43, 13:40:43, 13:40:45, 13:40:46, 13:40:46, 13:40:47, 13:40:47, 13:40:48, 13:40:50, 13:40:50, 13:40:53, NOT FOUND
    
    Checking for HTTP-Loadbalancing [Diff]: FOUND
    < Expires: Sun, 12 Mar 2017 13:40:54 GMT
    > Expires: Sun, 12 Mar 2017 13:40:55 GMT
    
    example.com does Load-balancing. Found via Methods: HTTP[Server] HTTP[Diff]


资料来源：[http://tools.kali.org/information-gathering/lbd](http://tools.kali.org/information-gathering/lbd)