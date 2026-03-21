# 2.1 arcon

### 描述

```arcon``` 命令用于启动弧焊过程。此命令可以以 4 种不同形式使用。但是，配置的焊机不支持的命令无法使用。
<br/>

### 语法

```python
arcon
arcon cnd=<Condition Number> 
arcon cnd=<Condition Number>,job=<Job Number of the Welder>,cur=<Current>,vol=<Voltage>, vol_offset=<Voltage Offset>
arcon cnd=<Condition Number>,job=<Job Number of the Welder>  
```  

### 参数

| 项目 | 说明 | 备注 |
| --- | --- | --- |
| **弧焊条件编号** | 启动弧焊所用的焊接条件编号以及特定条件 (1~100) | 可变 |
| **焊机的作业编号** | 存储在焊机中的作业编号(仅适用于支持作业模式的焊机) (0 ~ 9999) | 可变 |
| **电流** | 弧焊的输出电流值 (0 ~ 500)[A] | 可变 |
| **电压** | 弧焊的输出电压值 (20 ~ 40)[V] | 可变 |
| **电压偏移** | 弧焊期间协同电压的电压偏移值 (-200 ~ 200)[V] | 可变 |

### 示例

```python
   arcon  # 使用先前设置的焊接条件开始焊接。未执行重试或重启。
   arcon cnd=1  # 根据指定的焊接启动条件(cnd=1)开始焊接
   arcon cnd=1,cur=200,vol=22  # 使用指定的电流和电压(200A, 22V)开始焊接，其他焊接条件遵循指定焊接启动条件编号(cnd=1)的设置
   arcon cnd=1,job=5 # 在作业模式下开始焊接，使用作业编号 5。其他焊接条件遵循指定焊接启动条件编号(cnd=1)的设置
```  

### 详细信息  

请参阅 [[5. 编辑弧焊条件]](../5_Condition_editing/README.md) 
<br/>

{% hint style="warning" %}
[注意]
 - 一些焊机模型可以内部存储各种焊接设置作为作业。在这种情况下，您可以使用“焊机的作业编号”项目。
{% endhint %}