<div align="center">
  <img src="https://www.tensorflow.org/images/tf_logo_transp.png"><br><br>
</div>

-----------------


| **`Documentation`** |
|-----------------|
| [![Documentation](https://img.shields.io/badge/api-reference-blue.svg)](https://www.bipt.edu.cn/) |


# 北京邮电大学-数据挖掘竞赛-2018（tensorflow版本）
## 流程图

- 框架流程图

![流程图](picture/流程图.svg)

## 环境

| 环境      | 版本 | Python模块    | 版本 |
| ---    | ---    | ---      | --- |
| Ubuntu | 16.04  | tensorflow | 1.8 |
| Anaconda | 5.1 | numpy|
| Python | 3.6 | pandas|
| Jupyter lab | 0.31.5 | matplotlib|

## 数据预处理

- 合并1到10月所有csv文件
- 构造训练数据集
- 对每一个地点的用户ID总数统计，构造标签列。

> 合并文件利用pandas读取每个文件，将每个文件赋值给一个DataFrame，最后利用`pd.concat()`合并成为一个DaraFrame写入文件。

合并的文件如下图所示,共252014行：

|地点|时间|人数|
|-|-|-|
|12|2017-11-28 12|11878|
|12|2017-11-20 12|11171|
|12|2017-11-23 12|10740|
|12|2017-11-21 12|10069|
|...|...|...|

## 提取特征

1. 提取已有的基本的特征
1. 手工构造特征

- 提取特征列利用pandas对时间特征的解析，分离出日、月、小时等特征列，

| 特征列 |building|cat|day|hour|is_weekend|	loc_id|	month|weekday|
| - | - | - | - | - | - | - | - | - |
|特征列含义|建筑物编号|建筑物类别|日|小时|是否周末|地点ID|月|星期|

## 选择模型
## 参数选择
## 超参选择
## 模型训练
## 模型评测
## 模型预测
## 其他常用linux命令
## For more information