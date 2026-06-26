# 2.9 heightsen on

### Description 

```heightsen on``` 命令启动高度感应功能（AVC，弧长控制）。  


### Syntax
```python
    heightsen on, cnd=<Condition Number>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Condition Number** | 用于开始弧焊的焊接条件的编号和特定条件 (1 ~ 8) | Variable |


### Example

```python   
    heightsen on, cnd=1        # 使用条件编号 1 启动高度感应。
```  


### Details
  请参阅 [[8.4 Height Sensing]](../8_Application_function/4_Height_sensing/README.md)