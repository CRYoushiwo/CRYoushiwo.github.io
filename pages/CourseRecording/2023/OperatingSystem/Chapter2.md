---
layout: page
permalink: /CourseRecording/2023/OperatingSystem/Chapter2/index.html
title: OperatingSystemChapter2
---

# 进程管理

## 进程与线程

- 概念
    - 进程
    - 进程实体
    - 进程特征（5）
    - 进程状态
- 进程状态的转换
- 进程控制原语（5）
- 进程通信
    - 一低级，三高级
- 线程
    - 进程与线程的比较【组成，通信，地址空间，地位】
    - 用户级线程与内核级线程【功能实现支持，多处理器的利用，线程切换的状态变化】
    - 多线程模型【用户线程和核心线程的数量关系】

## 处理机调度

- 概念
    - 处理机调度【多道程序系统】
    - 调度层次（3）
    - 调度评价指标【运行时间，等待时间，周转时间】
        - 周转时间：作业完成时间-作业提交时间
        - 等待时间 = 周转时间 - 运行时间
    - 调度程序的组成
    - 进程切换的时机【不能马上切换（3），应当切换】
- 典型调度算法
    - 平均周转时间，平均周转系数
    - 适用于早期批处理系统
        
        <aside>
        ➡️ 各自特点【长/短作业，（非）抢占式，饥饿】
        
        </aside>
        
        - 先来先服务
            - 考虑等待时间
        - 短作业/进程优先
            - 考虑响应时间
        - 高响应比优先
            - $$响应比 = 优先权 = \frac{作业响应时间}{作业运行时间}$$
    - 适用于交互式操作系统
        
        <aside>
        ➡️ 各自特点【长/短作业，（非）抢占式，饥饿】
        
        </aside>
        
        - 优先级
        - 时间片轮转
        - 多级队列
- 同步与互斥
    - 概念
        - 临界资源的组成
        - 同步
        - 互斥
        - 同步机制准则（4）
    - 实现同步互斥方法
        - 软件实现
            - 单标志法
            - 双标志先检查法
            - 双标志后检查法
            - 皮特森法
        - 硬件实现（元方法）
            - 中断屏蔽法
            - 硬件指令法
    - 互斥锁
        - 
    - 信号量
        - 同步问题，互斥问题
        - 前驱与后继
    - 管程
        - 对共享资源的操作封装起来

## 死锁

- 死锁概念
    
    多道程序系统中，当某个进程提出资源的使用请求时后，系统中的一些进程处于无休止的阻塞状态，在无外力的作用下，这些进程将无法运行下去
    
- 资源
    - 永久性资源（独占资源）
        - 可剥夺式资源
        - 不可剥夺式资源
    - 临时性资源
- 必要条件（4）
    - 互斥使用
    - 非剥夺控制
    - 零散请求
    - 循环等待
- 死锁预防【破坏必要条件】
    - 破坏互斥使用：SPOOLing技术
    - 破坏非剥夺控制：仅适用于处理机和存储器资源
    - 破坏零散请求：静态分配策略（一次性分配所需所有资源）
    - 破坏循环等待：资源编号（占有资源编号小于申请资源编号才允许分配资源）
- 死锁避免【安全状态，不安全状态】
    - 银行家算法 $Max = Allocation + Need$, $Available$
- 死锁检测【死锁定理】
- 死锁解除（3）