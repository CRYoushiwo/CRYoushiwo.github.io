---
layout: page
permalink: /blogs/CourseRecording/2023/AnalogElectronicTechnology/Chapter7/index.html
title: AnalogElectronicTechnologyChapter7
---

# 集成运算放大器的应用

## 集成运放应用基础

- 集成运放的线性工作区
    - “虚短”：对于理想放大器，$A_{id}\rightarrow +\infty$ 同向输入端和反向输入端的电位相等
    - “虚断”：对于理想放大器，$r_{id} = \infty$ 集成运放端不取电流
- 集成运放的非线性工作区
    - 仍然具有“虚断”的特点

## 运算电路

<aside>
⚠️ 反相输入的输入电阻小，同相输入的输入电阻高
同相输入的共模电压高，反相输入的共模电压小

</aside>

### 比例运算电路

- 反相比例运算电路
    - 特殊：反相器$（R_2 = R_1）$
    
    $A_u = -\frac{R_2}{R_1}$
    

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled.png" class="blog-image" >

- 同相比例运算电路
    - 特殊：电压跟随器$（R_2 = 0\ or\ R_1 =\infty）$
    
    $A_u = 1+\frac{R_2}{R_1}$
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%201.png" class="blog-image" >
    
- 差动比例运算电路
    
    $U_o = -\frac{R_2}{R_1}U_{i1} + (1+\frac{R_2}{R_1})\frac{R_p}{R_2 + R_p}U_{i2}$
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%202.png" class="blog-image" >
    

### 求和电路

- 反相求和电路
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%203.png" class="blog-image" >
    
- 同相求和电路
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%204.png" class="blog-image" >
    
- 代数求和电路
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%205.png" class="blog-image" >
    

### 积分电路和微分电路

- 积分电路
    - 同相积分电路误差大（不考虑）
    - 反相积分电路 求$u_o = -\frac{1}{RC}\int u_i dt - u_c(0)$
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%206.png" class="blog-image" >
    
- 微分电路
    - $u_o = -RC\frac{du_i}{dt}$
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%207.png" class="blog-image" >
    

## 有源滤波电路

- 滤波定义
- 滤波器定义
- 四种滤波器
    - 低通滤波器 $w_h = \frac{1}{RC}$
    - 高通滤波器 $w_l = \frac{1}{RC}$
    - 带通滤波器 $w_h > w_l$（低通、高通串联实现）
    - 带阻滤波器 $w_h < w_l$（低通、高通并联实现）

## 电压比较器

- 简单电压比较器
    - 同相简单电压比较器
    - 反相简单电压比较器
- 滞回比较器
    - 同相滞回电压比较器
    - 反相滞回电压比较器
- 窗口比较器（双限比较器）

## 课件

- 运放工作在线性区的条件：引入负反馈
- 运放工作在非线性区的条件：电路开环工作或引入正反馈
- 比例运算电路
    - 电压跟随器
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%208.png" class="blog-image" >
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%209.png" class="blog-image" >
    
- 加减运算放大器
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%2010.png" class="blog-image" >
    
    **同相：**
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%2011.png" class="blog-image" >
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%2012.png" class="blog-image" >
    
    **反相：**
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%2013.png" class="blog-image" >
    

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%2014.png" class="blog-image" >

- 占空比：矩形波的高电平持续时间与其周期之比

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%2015.png" class="blog-image" >

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter7/Untitled%2016.png" class="blog-image" >