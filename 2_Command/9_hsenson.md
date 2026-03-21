# 2.9 启动高度传感

### 描述 

```heightsen on``` 命令启动高度传感功能（AVC, 弧长控制）。  


### 语法
```python
    heightsen on, cnd=<Condition Number>
```  

### 参数

| 项目 | 释义 | 备注 |
| --- | --- | --- |
| **条件编号** | 用于启动弧焊的焊接条件编号和具体条件（1 ~ 8） | 变量 |


### 示例

```python   
    heightsen on, cnd=1        # 使用条件编号1启动高度传感。
```  


### 详细信息
  请参考 [[8.4 高度传感]](../8_Application_function/4_Height_sensing/README.md)