# 2.2 arcoff

### Description

```arcoff``` command is used to stop Arc Welding. This command can be used in 2 different forms. However, commands not supported by the configured welder cannot be used.

<br/>

### Syntax

```python
arcoff
arcoff welder=<Condition Number>, delay=<Delay Time>
```  
<br/>


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| Condition Number | When using two welders, set the welder number to be turned off. (1 ~ 2) | Variable |
| Delay Time | When using two welders, set the delay time to be turned off. (1 ~ 2) | Variable |


### Example

```python
    arcoff                    # Terminate the arc welding without any special shutdown process
    arcoff welder=2, delay=1  # Trun off the arc of the 2nd welder after a 1-second delay.
```  
<br/>


### Details 

Refer to [[5. Editing Arc Welding Conditions]](../5_Condition_editing/README.md) 
