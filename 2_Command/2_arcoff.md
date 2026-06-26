# 2.2 arcoff

### 描述

```arcoff``` 命令用于停止弧焊。此命令可以使用两种不同形式。然而，配置的焊机不支持的命令无法使用。

<br/>

### 语法

```python
arcoff
arcoff welder=<Condition Number>, delay=<Delay Time>
```  


### 参数

| 项目 | 意义 | 备注 |
| --- | --- | --- |
| Condition Number | 使用两个焊机时，设置要关闭的焊机编号。（1 ~ 2） | 变量 |
| Delay Time | 使用两个焊机时，设置关闭的延迟时间。（1 ~ 2） | 变量 |


### 示例

```python
    arcoff                    # 在没有任何特殊关闭过程的情况下终止弧焊
    arcoff welder=2, delay=1  # 在1秒延迟后关闭第二台焊机的弧。
```  


### 详细信息 

请参阅 [[5. 编辑弧焊条件]](../5_Condition_editing/README.md) 