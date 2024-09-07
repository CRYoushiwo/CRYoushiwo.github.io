---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/ApplicationLayer/index.html
title: ApplicationLayer
---

# 应用层

## 域名系统

- 域名
    - 由若干个分量组成
- 域名服务器
    - 以区为单位，设置相应的权限域名服务器，用来保存该区中的所有主机的=
    - 类型
        - 根域名服务器
        - 顶级域名服务器
        - 权限域名服务器
        - 本地域名服务器
    - 域名服务器解析
        - **本地域名服务器向根域名服务器的查询**通常是采用**迭代查询**
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071406148.png" style="max-width: 80%; height: auto;">
            </div><br>
            
        - **主机向本地域名服务器的查询**一般都是采用**递归查询**
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071406443.png" style="max-width: 80%; height: auto;">
            </div><br>
            

## 文件传送协议

- FTP
    - 使用客户服务器方式
    - FTP 客户和服务器之间要建立两个并行的TCP连接
        - 控制连接
            - 用于传输FTP相关控制命令
            - 整个会话期间保持打开状态
            - 端口 21
        - 数据连接
            - 用于文件传输
            - 传输时建立，传输结束关闭
            - 端口 20
- NFS
    - 允许应用进程打开一个远地文件，在特定的位置上读写
    - 可使用户只复制一个大文件的部分，而非整个文件
- 简单文件传送协议 TFTP（端口号：69）
    - 很小且易于实现的文件传送协议
    - 使用客户服务器方式和 **UDP 数据报**，因此 TFTP 需要有自己的差错改正措施
    - 只支持文件传输而不支持交互
    - 没有一个庞大的命令集，没有列目录的功能，也不能对用户进行身份鉴别

## 远程终端协议 TELNET

<div style="display: flex; justify-content: center;">
    <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071406007.png" style="max-width: 80%; height: auto;">
</div><br>

- NVT格式
    - 网络虚拟终端的数据传输格式

## 电子邮件

<div style="display: flex; justify-content: center;">
    <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071406064.png" style="max-width: 80%; height: auto;">
</div><br>

- 简单邮件传送协议 SMTP
    - 只能传送 ASCII码
    - 全程使用 TCP连接
    - 一个邮件既可以作为客户也可以作为服务器
        - A 发送邮件 B
            - A：SMTP客户，B：SMTP服务器
        - A 接收邮件 B
            - B：SMTP客户，A：SMTP服务器
- 邮件读取协议 POP3 和 IMAP
    - 不同点
        - POP3
- 通用因特网邮件扩充 MIME
    - 将非 ASCII码 转为 7位 ASCII码

## 万维网

- 分布式超媒体系统
- 超文本是万维网的基础
- URL
    - <URL的访问方式>://<主机>:<端口>/<路径>
        - URL的访问方式
            - ftp
            - http
            - News
            - ……
- 使用高速缓存可减少 访问因特网服务器的时延