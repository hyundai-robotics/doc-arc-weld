# 2.1 arcon


### Description

```arcon``` command is used to start the Arc Welding process. This command can be used in four different forms. However, commands not supported by the configured welder cannot be used.
<br/>

### Syntax
  
```python
arcon
arcon cnd=<Condition Number> 
arcon cnd=<Condition Number>,job=<Job Number of the Welder>,cur=<Current>,vol=<Voltage>, vol_offset=<Voltage Offset>
arcon cnd=<Condition Number>,job=<Job Number of the Welder>  
```  
<br/>

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Arc Welding Condition Number** | The number of the welding condition used to starting Arc Welding and the specific condition (1~100) | Variable |
| **Job Number of the Welder** | The Job number stored in the welder to be used(only for welders supporting job mode) (0 ~ 9999) | Variable |
| **Current** | The output current value for Arc Welding (0 ~ 500)[A] | Variable |
| **Voltage** | The output voltage value for Arc Welding (20 ~ 40)[V] | Variable |
| **Voltage Offset** | The voltage offset value for the synergic voltage during Arc Welding (-200 ~ 200)[V] | Variable |


### Example

```python
   arcon  # Starts Welding using the previously set welding conditions. Retry or Restart is not executed.
   arcon cnd=1  # Starts welding according to the specified welding start condition(cnd=1)
   arcon cnd=1,cur=200,vol=22  # Starts welding with the specified current and voltage(200A, 22V), while other welding conditions follow the settings of the specified welding start condition number(cnd=1)
   arcon cnd=1,job=5 # Starts welding in Job mode, using Job number 5. Other welding conditions follow the settings of the specified welding start condition number(cnd=1)
```  
<br/>

### Details  

Refer to [[5. Editing Arc Welding Conditions]](../5_Condition_editing/README.md) 
<br/>


{% hint style="warning" %}
[**Caution**]  
 - Some welder models can store various welding settings as jobs internally. In this case, you can use 'Job number of the Welder' item.
{% endhint %}