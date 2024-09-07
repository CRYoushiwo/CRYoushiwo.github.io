---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/NetworkLayer/InternetProtocol/index.html
title: InternetProtocol
---

# IP协议

## IPv4


<div style="display: flex; justify-content: center;">
    <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071430646.png" style="max-width: 80%; height: auto;">
</div><br>

- 版本
    - IP协议版本（4b）
        - IPv4: 0100
        - IPv6: 0110
- 首部长度（4b）
    - 最大数值是 15 个**单位**（每个单位表示4B）
    - 至少长度要大于5（5*4 = 20B），否则数据有误（首部的最小长度为20B）
- 服务类型（8b）
    
    
    |  | D | T | R | C |
    | --- | --- | --- | --- | --- |
    | 说明 | 最小时延 | 最大吞吐量 | 最高可靠性 | 最小成本 |
    | 举例 | 交互式活动 | 发送数据块 | 管理活动 | 后台活动 |
- 总长度（16b）
    - 最大数值是 65535 个**单位**（每个单位表示1B）
- **标识-标志-片偏移**
    
    <div style="display: flex; justify-content: center;">
        <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071430345.png" style="max-width: 80%; height: auto;">
    </div><br>
    
    - 标识（16b）：计数器，用来产生数据报的标识
    - 标志（3b）：计数器，用于数据报的分片
        - 没有分片的分组可以认为是最后一个分段
    - 片偏移（13b）：数据载荷偏移量，以**8字节为单位**
    - Example 1
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071431984.png" style="max-width: 80%; height: auto;">
        </div><br>
        
    - Example 2
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071431892.png" style="max-width: 80%; height: auto;">
        </div><br>
        
        - 原始总数据长度 4020-20 = 4000
        - 第一个分片：0-1399(1400)--**0**
        - 第二个分片：1400-2799(2800)--**175**
            - 再分片的第一个分片：1400-2199(2200)--**175**
            - 再分片的第二个分片：2200-2799(2800)--**275**
        - 第三个分片：2800-3999(4000)--**350**
    - Example 3
        - 到达的一个分组的偏移值是 100，而 HLEN字段值为 5，总长度字段的值是 100。试问第一个字节和最后字节的编号是多少？
        - 第一个字节的编号是 100 × 8 = 800.
            - 总长度是 100字节，头部长度是 20 个字段 (5 × 4), 这就是说这个数据报有 80个字节
            - 如果第一个字节的编号800，则最后字节的编号是879
- 生存时间（8b）
    - 以“跳数”为单位，路由器收到待转发的IPv4数据报时，该字段的值减1
- 协议（8b）
    - 此数据报携带的数据使用何种协议以便目的主机的 IP 层将数据部分上交给哪个处理过程
- 首部检验和
    - 反码解决数据段的进位和借位问题
    
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071431338.png" style="max-width: 80%; height: auto;">
        </div><br>
    
    - Example 1
        - 数字21的二进制表示10101（5位）。可以把最左边的位加到最右边的4位，
        即：0101+1=0110或者 6。
    - Example 2
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071431365.png" style="max-width: 80%; height: auto;">
        </div><br>
        
    - Example 3
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071431583.png" style="max-width: 80%; height: auto;">
        </div><br>
        

## IPv6

## IPv4 到 IPv6的过渡

- 三个策略
    - 双协议栈
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071431103.png" style="max-width: 80%; height: auto;">
        </div><br>
        
    - 隧道策略
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071431942.png" style="max-width: 80%; height: auto;">
        </div><br>
        
    - 头部转换策略
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071432146.png" style="max-width: 80%; height: auto;">
        </div><br>