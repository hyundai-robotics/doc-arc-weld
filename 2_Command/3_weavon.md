# 2.3 weaving on


### Description
```weaving on``` command is used to enable the weaving condition. You can enter the properties window to set the corresponding weaving condition for the specified condition number.  
<br/>

### Syntax

```python
    weaving on, cnd=<Weaving Condition number>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Weaving Condition number** | Load the Weaving condition number (1 ~ 1000) | Variable |


### Example

```python  
   weaving on, cnd=1    # Load and execute weaving condition number 1
   arcon cnd=1          # Execute with arc condition number 1
   move L,spd=100cm/min,accu=0,tool=0   # Perform execution according to the above weaving conditions while moving the robot
```  


### Details  
  Refer to [[6. Weaving Function]](../6_Weaving_function/README.md)
