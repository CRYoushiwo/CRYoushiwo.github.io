---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/PhysicalLayer/BandwidthUtilization/index.html
title: BandwidthUtilization
---

# 带宽利用

## 复用

- 允许同时通过一条数据链路传输多个信号的一组技术

### 频分多路复用(FDM)

- 一种模拟技术，在链路带宽（以Hz为单位）大于要传输的信号的带宽之和时采用
- Example 1
    - 一个语音通道占用的带宽是4 kHz，要将三个语音通道合并到一条带宽为  12 kHz( 20 ~ 32 kHz)的链路。使用频域图表示这一配置过程，这里假定不使用防护频带
    - 解：
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072220269.png" style="max-width: 80%; height: auto;">
        </div><br>
        
- Example 2
    - 有5个通道，每个通道的带宽是100-kHz  全部进行多路复用。如果通道之间需要10 kHz的防护频带以防止干扰，则链路的最小带宽是多少  ?
    - 解：5 × 100 + 4 × 10 = 540 kHz

### **波分多路复用(WDM)**

- 合并多个光信号的模拟多路复用技术
- 在概念上与频分多路复用（FDM）相同，其原理也一样

### 时分复用（TDM）

- 组合多个低速的通道为一个高速通道数据的复用技术
- 同步时分复用
    - 链路速率是数据速率的 $*n*$ 倍
    - 每个输出单元的持续时间是输入单元的持续时间的$\frac{1}{n}$
    - 针对信道利用率的提高
        - 多级复用
        - 多时隙
        - 脉冲填充
    - Example 1
        - 每个输入连接的数据速率是 1 kbps。一个单元为1位，试确定 : (a) 每个输入单元的时隙, (b) 每个输出单元的时隙  (c) 每个帧的时隙 ?
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072220756.png" style="max-width: 80%; height: auto;">
        </div><br>
        
        - 解：
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072220692.png" style="max-width: 80%; height: auto;">
            </div><br>
            
    - Example 2
        - 将4个 1-kbps 的连接一起复用，每个单位为 1位.    试求(a) 复用前一位持续的时间(b) 链路传输速率(c) 时隙持续时间(d)一帧持续时间
        - 解：
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072221307.png" style="max-width: 80%; height: auto;">
            </div><br>
            
    - 存在的问题
        - 信道利用率不高
        - 解决方法
            - 多级复用
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072221874.png" style="max-width: 80%; height: auto;">
            </div><br>
            
            - 多时隙
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072221951.png" style="max-width: 80%; height: auto;">
            </div><br>
            
        - 脉冲填充
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072221759.png" style="max-width: 80%; height: auto;">
            </div><br>
            
            - 帧同步
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072221835.png" style="max-width: 80%; height: auto;">
            </div><br>
            
    - Example 3
        - 4个数据源，每个数据源每秒产生250个字符。如果交替的单元是  1个字符，每帧增加1个同部位，试确定(a)每个数据源的数据速率,(b) 每个数据源中每个字符的持续时间,(c) 帧速率,(d) 每帧的持续时间,(e) 每帧的位数(f)链路的数据速率
        - 解：
            
            <div style="display: flex; justify-content: center;">
                <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072221971.png" style="max-width: 80%; height: auto;">
            </div><br>
            
- 统计时分复用
    - 动态分配时隙

## 扩频

- **跳频扩频**
- **直接序列扩频**