---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/DataLinkLayer/MultipleAccess/index.html
title: MultipleAccess
---

# 多路访问

## 基本概念

- 共享信道的问题：**若多个设备在共享的广播信道上同时发送数据，则会造成彼此干扰，导致发送失败**
- 以太网（有线LAN）
    - 逻辑链路控制（LLC）：与传输媒体无关
        - 封装成帧
        - 透明传输
        - 数据链路控制
    - 媒体接入控制（MAC）：与传输媒体有关
        - 保证使用介质的每个结点隔离来自同一信道上其他结点所传输的信息
    - 网络适配器（网卡，adapter）
    - MAC地址（硬件地址，物理地址，数据链路层地址）
        - 点对点通信
        - 广播通信
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072209561.png" style="max-width: 80%; height: auto;">
        </div><br>
        

## 多路访问控制协议

| 随机访问协议 | 受控访问控制协议 | 通道化协议 |
| --- | --- | --- |
| 动态 | 动态 | 静态 |

### 随机访问协议

- $T_{fr} = 2T_p = \frac{L}{C} = \frac{2d}{V_p}$
    - $T_{fr}$：一个帧的平均传播时间（$s$）
    - $T_p$：传播时延（$s$）
    - $L$：帧的长度（比特）
    - $C$：带宽（$bps$）
    - $d$：传播距离（$m$）
    - $V_p$：数据在链路的传播速度（$2\times10^8m/s$）
    - $G$：帧传输时间内系统产生的帧的平均数量
- ALOHA协议
    - 二进制指数回退
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072209400.png" style="max-width: 80%; height: auto;">
        </div><br>
        
    - 纯ALOHA可能冲突的时间（脆弱时间）：$2\cdot T_{fr}$
    - 纯ALOHA吞吐量：$S = G\times e^{-2G}$
        - 当 $G = 0.5$ 时，$S_{max} = 0.184$
    - 时隙ALOHA可能冲突的时间：$T_{fr}$
    - 时隙ALOHA吞吐量：$S = G\times e^{-G}$
        - 当 $G = 1$ 时，$S_{max} = 0.368$
    - Example
        - 一个时隙ALOHA网络使用一个带宽为200kbps的共享通道发送200b的帧，如果系统**（包括所有站点）**产生每秒1000个帧，则吞吐量？
            - $G = \frac{\frac{200\times 10^3}{200}}{1000} = 1$ ，$S = 0.368$，吞吐量为 $0.368*1000 = 368$
- CSMA/CD协议
    - 组成
        - **多址接入（MA）**：说明这是总线型网络。
        - **载波监听（CS）**：即“边发送边监听”
        - **碰撞检测（CD）**：适配器边发送数据，边检测信道上的信号电压的变化情况，检测碰撞
    - 以太网单程端到端传播时延：$\tau$（$T_p$）
        - 站点从发送帧开始，经过争用期 𝟐𝝉 这段时间还没有检测到碰撞，就可以肯定这次发送不会产生碰撞
    - 关键截点
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072209595.png" style="max-width: 80%; height: auto;">
        </div><br>
        
        - 最短碰撞检测时间（中间处发生碰撞）：$\tau$
        - 最长碰撞检测时间（接收方处发生碰撞）：$2\cdot \tau$
        - 最短帧长：$数据传输速率\cdot2\cdot\tau$
            - 如果小于最短帧长，则发送端无法判定发送帧是否发生碰撞
        
        <aside>
        📢 10Mb/s共享总线以太网（传统以太网，即10BASE-T）规定：争用期 $2τ$ 的值为 $512b(64B)$ 的发送时间，即 $51.2μs$
        
        u理论上，总线长度为 $**2×10^8 m/s×25.6μs=5120m**$
        
        </aside>
        
        - 最长帧长：人为规定
            - 如果大于最长帧长，则其他发送端无法发送帧，长期处于等待状态
    - 截断二进制指数退避
        - $2\tau \times r$
        - 其中 $r \in \{0,1,...,2^k - 1\}$
    - 信道利用率
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072209886.png" style="max-width: 80%; height: auto;">
        </div><br>
        
        - $S_{max} = \frac{T_0}{T_0 + \tau}$（忽略前面的等待时间）
        - 提高信道利用率
            1. 共享总线以太网端到端的距离不应太长
            2. 帧的长度应尽量大
- CSMA/CA 协议
    - 在 CD 的基础上，增加三个方法避免冲突
        - 帧间间隔（IFS）
        - 竞争窗口
        - 确认

### 受控访问控制协议

- 预约访问协议
    - 站点在发送数据之前需要预约，将时间划分为时隙，在每个时隙内，在数据帧之前发送一个预约帧
- 轮询访问协议
    - 设备分为主站和从站。主设备控制链路，从设备跟随指令工作
    - 两个功能
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072210500.png" style="max-width: 80%; height: auto;">
        </div><br>
        
        左边是选择，右边是轮询
        
        - 轮询：主设备接收数据，从设备发送数据
        - 选择：主设备发送数据，从设备接收数据
- 令牌协议
    - 令牌作为发送数据的权利标志，在所有站点中循环传递
    - 欲发送数据的站点截获令牌，发送完毕释放令牌

### 通道化协议

- 频分多址
    - 每个站点可在相同的时间占用不同的频带
- 时分多址
    - 每个站点在不同的时间占用同样的频带
- 码分多址
    - 每个站点可以在相同的时间使用相同的频带进行通信
    - 每个站点都被指派一个唯一的 m 比特码片序列
    - 正交序列（芯片数字序列）
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072210816.png" style="max-width: 80%; height: auto;">
        </div><br>
        
        - 每个序列都有 $N$ 个元素， $N$ 为站点数
        - 相同序列相乘，结果为 $N$
        - 不同序列相乘，结果为 $0$
    - example
        - 假设给某个站指派的 8 比特码片序列为01011001
            - 则发送比特1：01011001
            - 则发送比特0：10100110
            - 码片向量：（-1 +1 -1 +1 +1 -1 -1 +1）