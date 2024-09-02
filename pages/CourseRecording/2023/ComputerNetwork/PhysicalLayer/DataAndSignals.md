---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/PhysicalLayer/DataAndSignals/index.html
title: DataAndSignals
---

# 数据与信号

## 信号

- 分类
    - 模拟信号（连续）
    - 数字信号（离散）
- 模拟信号
    - 频域和时域的表示
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/PhysicalLayer/Chapter3/Untitled.png" class="blog-image" >
        
        - 用频域图中单个峰值可表示时域图中一个完整正弦波
    - 复合信号
        - 周期和非周期信号分解
            
            <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/PhysicalLayer/Chapter3/Untitled%201.png" class="blog-image" >
            
- 数字信号
    - 电平与信号
        - **信号有L个电平，则每个信号位可以携带log2L个bit位**
    - 周期和非周期信号分解
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/PhysicalLayer/Chapter3/Untitled%202.png" class="blog-image" >
        

## 数字信号传输

- 基带传输：直接传输数字信号
    - 需要带宽下限频率为0的低通通道
- 频带传输：把数字信号转换成模拟信号进行传输
    - 宽带传输：一种特殊的频带传输（带宽宽的特点）
    - 数字信号近似模拟信号
        - 所需的带宽与比特率成正比
        - 同样比特率情况下，叠加更多谐波，其合成后的模拟信号越近似于数字信号
        - 比特率与带宽
            - 最小带宽 = 比特率/2
            - 最大比特率 = 带宽 * 2
            - Eample 1
                - 基带传输发送比特率 $n=1Mbps$，求低通通道所需带宽
                    1. 最小带宽、使用第一谐波 $\rightarrow$ $B_1=\frac{n}{2}=500KHz$z
                    2. 使用第一、三谐波 $\rightarrow$ $B_3=3×B_1=1.5MHz$
                    3. 使用第一、三、五谐波 $\rightarrow$ $B_5=5×B_1=2.5MHz$ 
            - Eample 2
                - 一条带宽 $B=100kHz$ 的低通通道，求最大比特率
                    1. 使用第一谐波得到最大比特率  $\rightarrow$ $n=2×B=200kbps$

## 典型的传输减损

- 衰减：通过某种介质传输时，信号能量下降
    - 分贝表示信号损失或增益强度
        
        $dB=10\lg\frac{P_2}{P_1}$  其中，$P_1$、$P_2$表示信号前后的功率
        
- 失真：不同信号成分具有不同的传播速度导致信号波形失真
- 噪声：外界干扰，电缆中的电子随机移动而产生的额外信号
- 信噪比：信号功率与噪声功率的比率$SNR=\frac{P1}{P2}$
    - 其中
        - $P_1$：平均信号功率
        - $P_2$：平均噪声功率
    - 分贝单位：$SNR_{dB}$=$10\lg SNR$

## 数据速率限制

<img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/PhysicalLayer/Chapter3/Untitled%203.png" class="blog-image" >

- 定义
    - $N$：比特率
    - $C$：比特率上限
    - $B$：带宽
    - $L$：电平数
- 尼奎斯特定理（无噪声通道）
    - 有限带宽 $B$ 下，通道的极限波特率(码元速率)为 $S=2B$
- 奈奎斯特速率（无噪声通道）
    - 给定带宽下理论上的最大比特率: $N=2×B×log_2L$
- 香农容量定理（有噪声通道）
    - 确定噪声通道理论上的最高数据速率: $C=B×log_2(1+SNR)$
    - 其中通道容量是指通道的传输容量，即每秒的比特数等于比特率
    - 当 $SNR$ 较大时，$SNR+1\approx SNR$，则 $C=B×\frac{SNR_{dB}}{3}$
    - Eample
        - 一通道带宽 $B=1MHz$，信噪比 $SNR=63$，求合适的比特率以及信号电平
        - 解：由香农公式确定比特率上限
            - $C=B\times log_2(1+SNR)=6Mbps$
            - 为了获得更好的性能，取通道比特率 $N=4Mbps$
            - 由奈奎斯特公式计算信号电平数:
                - $N=2\times B\times log_2L$ $\rightarrow$ $L=4$
- 香农容量定理给出**数据速率的上限**，奈奎斯特公式给出**所需的信号电平数**
- 带宽
    - 以赫兹为单位
    - 以比特率为单位

## 性能

- 带宽：链路的潜在衡量值，链路最大的数据传输速率
- 吞吐量：发送速度快慢的实际衡量值，小于带宽
- 延迟：第一个位开始发出到整个报文完全到达目标所经历的时间
    - 延迟 = 传播时间 + 传输时间 + 排队时间 + 处理延迟
        - 传播时间：一个位从源传输到目标所需时间（与介质相关）
            - $Tp=\frac{d}{v}$
        - 传输时间：传输一个报文的时间
            - $Tt=\frac{LF}{B}$
            - 其中，帧长 $LF$ 表示一个报文长度
        - 排队时间：每个中间或端设备在处理报文前保持报文所需的时间
        - 带宽与延迟乘积：能充满链路的位数（传播时间 * 带宽）