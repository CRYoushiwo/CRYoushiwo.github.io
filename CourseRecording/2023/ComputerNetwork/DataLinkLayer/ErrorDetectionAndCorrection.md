---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/DataLinkLayer/ErrorDetectionAndCorrection/index.html
title: ErrorDetectionAndCorrection
---

# 检错与纠错

## 差错的区别

| 单个位差错 | 突发性差错 |
| --- | --- |
| 几乎不发生 | 常发生 |
|  | 差错长度（第一个差错位和最后一个差错位） |

## 块编码

- 码字(n) = 数据字(k) + 冗余位(r)
- 汉明距离：两个相同长度的字之间不同位数
    - 最小汉明距离：在一组相同长度的字之间最小不同位数

| 检错码 | 纠错码 |
| --- | --- |
| 块编码的最小汉明距离=检错位数+1 | 块编码的最小汉明距离=2*纠错位数+1 |

## 线性块编码

- 任意两个有效码字的异或生成另一个有效码字
- **线性块编码的最小汉明距离**：具有最少1的个数的非0有效码字中1的个数
    - Example
        - 一组码字：00000，01011，10101，11110
            - 非0码1的个数分别为：3，3，4
            - 故最小汉明距离 = 3

| 几种常见线性块编码 | 检错效果 | 说明 |
| --- | --- | --- |
| 简单奇偶校验码 | 检错奇数位 | 默认是偶校验 |
| 汉明码【C(n, k)】 | 检错2位，纠错1位 | $n = m + k$ （k：数据位，n：码位，m：校验位个数）
$n = 2^m - 1$ |
| 循环冗余校验码（CRC）【同时也是循环编码】 |  | $n = m+k$（：数据位，n：码位）
所使用的除数：$n-k+1$

至少有两项
且 $x^0$ 的系数是1
生成多项式不能整除 $x^t$ + 1 
包含因子（x+1） |
- CRC——多项式运算（课后习题例24）
    - 加减：相同，删除相同项，把不同项结合在一起
    - 乘法：先数学相乘，再使用加减的规则
    - 除法：

## 校验和

- 反码运算相加
    - Example 1
        - 传输（7，11，12，0，6）
            - 7+11+12+0+6 = 36
            - 36 = **10**0100 $\rightarrow$6 = 0110（和，由左边超出部分与右边部分相加，即 0100 + 0010） $\rightarrow$ 9 = 1001（检验和，即反码）
    - Example 2
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter10/Untitled.png" class="blog-image" >