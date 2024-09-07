---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/DataLinkLayer/DataDetectionControl/index.html
title: DataDetectionControl
---

# 数据链路控制

- 可靠传输
- 流量控制：用来限制发送方在等到确认之前发送的数据数量
- 差错控制：控制基于自动重复请求，即重传数据

## 基本知识

- 前提知识
    - 链路与通路
    - 主机和交换机在局域网都必须实现数据链路层
    - 基本传输单位：帧
- 封装成帧
    - 网络层协议数据单元+头部和尾部
    - 帧定界符
- 透明传输
    - 面向字节
        - 使用换义字符（ESC）对数据内同帧定界符相同的字符进行转义
        - 该方法递归使用
    - 面向比特
        - 直接将数据内的帧定字符替换都替换为全0

## 停等ARQ

<div style="display: flex; justify-content: center;">
    <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071412387.png" style="max-width: 80%; height: auto;">
</div><br>

- 信道利用率
    
    <div style="display: flex; justify-content: center;">
        <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071412163.png" style="max-width: 80%; height: auto;">
    </div><br>
    

## 后退N帧ARQ

- 在后退 N 帧协议中，序列号是模$2^m$ ，其中$m$为序列号字段长度

### 发送窗口

- 通过三个变量 $S_f$、 $S_n$、 和 $S_{size}$ 来定义它的大小
- $S_{size}$ 小于 $2^m$ ，一般取 $2^m-1$
    
    <aside>
    ⚠️  $S_{size} =1$：退化为停等ARQ
    $S_{size} \ge 2^{m}$：接收方无法分辨新旧数据分组
    
    </aside>
    
<div style="display: flex; justify-content: center;">
    <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071413324.png" style="max-width: 80%; height: auto;">
</div><br>

### 接收窗口

- 用变量 $R_n$ 定义了大小为1的接收窗口
- 采用累计确认：连续收到多个按序到达且无误码的数据分组后，才针对最后一个数据分组发送确认分组

<div style="display: flex; justify-content: center;">
    <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071413602.png" style="max-width: 80%; height: auto;">
</div><br>

## 选择性重传ARQ

- 在选择重传ARQ协议中，序列号是模$2^m$ ，其中$m$为序列号字段长度
- 发送窗口$W_T$大小与接收窗口大小需满足： $W_T+W_R≤2^m$
- 接收窗口$W_R$大小需满足： $W_R≤2^{m-1}$
- 需要对帧逐一判断确认