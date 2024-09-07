---
layout: page
permalink: /CourseRecording/2023/ComputerOrganization/Chapter7/index.html
title: ComputerOrganizationChapter7
---

# 总线与输入输出系统

## 概述

- 组成计算机的三类模块： CPU、 存储器、 I/O设备
- 总线
    - 计算机系统中多个部件或设备共用的传递信息的数据通路
    - 是计算机系统的互连机构
    - 通常分为地址总线、 数据总线、 控制总线
- 输入/输出系统
    - 外部设备
        - 组成<输入/输出设备，外部存储器>
        - 分类<字符设备，块设备>
    - 输入输出接口
    - 基本输入输出技术
        - 程序查询方式
        - 中断控制方式
        - DMA(直接存储器存取)方式
        - 通道控制方式

## 总线技术

- 总线类型
    - 按连接层次分类
    - 按数据位数分类
    - 按用法分类
- 总线结构
    - 单总线结构
    - 双总线结构
    - 多总线结构
- 典型总线
    - PCI总线
    - PCI Express总线
    - USB总线

## 输入/输出接口

## 输入输出技术

- 程序查询方式
- 中断方式
    - 中断源在需要得到CPU服务时，请求CPU暂停现行工作转向为中断源服务，服务完成后，再让CPU回到原工作状态继续完成被打断的工作
    - 中断执行过程的微操作【PSW，PC】
    - 内中断（软件中断），外中断（硬件中断）的判断【中断源】
    - 处理过程【发送请求，检测请求，中断响应，断点保护，**撤销中断请求**，识别中断源，执行中断处理程序，中断返回，断点恢复】
- 直接存储器存取方式
    - DMA控制器
        - DMC与CPU总线控制权的交换（4）

<div style="display: flex; justify-content: center;">
    <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072356794.png" style="max-width: 80%; height: auto;">
</div><br>

- I/O通道方式
    - 具有特殊功能的处理器
    - 通道的类型
        - 选择通道【高速外围设备】
        - 字节多路通道【字符类低速外围设备】
        - 数组多路通道【上面两者结合】