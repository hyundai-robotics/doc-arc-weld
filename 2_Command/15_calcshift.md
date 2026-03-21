# 2.15 calshift

### 描述  

```calshift``` 命令使用两个姿态变量来计算移位。
它通常用于基于从触觉传感保存的姿态变量计算移位。  
<br/>

### 语法

```python
<Shift Val>=calshift(<Pose Val 1>, <Pose Val 2>)
<Shift Val>=calshift(<Pose Val 1>, <Pose Val 2>,"TV")
```  

### 参数

| 项目 | 释义 | 备注 |
| --- | --- | --- |
| **移位变量输入** | 输入要存储计算移位的移位变量 | 移位变量 |
| **姿态变量输入** | 输入姿态变量 (1 ~ 9999) | 姿态变量 |
| **TV** | 计算与工具垂直方向的移位 (1 ~ 9999) | 字符串 |

### 示例

```python
    move L, spd=30%, ...
    var pose_1 = cpo()
    move L, spd=30%, ...
    var pose_2 = cpo()
    var sft_1
    sft_1=calshift(pose_1,pose_2)   
    # 计算 pose_1 和 pose_2 之间的向量移位，并将结果存储在 sht_1 中
```  