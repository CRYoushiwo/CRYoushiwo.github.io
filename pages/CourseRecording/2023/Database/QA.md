---
layout: page
permalink: /CourseRecording/2023/Database/QA/index.html
title: DatabaseQA
---

# 题型分析

## 第一章 数据库概述

- 基本概念
    - 数据模型
        - 数据模型的组成要素【数据结构，数据操作，完整性约束条件】
        - E-R图的绘制
        - 常见数据模型【层次模型，网状模型，关系模型…】
    - 数据库系统的结构
        - 三级模式结构【内模式，模式，外模式】
        - 两层映像【外模式/模式映像，模式/内模式映像】
            - 前者保证逻辑独立性，后保证物理独立性
    - 数据库组成
- 题型
    - 文件处理系统存在弊端【数据冗余多、数据不一致、不完整、不安全、数据之间的联系弱】
    - 概念模型的E-R图的绘制
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072356027.png" style="max-width: 80%; height: auto;">
        </div><br>

        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072356756.png" style="max-width: 80%; height: auto;">
        </div><br>

        

## 第二章 数据库设计和关系模式规范化理论

- 关系特征（6）
- 关系模型的完整性（3）
- 外码的判断
- 函数依赖示意图的绘制
- 范式的判断与范式相关结论的证明
    
    <div style="display: flex; justify-content: center;">
        <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072357364.png" style="max-width: 80%; height: auto;">
    </div><br>

- **函数依赖（3）与范式（4）**
    - 判断函数依赖，判断范式
    - 各个范式的特点

## 第三章 关系代数和SQL

- 根据题目所给的关系模式和查询要求，给出关系代数表达式
- 根据关系代数表达式和关系，写出关系运算的结果
- 根据题目所给的关系模式和查询要求，给出SQL语句

## 第四章 完整性和安全性

### 数据库安全性

- 用户识别与鉴定（最外层）
- 存取控制
    - 自主存取控制（DAC）
        - 授权与回收
            - GRANT（授权）
            - REVOKE（回收）
            - ROLE（角色，既可作为用户也可以作为权限）
            
    - 强制存取控制（MAC）
        - 主体（用户与进程）与客体（受主体操作的对象）
        - 敏感度标记
            - 许可证级别（主体）
            - 密级（客体）
        - 规则：
            - 主体的许可证级别**大于或等于**客体的密级时，该主体才能读出相应客体
            - 仅当主体的许可证级别**等于**客体的密级时，该主体才能写相应客体
        
    
    **DAC和MAC共同构成DBMS的安全机制**
    
- 视图机制
- 审计
- 统计数据库安全性
    - 不允许用户查询聚集类型的信息
    - 不允许查询单个记录信息
    - 规则
        - 任何查询，需要涉及N个以上记录
        - 任意两个查询的相交数据项不能超过M个
        - 任意用户查询次数不能超过 $1+(N-2)\frac{1}{M}$

### 数据库完整性

- 完整性约束机制
    - 实体完整性
        - 定义：PRIMARY KEY【列级或表级】
    - 参照完整性
        - 定义：FOREIGN KEY <列名> REFERENCES <表名>  (<列名>)
        - 违约处理：拒绝，级联删除/修改，设为空值
    - 用户定义完整性
        - 列值非空（NOT NULL），列值唯一（UNIQUE），检查是满足一个布尔表达式（**CHECK**）
        - 违约处理：拒绝
    - 完整性约束命名子句
        - **CONSTRAINIT**
        
        <div style="display: flex; justify-content: center;">
            <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072357643.png" style="max-width: 80%; height: auto;">
        </div><br>
        
        - 使用 ALTER TABLE 修改完整性约束
- 域的完整性约束
    - DOMAIN
- 触发器
    - TRIGGER
    
    <div style="display: flex; justify-content: center;">
        <img src="https://cryoushiwo.oss-cn-hangzhou.aliyuncs.com/course-recording/202409072357795.png" style="max-width: 80%; height: auto;">
    </div><br>
    

## 第五章 数据库内核-存储引擎

- 分槽页面结构的空间占用情况分析
- 行存储和列存储的选择
- 顺序文件组织的插入和删除（链表的变化）
- 哈希表文件组织（哈希表的绘制）
- 根据页面访问编号序列，选择页面置换算法（LRU算法和CLOCK时钟置换算法），完成缓冲区管理过程分析

## 第六章 数据库内核-SQL引擎

- 字符标记流的书写
- 语法分析树的绘制
- 逻辑重写的优化分析（几个常见的规则）
- **物理算子的实现（主要为I\O代价的分析）**
- B+树的插入和删除
- B+树插入多个相同值的情况分析
- 三种静态哈希的插入和删除
- 位图索引的占用空间

## 第七章 事物

- 解释ACID特性
- 说明说明随若隔离级别的增高，数据库一致性与数据库性能分别是怎样变化的，并简单阐述理由
- 解释事物的并发执行
- **解释串行化调度，冲突可串行化调度，视图可串行化调度（还要会举例子！）**
- 优先图分析是否冲突可串行化调度