---
layout: page
permalink: /blogs/CourseRecording/2023/AnalogElectronicTechnology/QA/index.html
title: AnalogElectronicTechnologyQA
---

# 总复习

## 半导体器件

- 概念与术语
    - PN结形成机理
    - PN结伏安特性曲线，死区电压，正向导通压降
    - 扩散运动和漂移运动
    - 雪崩击穿和齐纳击穿
    - 正偏，反偏时，势垒电容和扩散电容
    - 二极管的两个模型（理想二级管，恒压降模型）
    - 其他二极管的工作状态
        - 稳压二极管（反向击穿）
        - 发光二极管（正向导通）
        - 光电二极管（反向饱和）
        - 光电耦合器件（反向击穿）
        - 变容二极管（反向饱和）
    - 三极管的放大条件（内部，外部）
    - 共射发射极放大状态，内部载流子传输过程
    - 输入特性曲线，输出特性曲线的三个区域特点
        - 截止区：$I_B = 0$
        - 放大区：$U_{BE} \geq 0.7V$
        - 饱和区：$U_{CES} = 0.3V$
    - 温度对特性曲线的影响$U_{BE}，I_{CEO}，I_{CBO}，\beta$
        - 输入特性曲线左移
        - 输出特征曲线上移动
- 根据 $I_B,I_C$ 变化量，估算 $\beta$
- 判断NPN/PNP，硅管/锗管，e/b/c极，工作状态
    - NPN/PNP：$U_{BE}$ 正负
    - 硅管/锗管：$\lvert U_{BE} \lvert = 0.7V or 0.2V$
    - e/b/c极： $U_B,U_C,U_E$ 大小关系
    - 工作状态
        
        饱和：$U_{CE} = 0.3V$
        
        放大：$U_{CE} > 0.3V$
        
        截止：$U_{BE} = 0$
        

## 放大电路基础

- 概念与术语
    - 静态工作点的作用：保证工作在放大区
    - $R_b,R_c,U_{cc}$ 对静态工作点的影响
- 静态工作点的确定
    - 解析法
        - $I_B,U_{CE}$
    - 图解法
        - 先确定 $I_{BQ}$
        - 再绘制直流负载线
        - 交点即为工作点
- 交流负载线的确定
    - Q点
    - $U_{CC}^{'} = U_{CEQ} + I_{CQ}\cdot R_{L}^{'}$
- 非线性失真的判断，以及调节失真方法
- 最大不失真电压
    - $U_{cem}$：$U_{CEQ} - U_{ces}(0.3V)（饱和限制）$ $or$ $I_{CQ}\cdot R_L^{'}（截止限制）$
    - 注意如果是求有效值，则还要除$\sqrt{2}$
- 直流通路和交流通路的绘制
- 三种基本放大电路放大性能指标，及其计算
    - $A_u，A_{us}，r_i，r_O$
- 静态工作点的稳定及其偏置电路
- 多级放大电路的性能指标分析

## 场效应管放大电路

- 工作原理
    - 结型场效应管：改变 $U_{GS}$，从而改变PN结阻挡层的宽度，沟道电阻随之改变，达到控制漏极电流的效果
    - 增强型MOS场效应管：利用$U_{GS}$控制“感应电荷”数量，沟道电阻随之改变，达到控制漏极电流的效果
- 六种场效应管的符号与特性曲线
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/QA/Untitled.png" class="blog-image" >
    

- 分压式偏置电路和自给偏压电路
    - 分压式偏置电路
        
        <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/QA/Untitled%201.png" class="blog-image" >
        
        - $U_{GS} = \frac{R_1}{R_1+R_2}U_{DD}-I_DR_S$
        - $I_D = I_{DSS}(1-\frac{U_{GS}}{U_P})^2$
    - 自给偏压电路（不适合增强型！！）
        
        <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/QA/Untitled%202.png" class="blog-image" >
        
    - $U_{GS} = -I_DR_S$
    - $I_D = I_{DSS}(1-\frac{U_{GS}}{U_P})^2$
- 共源发射极和共漏发射级
    
    图如上所示
    
    - 共源发射极
        - $A_u = -g_mR_L^{'}$
        - $r_i = R_G + R_1//R_2$
        - $r_o = R_D$
    - 共漏发射级
        - $A_u = \frac{g_mR_L^{'}}{1+g_mR_L^{'}}$
        - $r_i = R_G$
        - $r_o = \frac{1}{g_m}//R_S$

## 负反馈放大电路

- [题型分析](https://CRYoushiwo.github.io/blogs/CourseRecording/2023/AnalogElectronicTechnology/Chapter5) 

## 集成运算放大器

- 概念与术语
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
        
        <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/QA/Untitled%203.png" class="blog-image" >
        
    

## 集成运算放大器的应用

- [题型分析](https://CRYoushiwo.github.io/blogs/CourseRecording/2023/AnalogElectronicTechnology/Chapter7) 

## 直流电源

- 组成部分
    - 直流电源
        - 变压器
        - 整流电路
        - 滤波电路
        - 稳压电路
    - 串联型稳压电路
        - 基准电压源
        - 取样电路
        - 比较放大电路
        - 调整元件
- 整流电路
    - 参数表达式
        
        $U_o$- - - $U_2$
        
        $I_D$- - - $I_o$
        
    - 参数限制
        
        $U_{RM}$
        
        $I_F$
        
    - 桥式整流的故障
        - 二极管开路：变为半波整流（**注意后面是否有滤波电路，如果存在，则并非半波**）
        - 二极管反接：变压器有半周期被短路，会引起元器件损坏
- 滤波电路
    - 参数表达式
        
        $U_O$：与$R_LC$相关，成正比
        
    - 参数限制
        
        $U_{RM}$
        
        $R_LC = （3$~$5）\frac{T}{2}$ 
        
    - 故障
        - 电容开路： 仅存在整流电路
        - 负载$R_L$开路：$\sqrt{2}U_2$
- 稳压电路
    - 稳压二极管稳压电路
        - 限流电阻，负载电阻，$U_I，U_o，I_L$ 取值范围
            - $I_{zmin} \leq I_z \leq I_{zmax}$
            - $\frac{U_I-U_z}{R} - \frac{U_z}{R_{Lmax}} \leq I_{zmax}$
            - $\frac{U_I-U_z}{R} - \frac{U_z}{R_{Lmin}} \geq I_{zmin}$