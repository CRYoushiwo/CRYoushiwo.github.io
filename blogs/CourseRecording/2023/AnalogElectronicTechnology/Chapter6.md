---
layout: page
permalink: /blogs/CourseRecording/2023/AnalogElectronicTechnology/Chapter6/index.html
title: AnalogElectronicTechnologyChapter6
---

# 集成运算放大器

## 概念

- 零点漂移（4）
    - 零点定义：输入交变信号为0时的输出电压值被称为放大器的零点
    - 零点漂移：当输入短路(为零)时，输出信号不为零， 而是一个随时间漂移不定的信号
    - 零点漂移衡量：将输出漂移电压按电压增益折算到输入端的等效输入漂移电压值
    - 在零漂干扰下，信号放大条件：$u_i > u_{i漂移}$
- 信号
    - 共模信号：两个大小相等、极性相同的信号
    - 差模信号：两个大小相等、极性相反的信号
    - 共模输入信号$（U_{ic}）$：与共模信号相等
    - 差模输入信号$（U_{id}）$：差模信号之差
    - 任意输入信号：$U_{i1}，U_{i2}$
        - 信号分解：
            - $U_{ic} = \frac{U_{i1}+U_{i2}}{2}$
            - $U_{id} = U_{i1}-U_{i2}$
- 长尾式差动放大电路
    - 双电源供电作用
        1. 使信号变化幅度加大
        2. $I_{B1}$、$I_{B2}$由负电源$-U_{EE}$提供
        
    - $R_e$作用
        
        对直流和共模型号引入串联电流负反馈，对差模信号不起作用
        
        抑制温度漂移，稳定静态工作点
        
- 差动放大器的主要指标
    - 差模电压放大倍数$A_{ud}$
    - 共模电压放大倍数$A_{uc}$
    - 共模抑制比$CMRR$
    - 差模输入电阻$r_{id}$
    - 差模输出电阻$r_{od}$
    - 共模输入电阻$r_{ic}$
- 恒流源
    - 提高共模抑制比
    - $**r_{o3} = (1+\frac{\beta R_3}{r_{be}+R_1//R_2+R_3})r_{ce}**$
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter6/Untitled.png" class="blog-image" >