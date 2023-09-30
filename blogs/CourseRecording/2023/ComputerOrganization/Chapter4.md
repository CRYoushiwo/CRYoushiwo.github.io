---
layout: page
permalink: /blogs/CourseRecording/2023/ComputerOrganization/Chapter4/index.html
title: ComputerOrganizationChapter4
---

# 存储系统

## 第四章 存储系统

- SRAM：“静态”——只要保持通电，数据可以无限制读取
- DRAM：“刷新”
    - 集中式
    - 分散式
    - 异步式
- DRAM中，CAS具有OE引脚的功能！
- DRAM刷新周期
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerOrganization/Chapter4/Untitled.png" class="blog-image" >
    
- 闪存

    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerOrganization/Chapter4/Untitled%201.png" class="blog-image" >
    
- 同步DRAM（SDRM）
    - 内含两个交错的存储阵列，当CPU从一个存储体或阵列访问数据时，另一个就已为读写数据做好了准备，通过这两个存储阵列的紧密切换，读取效率就能得到成倍的提高
- 双倍数据传输（DRR）
    - DDR在时钟信号上升沿与下降沿各传输一次数据，使得DDR的数据传输速度为传统SDRAM的两倍
    - 带宽 = 内存核心频率 × 内存总线位数 × 倍增系数
    - 数据传输频率 = 时钟频率 * 2
    - 时钟频率 = 核心频率 * n
    - EEPROM与闪存
        - EEPROM能在字节水平上进行删除和重写而不是整个芯片擦写，而闪存的大部分芯片需要块擦除
        - NOR型：有**独立的地址线和数据线**，基本存储单元是bit，**按存储单元进行删除和访问**，容量较小，价格较贵
        - NAND型的地址线和数据线是共用的I/O线，基本存储单元是页(Page)，类似硬盘的扇区；成本要低一些，而容量大得
        
- CPU的写（或读）内存的周期应大于等于存储器芯片所要求的写（或读）时间
- 补充的存储器
    - 多体存储器
        - 数据位顺序相连
        - 注意字节允许型号的书写
        
        <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerOrganization/Chapter4/Untitled%202.png" class="blog-image" >
        
        - 交叉组织方式
            
            <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerOrganization/Chapter4/Untitled%203.png" class="blog-image" >
            <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerOrganization/Chapter4/Untitled%204.png" class="blog-image" >
            
    - 双端口存储器
    - 先进先出存储器
    - 相联存储器
- 磁盘的主要指标
    - 道密度
    - 位密度
    - 非格式化容量
    - 格式化容量
    - 数据传输率
- RAID
    - 主要使用的三种技术：条带化，镜像，校验