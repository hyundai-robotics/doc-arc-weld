# 2.3 编织开启

### 描述
```weaving on``` 命令用于启用编织条件。您可以进入属性窗口，为指定的条件编号设置相应的编织条件。  
<br/>

### 语法

```python
    weaving on, cnd=<Weaving Condition number>
```  

### 参数

| 项目 | 含义 | 备注 |
| --- | --- | --- |
| **编织条件编号** | 加载编织条件编号 (1 ~ 1000) | 变量 |


### 示例

```python  
   weaving on, cnd=1    # 加载并执行编织条件编号 1
   arcon cnd=1          # 用弧形条件编号 1 执行
   move L,spd=100cm/min,accu=0,tool=0   # 在移动机器人时，根据以上编织条件执行
```  


### 详情  
  请参阅 [[6. 编织功能]](../6_Weaving_function/README.md)