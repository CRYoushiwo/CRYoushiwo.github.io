---
layout: page
permalink: /blogs/CourseRecording/2023/ComputerNetwork/PhysicalLayer/AnalogTransmission/index.html
title: AnalogTransmission
---

# 模拟传输

- 数字数据转换为帯通模拟信号传统上称为数字到模拟转换
- 将低通模拟信号转换为帯通信号传统上被称为模拟到模拟转换
- 数据速率$N$和信号速率$S$的关系：$S = N\cdot \frac{1}{r}$
    - 其中，$r$是一个信号元素携带的数据元素个数
    - Example 1
        - 模拟信号的每个信号单元运送4位，如果每秒发送1000 个信号单元，试求比特率
        - 解：
            1. r = 4, S = 1000
            2. $N = S\times r = 4000 bps$
    - Example 2
        - 一个信号的比特率为8000 bps ，波特率为1000 baud，问每个信号元素携带多少个数据元素？需要多少个信号元素?
        - 解：
            
            <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/PhysicalLayer/Chapter5/Untitled.png" class="blog-image" >
            
- 载波信号：在模拟传输中，发送设备产生一个高频率信号作为基波来承载信息
- 幅移键控
    - 通过改变载波信号的振幅生成信号元素
    - 二进制ASK
        - ASK带宽：$B = (1+d)\cdot S$
            - $d \in [0,1]$，下同
- 频移键控
    - 通过改变载波信号的频率生成信号元素
    - 二进制FSK
        - FSK带宽：$B = (1+d)\cdot S +2\delta f$
        - $2\delta f$ 最小值为$S$