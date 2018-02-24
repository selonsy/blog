---
title: Path MTU Discovery 问题
time: 2018.02.24 12:23:52
layout: post
tags:
- Network
- Q & S
excerpt: 手机PC处于同一网络并访问同一网络地址，手机端正常显示，PC端却超时失败，为什么？
---
## 问题描述：
手机PC处于同一网络并访问同一网络地址，手机端正常显示，PC端超时失败，为什么？

## 原因排查：
Windows 8 plus开始缺省打开 **path MTU discovery** ，所有的 IP 包都 DF=1，一旦遇到 intermediate router MTU 变小， IP 包被丢弃，而 ICMP 一旦无法成功返回，就进入流量黑洞模式。

>如果禁用了 **PMTU** 发现，则 TCP 将仅发送 MTU 大小为 576 且未设置 Don't Fragment 位的数据包。这样路由器就能够将数据包分段并跨网络发送数据包。此方法影响发送到所有目标的数据包。通常，在数据包大小为 576 时，性能处于一个可接受的级别，但是，如果启用了 PMTU 发现且路径支持的 MTU 大小大于 576，则性能将会更低。 

## 解决方案：
禁用 PMTU 发现--*Disable path MTU discovery*.

## 操作方法：
1. 单击“开始”，单击“运行”，键入 regedit，然后单击“确定”。
2. 在注册表中找到下面的项：   
`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`
3. 在“编辑”菜单上，指向“新建”，然后单击“DWORD 值”。
4. 键入 EnablePMTUDiscovery，然后按 Enter。
5. 在“编辑”菜单上，单击“修改”。
6. 在“数值数据”框中，键入 0，然后单击“确定”。
7. 退出注册表编辑器，然后重新启动计算机。

>注：如果已经有了该项，可直接修改，具体如下图所示。  

## 操作图示：
<img class="full-img" src="{{ site.loadingImg }}" data-src="{{ site.url }}/img/post/2018-02-24-path-mtu-discovery.png" />



