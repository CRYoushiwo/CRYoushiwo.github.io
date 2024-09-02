---
layout: page
permalink: /CourseRecording/2023/OperatingSystem/Chapter4/index.html
title: OperatingSystemChapter4
---

# 文件管理

## 文件结构及文件存取方式

- 文件的逻辑结构
    - 有结构记录式文件
    - 无结构流式文件
- 存储介质
    - 磁带
    - 磁盘
    - 光盘
- 文件的物理结构
    - 连续结构（顺序结构）
    - 链接结构（串联结构）
    - 索引结构
        - $I$节点
        - `UNIX`三级索引结构
- 文件的存取方式
    - 顺序存储
    - 随机存储
        - 直接存取法
        - 按键存取法
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/OperatingSystem/Chapter4/Untitled.png" class="blog-image" >
    

## 文件目录

- 目的：实现按名存取
- 文件控制块（FCB）
    - 基本信息类
    - 存取控制信息类
    - 使用信息类
- 目录结构
    - 一级目录结构
    - 二级目录结构
    - 多级目录结构
    - 改进的多级目录结构（无环图目录结构）
- UNIX目录结构
    - FCB = 文件名 + 索引节点（$I$节点，文件说明）
    - 目录 = 文件名+索引节点号
- 文件目录检索
    - 线性检索法
    - Hash方法
- 记录的成组与分解
    - 成组：将若干个逻辑记录合成一组存放在一个物理块的过程
    - 分解：从一组逻辑记录中把一个逻辑记录分离出来的过程
    - 缺点：需要软件增加操作，要有能容纳最大块长的I/O缓冲区
- 文件空间的管理和分配
    - 连续分配
    - 链接分配
        - 隐式链接分配
        - 显式链接分配【FAT，文件分配表（在内存中）】
    - 索引分配
        - 进程打开文件表，系统打开文件表【磁盘索引节点→内存索引节点】
        - 单级索引
        - 多级索引
        - 混合索引
- 外存空间管理
    - 磁盘分配表（在外存中）
    - 空闲表法【动态分区分配】
    - 位示图
        
        $（字号，位号）\rightleftharpoons 盘块号$
        
    - 空闲链表法
        - 空间盘块链
        - 空间盘区链
    - 成组链接法【UNIX, 100个空闲块一组】

## 操作系统的使用

- 文件操作
    - `create()`,`link()`,`unlink()`,`open()`,`close()`,`read()`,`write()`,`lseek()`
    - *O_RDONLY, O_WRONLY, O_RDWR*
    - In `lseek()`: whence(0,1,2)
- 文件共享
    - 基于索引节点【指针是否共享（静态），进程是否并发（动态）】
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/OperatingSystem/Chapter4/Untitled%201.png" class="blog-image" >
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/OperatingSystem/Chapter4/Untitled%202.png" class="blog-image" >
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/OperatingSystem/Chapter4/Untitled%203.png" class="blog-image" >
    
    - 利用符号链接共享文件

## 文件共享

- 基于索引节点的共享方式（硬链接）
    - 静态共享（不随进程产生与消亡）
        - `link(oldnamep, newnamep);`
    - 动态共享（随进程产生与消亡）
        - `open()`
- 利用符号链接共享文件

## 文件系统的可靠性与安全性

略

## 磁盘

- 访问时间
    - 寻道时间
        - $T_s = s + m*n$
    - 延迟时间
        - $T_R = \frac{1}{2}\frac{1}{r}$
        - 减少方法<交替编号，错位命名>
    - 传输时间
        - $T_t = \frac{b}{N}\frac{1}{r}$
- 调度算法
    
    <aside>
    ⚠️ 若题目没说明，SCAN就是LOOK，C-SCAN就是C-LOOK
    
    </aside>
    
    - 先来先服务（FCFS）
    - 最短寻找时间优先算法（SSTF）
    - 扫描算法，电梯算法（SACN）
    - 循环扫描（C-SCAN）