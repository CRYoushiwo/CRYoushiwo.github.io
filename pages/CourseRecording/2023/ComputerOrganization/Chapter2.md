---
layout: page
permalink: /CourseRecording/2023/ComputerOrganization/Chapter2/index.html
title: ComputerOrganizationChapter2
---

# 计算机系统中的数据表示

- 反码与真值不能一一对应
- 负数的码值大于正数的码值：原码，反码，补码
- 负数的补码大于正数的补码
- 求补运算
- 变形补码：左符号（真正符号），右符号（判断溢出）
- *补码的符号位扩展（比如从8位扩展到16位）
- 移码定义：真值加上一个偏移量（移码和真值的转换）
- 机器零：尾数为0，阶码最小表示
- 奇校验：奇数个1，C=0；偶校验：奇数个1，C=1
- 检查e个错误，需要最小海明码：（e+1）；检测和校验e个错误，要最小海明码：（2e+1）
- 发现并改正一位错：$2^r \ge k+r+1$ 数据位：k；校验位：r
- 海明码的校验位构造与检验
- CRC编码的构造
- 八位二进制表示整数补码，如何判断有无百位，有无十位？