---
layout: page
permalink: /blogs/CourseRecording/2023/AnalogElectronicTechnology/Chapter9/index.html
title: AnalogElectronicTechnologyChapter9
---

# 低频功率放大电路

## 功率放大器分类

- 甲类放大
- 乙类放大
    - T1、T2两个晶体管都只在半个周期内工作的方式，称为乙类放大
    - 交越失真（非线性失真，输入信号很小时，达不到三极管的开启电压，三极管不导电）
- 甲乙类放大
    - 为解决交越失真，可给三极管稍稍加一点偏置，使之工作在甲乙类
    - 利用二极管提供偏置电压
        - 二极管作用：二极管正向导通，为三极管提供所需的偏压
    - 利用三极管恒压源提供偏置

## 互补对称功率放大电路

- 双电源互补对称电路（OCL电路）
    - 特点
        - 由NPN型、PNP型三极管构成两个对称的射极输出器对接而成
        - 双电源供电
        - 输入输出端不加隔直电容
    - 计算：$\xi = \frac{U_{cem}}{U_{CC}}$
        - 输出功率：$P_o = \frac{1}{2}\frac{\xi^2 U_{CC}^2}{R_L}$
        - 直流电源供给功率：$P_E = \frac{2}{\pi}\frac{\xi U_{CC}^2}{R_L}$
        - 集电极功率损耗：$P_C = P_E - P_o$
        - 效率：$\eta = \frac{\pi}{4}\xi$
- 单电源互补对称电路（OTL电路）
    - 特点
        - 单电源供电
        - 输出加有大电容
    - 计算：同OCL电路，$只需将U_{CC}换成\frac{1}{2}U_{CC}$

## 复合管

- 作用：提高电流放大倍数，扩大电流的驱动能力
- 规则
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/AnalogElectronicTechnology/Chapter9/Untitled.png" class="blog-image" >
    
- 计算
    - $\beta = \beta_1\beta_2$
    - $r_{be} = r_{be1}+(1+\beta_1)r_{be2}$