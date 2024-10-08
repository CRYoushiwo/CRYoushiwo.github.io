---
layout: page
permalink: /CourseRecording/2023/ComputerOrganization/Chapter5/index.html
title: ComputerOrganizationChapter5
---

# 指令系统

## 重点题型

- 操作码编码方案（特别是扩展操作码编码）5.9
- 结合地址码的情况，分析扩展操作码的可行性和指令数量的变化情况 5.10，5.12
- 数据存储<大端，小端> 5.14 **注意可能会结合后面寻址结果**
- 依据基本寻址方式，分析新的寻址方式（主要是寻址方式的名称，最后的寻址结果）
- 设计指令格式
- 根据指令功能，设计某一具体指令

## 术语

- 指令：控制计算机硬件完成指定基本操作的命令
- 指令系统：指令集合
- 指令字长：指令的位数
- 操作码：指定指令要完成的功能
- 地址码（操作数）：提供该指令的操作对象
- 寻址方式：指令获取操作数的方式
- CISC：复杂指令系统
- RISC：精简指令系统

## 指令系统概述

- 指令系统是从程序设计者看到的机器的主要属性，是软、硬件的主要界面
- 指令系统的设计主要包括**指令功能**和**指令格式**的设计。

## 指令系统结构层定义

- 存储模式
    - 数据存储顺序
        - 大端存储【字符打印】
        - 小端存储【算术运算】
        - 例题
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072355999.png" style="max-width: 80%; height: auto;">
        </div><br>
        
    - 边界对齐
        - 按字节编址， 边界对齐
    - 堆栈
        - 管理堆栈<堆栈指针，堆栈基址，堆栈界限>
        
        <aside>
        ⚠️ 堆栈界限 > 堆栈基址 VS 堆栈界限 < 堆栈基址
        
        </aside>
        
    - 冯·诺依曼结构和哈佛结构
        - 优缺点分析【主存空间利用，数据操作对指令的破坏性，】
    - 加载/存储体系结构
        - Load，Store指令
- 寄存器组织
    - 软件设计者唯一能操作的CPU内部资源
    
    <aside>
    📢 标志寄存器常作为条件跳转指令的跳转条件
    
    </aside>
    
- 数据类型
- I/O模式
    - 统一编址
    - 独立编址
- 指令类型
    - 程序控制类
        - 转移指令<无条件转移指令, 条件转移指令>
        - 循环控制指令
        - 过程调用和返回指令
        - 程序自中断指令

## 指令设计

- 指令格式<操作码，操作数>
- 指令长度
    - $指令长度 = 操作码+地址码（注意按字节向上取整）$
- 地址码设计
    
    
   | 源操作数|目的操作数|下条指令地址|
    
    <div style="display: flex; justify-content: center;">
        <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072355477.png" style="max-width: 80%; height: auto;">
    </div><br>

    <div style="display: flex; justify-content: center;">
        <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072355826.png" style="max-width: 80%; height: auto;">
    </div><br>
    
- 操作码设计
    - 定长操作码
    - 变长操作码
        - 霍夫曼编码
        - 扩展操作码（为充分利用操指令的二进制位）
            
            <aside>
            ⚠️ 拓展操作码的设计
            
            </aside>
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072355365.png" style="max-width: 80%; height: auto;">
            </div><br>
            

## 寻址方式

- 基本寻址方式

📢 寻址方式在指令中的体现：**由操作码决定（隐含寻址），操作数中设置寻址方式字段（显式寻址）**


| 隐含寻址|解释|
|-
|立即寻址|  |
|寄存器寻址|寄存器编号|
|直接寻址|操作数地址|
|间接寻址|操作数地址的地址→操作数地址|
|寄存器间接寻址|寄存器编号→操作数地址|
|相对寻址|地址偏移 (+PC)|
|基址寻址|基址寄存器寻址位+地址偏移|
|变址寻址|变址寄存器寻址位+地址偏移|
|堆栈寻址|  |


- **RISC-V 和 x86 寻址方式**

<aside>
⚠️ 额外内容

</aside>

| RISC-V|x86|
|-
|立即寻址|立即寻址|
|寄存器寻址|寄存器寻址|
|基址寻址|主存储器寻址|
|相对寻址| |

- 例题

    <div style="display: flex; justify-content: center;">
        <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072355234.png" style="max-width: 80%; height: auto;">
    </div><br>

## 指令系统结构的发展

- CISC 复杂指令系统计算机
    - 指令系统复杂庞大
    - 指令长度不固定，指令格式种类多，寻址方式种类多
    - 可以访存的指令不受限制
    - 控制器大多数采用微程序控制
- RISC 精简指令系统计算机
    - 指令系统简单
    - 采用Load/Store结构
    - 重视提高流水线的执行效率
    - 强调优化编译技术的作用

## 指令系统实例

<aside>
⚠️ 新增，考试重点

</aside>

- RISC-V 指令系统
- Intel CPU 指令系统
    - Intel 64  和 IA-32
    - IA-32e
    - Intel AVX
- MIPS 指令系统