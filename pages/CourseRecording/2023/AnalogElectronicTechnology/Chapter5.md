---
layout: page
permalink: /CourseRecording/2023/AnalogElectronicTechnology/Chapter5/index.html
title: AnalogElectronicTechnologyChapter5
---

# 负反馈放大电路

## 杂七杂八的概念

- 反馈
    
    将电路的输出量的部分或全部，通过一定的元件，以一定的方式回送到输入回路并影响输入量，和输出量的过程
    
- 自激振荡（3）
    
    定义：输入端不加信号，其输出端也有一定频率和幅度的输出波形
    
    产生条件：负反馈变成正反馈，并且$AF = -1$
    
    消除方法：减小反馈深度或引入相位矫正网络
    
- 串联反馈和并联反馈
    
    串联反馈：输入电压和反馈电压在输入回路中是相串联的
    
    并联反馈：输入电流和反馈电流在输入端中流向同节点
    
- 电压反馈和电流反馈
    
    电压反馈：反馈信号正比于输出电压
    
    电流反馈：反馈信号正比于输出电流
    
- 基本量
    - 开环放大倍数：$A = \frac{x_o}{x_{id}}$
    - 反馈系数：$F = \frac{x_f}{x_o}$
    - 闭环放大倍数：$A_f = \frac{x_o}{x_i}$
    - 环路增益：$AF = \frac{x_f}{x_{id}}$
    - 反馈深度：$\lvert 1 + AF\rvert$

## 反馈类型的判断

- 分析存在的网络
- 判断是交流反馈 or 直流反馈 or 交、直流反馈
    
    对整个反馈网络分析
    
- 判断是正反馈 or 负反馈
    1. 单级反馈（瞬时极性法）
        1. 从输入端
            1. 串联反馈：起始变化量为电压$(e.g.\ U_{be})$
            2. 并联反馈：起始变化量为电流$(e.g.\ I_b)$
        2. 从输出端
            1. 电压反馈：起始变化量为电压$(e.g.\ U_o)$
            2. 电流反馈：起始变化量为电流$(e.g.\ I_e )$
    2. 多级反馈（相位极性法）
        1. 反馈网络的取样点作为假想放大器的输出端
        2. 反馈网络的注入点作为假想放大器的输入端
        3. 如果同相放大，则为正反馈；如果反相放大，则为负反馈
- 判断组态
    1. 输出端：串联反馈 or 并联反馈
        1. 注入端与输入同一端：并联反馈
        2. 注入端与输入不同一端：串联反馈
    2. 输出端：电压反馈 or 电流反馈
        1. 取样端与输出同一端：电压反馈
        2. 取样端与输出不同一端：电流反馈

## 负反馈对放大器性能的影响

- 降低放大器的放大倍数
- 提高放大倍数的稳定性
    - 串联电压负反馈稳定电压增益
    - 串联电流负反馈稳定互导增益
    - 并联电压负反馈稳定互阻增益
    - 并联电流负反馈稳定电流增益
    - $\frac{dA_f}{A_f} = \frac{1}{1+AF}\frac{dA}{A}$
- 减小非线性失真和抑制干扰、噪声
    
    <aside>
    ⚠️ 减少的是反馈环内产生的，反馈环外侵入的或原输入信号带入的不起作用
    
    </aside>
    
- 扩展频带
    
    $f_{hf} = (1+AF)f_h; \ f_{lf} = \frac{1}{1+AF}f_l$
    
- 负反馈对输入电阻的影响（取决于串联与并联）
    - 串联反馈：$r_{if} = (1+AF)r_i$
    - 并联反馈：$r_{if} = \frac{1}{1+AF}r_i$
- 负反馈对输出电阻的影响（取决于电压与电流）
    - 电流反馈：$r_{of} = (1+AF)r_o$
    - 电压反馈：$r_{of} = \frac{1}{1+AF}r_o$
- 信号源内阻对反馈的影响
    - 信号源内阻小——>串联反馈效果好
    - 信号源内阻大——>并联反馈效果好

## 深度负反馈电压增益

<aside>
⚠️ 在深度负反馈被取样信号单独作用时求解，注意正、负号！

</aside>

$X_i = X_f$

<div style="display: flex; justify-content: center;">
  <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071352000.png" style="max-width: 80%; height: auto;">
</div><br>

<div style="display: flex; justify-content: center;">
  <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071353058.png" style="max-width: 80%; height: auto;">
</div><br>

<div style="display: flex; justify-content: center;">
  <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071353347.png" style="max-width: 80%; height: auto;">
</div><br>

<div style="display: flex; justify-content: center;">
  <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/images/202409071353375.png" style="max-width: 80%; height: auto;">
</div><br>

## 根据性能要求，引入负反馈

- 注意要保证引入的是负反馈！

## 待解决问题

- 课后习题
    1. 分析含场效应管的负反馈？
    2. 分析含差动放大电路的负反馈？
    3. 如何根据条件，引入负反馈（特别是对于唯一情况）？