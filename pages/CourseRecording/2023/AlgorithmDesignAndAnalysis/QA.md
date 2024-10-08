---
layout: page
permalink: /CourseRecording/2023/AlgorithmDesignAndAnalysis/QA/index.html
title: AlgorithmDesignAndAnalysisQA
---

# 总复习

## 引言

- 软件开发的要素（不考）
    - 体系结构
    - 服务/库
    - 构件化
        - MVC（模块+交互界面+控制）
        - object request broker（通讯总线，对函数调用的延伸）
    - 算法与数据结构
        - algorithm def：对数据进行有限步骤的处理得到所需结果
- 最大子数组问题
    - 蛮力设计
- 插入排序
    - 针对问题的特定设计
    - 算法伪代码样式
    - **非递归算法的分析方法**

## 分治/规模压缩策略引入

- 分治策略的一般方法
    - 分、治、合并
- 二分应用于排序问题
    - 归并排序
    - 递归算法的分析
- n推n-1应用于排序
    - 插入排序的规模压缩视角**（按当前的排序顺序少）**
    - 冒泡/选择排序**（少的那一个为最大/最小值）**的规模压缩视角

## 算法分析的方法

- 渐近表示的数学定义
    - O/Θ/Ω的数学定义
    - 计算时间多项式的数学结论
- 计算时间递归式求解
    - 代换法
    - 递归树法（用来估计）
    - **主方法**

## 分治/规模压缩策略应用

- 建堆及堆排序
    - 建堆的二分方法
    - 建堆的n推n-1思路
    - 基于堆的排序
    - 堆/优先级队列及应用（所有操作都是对数级时间）
        - 减少一个元素
        - 增加一个元素
        - 修改一个元素
        - 查看最大值
- 快速排序
    - 另一种二分：分解多做事
    - 快速排序计算时间分析
    - 随机策略
- 排位统计/Select
    - Select问题的二分尝试（最大/最小/通用）
    - Select问题的n推n-1尝试
    - 二分：分解多做事
    - 最坏情况下线性时间Select
- 矩阵相乘的二分方法
    - 直接二分
    - Strassen的改进
- 最大子数组的二分方法
    - 二分：失败及修补
    - n推n-1（暂时失败）

## 排序问题的时间下界

- 基于比较的排序时间下界
    - 判定树模型（了解一下怎么画）
    - 最坏情况下的时间下界（nlgn）
- 线性时间内完成排序
    - 计数排序(主要思路：统计每个元素的出现次数，并利用这些统计信息直接放置元素到它们在输出数组中的正确位置)
    - 基数排序（主要思路：按照低位到高位的顺序，逐位对数字进行排序，通常使用稳定排序算法（如计数排序）作为子程序）
    - 桶排序（主要思路：将输入数据分散到有限数量的桶中，每个桶内部单独排序，最后依次将各个桶中的元素合并成有序序列）

## 动态规划策略及应用

- 装配线调度问题
    - 二分方法
    - n推n-1方法（DP）
- DP的一般方法
    - 刻画最优解的结构（OSS）
    - 递归定义最优解的值（形式统一）
    - 自下而上计算（还可使用备忘录）
    - 构造最优解
- 矩阵链乘问题
    - 二分、n推n-1尝试
    - 失败中得到正确的规模压缩方法
    - 完成计算：DP算法
- 最长公共子序列问题
    - 二分尝试（失败）
    - n推n-1：DP算法
- 最大子数组的DP算法
    - 换一种思路n推n-1

## 贪心策略及应用

- 活动选择问题
    - 规模压缩的尝试：二分及n推n-1
    - 如何从合并需求出发保证子问题独立性：DP
    - 特殊性：提前挑最好，得到贪心
- 背包问题-*5/8-
    - 均满足最优子结构
    - 分数背包的贪心算法
    - 0/1背包的DP算法
- Huffman编码
    - 构造Huffman树的贪心算法

## 最短路径问题

- 最优子结构落地问题
    - 计算次序问题
- 非负权图的计算次序
    - Dijkstra算法
- 含负权图的乱序计算
    - Bellman-Ford算法
- 重新建模以给出计算次序
    - 以边数为规模的建模：DP1
    - 以节点集合为规模的建模：Floyd-Warshall
- 非规模压缩策略
    - 重赋权：Johnson

## 难题怎么办

- 常规搜索
    - 无法采用规模压缩
        - 类蛮力的状态空间搜索
    - 限界函数的作用
        - **减少不必要的搜索**
        - 作用有限
    - 回溯法**（固定用深搜）**
        - 非优化问题（迭代形式）：皇后问题
        - 非优化问题（递归形式）：子集和数问题
        - 优化问题：0/1背包的搜索算法
    - 分支-限界法**（非深搜）**
        - 皇后问题的分支-限界方法
        - 最小代价检索：效率改进的尝试
- 难题有多难
    - 不可判定问题
        - 普斯特对应问题
        - 多元多项式整数根（费马大定理）
        - 停机问题
    - 可判定问题中的难题
        - NPC
            - TSP
            - 三色问题
            - 电路可满足性问题
- 难题的近似算法
    - 放弃理想目标的贪心
    - 领域搜索
        - 简单遗传算法SGA
- 基本步骤
- 课上讲的问题，如何把步骤说清楚