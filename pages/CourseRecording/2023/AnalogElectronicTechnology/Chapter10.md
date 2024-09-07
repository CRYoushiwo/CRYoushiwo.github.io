---
layout: page
permalink: /CourseRecording/2023/AnalogElectronicTechnology/Chapter10/index.html
title: AnalogElectronicTechnologyChapter10
---

# 直流电源

## 整流电路

利用二极管的单向导电特性

- 单相半波整流电路
    - $U_O = \frac{\sqrt{2}}{\pi}U_2 \approx 0.45U_2$
    - $I_O = I_D = 0.45\frac{U_2}{R_L}$
    - $I_F \ge I_D = 0.45\frac{U_2}{R_L}$
    - $U_R \ge \sqrt{2} U_2$
- 单相全波整流电路
    - $U_O = \frac{2\sqrt{2}}{\pi}U_2 \approx 0.9U_2$
    - $2I_D = I_O = 0.9\frac{U_2}{R_L}$
    - $I_F \ge I_D = 0.45\frac{U_2}{R_L}$
    - $U_R \ge 2\sqrt{2} U_2$
- 单相桥式整流电路
    - $U_O = \frac{2\sqrt{2}}{\pi}U_2 \approx 0.9U_2$
    - $2I_D = I_O = 0.9\frac{U_2}{R_L}$
    - $I_F \ge I_D = 0.45\frac{U_2}{R_L}$
    - $U_R \ge \sqrt{2} U_2$
- 整流二极管的选择
    - $二极管额定电流\geq 2I_D$
    - $最大反向电压 \geq 2U_R$

## 滤波电路

### 电容滤波电路

- $0.9U_2 < U_O < \sqrt{2}U_2$
    - 一般取：$U_0 = 1.2U_2$
- 整流二极管
    - $I_F \ge (2$~$3)\frac{1}{2}\frac{U_0}{R_L}$
- 滤波电容：
    - $R_LC \ge (3$~$5)\frac{T}{2}$

## 稳压电路

<aside>
➡️ 输入电压变化（ $U_1$ ），负载电流变化（ $I_L$ ,加上电源内阻的影响）

</aside>

- 稳压二极管稳压电路
- 线性串联型稳压电源
    - 基准电压源，取样电路，比较放大电路，调整管【共基极三极管】
    - 输出电压调节范围的计算【取样电路的电阻】
- 三端固定式集成稳压电路

<aside>
➡️ 引脚判断，根据名称判断输出电压

</aside>

- CW78系列<输出电压 $U_{XX}$：3引角-2引角>
- CW79系列<输出电压 $U_{XX}$：3引脚-1引脚>
    
    <div style="display: flex; justify-content: center;">
        <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071401377.png" style="max-width: 80%; height: auto;">
    </div><br>

    - 应用
        - 输出为固定电压的电路
        - 输出正负电压的电路
        - 提高输出电压的电路
        - 输出电压可调式电路
        - 作恒流源使用