# 2.1 arcon


### Description

```arcon``` 命令用于启动弧焊过程。此命令可以以4种不同的形式使用。然而，未被配置焊机支持的命令不能被使用。
<br/>

### Syntax
  
```python
arcon
arcon cnd=<Condition Number> 
arcon cnd=<Condition Number>,job=<Job Number of the Welder>,cur=<Current>,vol=<Voltage>, vol_offset=<Voltage Offset>
arcon cnd=<Condition Number>,job=<Job Number of the Welder>  
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Arc Welding Condition Number** | 用于启动弧焊的焊接条件编号以及特定条件（1~100） | Variable |
| **Job Number of the Welder** | 存储在焊机中的作业编号（仅适用于支持作业模式的焊机）（0 ~ 9999） | Variable |
| **Current** | 弧焊的输出电流值（0 ~ 500）[A] | Variable |
| **Voltage** | 弧焊的输出电压值（20 ~ 40）[V] | Variable |
| **Voltage Offset** | 弧焊过程中协同电压的电压偏移值（-200 ~ 200）[V] | Variable |


### Example

```python
   arcon  # 使用先前设置的焊接条件启动焊接。不会执行重试或重启。
   arcon cnd=1  # 根据指定的焊接启动条件启动焊接（cnd=1）
   arcon cnd=1,cur=200,vol=22  # 使用指定的电流和电压（200A, 22V）启动焊接，同时其他焊接条件遵循指定焊接启动条件编号（cnd=1）的设置
   arcon cnd=1,job=5 # 在作业模式下启动焊接，使用作业编号5。其他焊接条件遵循指定焊接启动条件编号（cnd=1）的设置
```  

### Details  

请参阅 [[5. Editing Arc Welding Conditions]](../5_Condition_editing/README.md) 
<br/>


{% hint style="warning" %}
[Caution]
 - 某些焊机型号可以将各种焊接设置作为作业内部存储。在这种情况下，您可以使用“焊机的作业编号”项目。
{% endhint %}