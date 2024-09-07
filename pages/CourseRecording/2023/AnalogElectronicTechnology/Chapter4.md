---
layout: page
permalink: /CourseRecording/2023/AnalogElectronicTechnology/Chapter4/index.html
title: AnalogElectronicTechnologyChapter4
---

# 场效应管放大电路

## 结型场效应管

- 工作原理：改变$U_{GS}$，从而改变PN结阻挡层的宽度，沟道电阻随之改变，达到控制漏极电流的效果
- N型沟道结型场效应管与P型沟道结型场效应管
- 栅极与源极的反向电压$U_{GS}$
- 夹断电压$U_P$与预夹断
    - $U_{DG} = U_{DS} - U_{GS} = U_P$
- 输出特性曲线（漏极电流和漏、源电压关系）
    - 可变电阻区：固定$U_{GS}$，线性电阻
    - 恒流区
    - 击穿区（雪崩击穿） 击穿电压 $BU_{DS}$，$U_{GS} = 0$时，用$BU_{DSS}$
    - 截止区
- 转移特性曲线（漏极电流和栅、源电压关系）
    - 饱和漏极电流 $I_{DSS}$
    - $I_D = I_{DSS}(1 - \frac{U_{GS}}{U_P})^2$

## 绝缘栅场效应管

- N沟道增强型MOS场效应管
    - 工作原理：利用$U_{GS}$控制“感应电荷”数量，沟道电阻随之改变，达到控制漏极电流的效果
- N沟道耗尽型MOS场效应管
- 二者区别：
耗尽型：绝缘层中认为掺入正离子，$U_{GS} = 0$时，存在沟道
增强型：只有在$U_{GS} > U_T > 0$时，存在沟道

<div style="display: flex; justify-content: center;">
  <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071352133.png" style="max-width: 80%; height: auto;">
</div><br>

## 场效应管主要参数

- 直流参数
    - 饱和漏极电压 $I_{DSS}$
    - 夹断电压 $U_P$
    - 开启电压$U_T$
    - 直流输入电阻 $R_{GS}$
- 交流参数
    - 低频跨导 $g_m = - \frac{2I_{DSS}}{U_P}(1 - \frac{U_{Gs}}{U_P})$ (结型场效应管)
    - 级间电容
- 极限参数
    - 漏极最大允许耗散功率 $P_{Dm}$
    - 漏、源间击穿电压 $BU_{DS}$
    - 栅源间击穿电压 $BU_{GS}$

## 场效应管的特点

- 电压控制器件
- 输入端几乎无电流，输入电阻较高
- 电流由多数载流子形成，温度稳定性较好
- 一般电压放大系数小于三极管组成的放大电路

## 场效应管放大电路

- 静态工作点与偏置电路
    - 静态工作点与偏置电路：$I_D,U_{GS}$
    - 自给偏压电路
        - 适用于结型和耗尽型
        - $U_{GS} = -I_DR_S$
    - 分压式偏置电路
        - $U_{GS} = U_G - U_S = \frac{R_1}{R_1+R_2}U_{DD} - I_DR_S$
    - 图解法： $U_{DS} = U_{DD} - I_D(R_D + R_S)$
    - 计算法： $I_D = I_{DSS}(1 - \frac{U_{GS}}{U_P})^2$
- 场效应管的微变等效电路
- 共源极放大电路
- 共漏极放大电路
- 共栅极放大电路