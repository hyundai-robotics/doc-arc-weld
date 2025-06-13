# 2.2 arcoff

### Description

```arcoff``` command is used to stop Arc Welding. This command can be used in four different forms. However, commands not supported by the configured welder cannot be used.

<br/>

### Syntax

```python
arcoff
arcoff welder=<조건번호>, delay=<지연시간>
```  
<br/>


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| 조건번호 | 용접기를 2대 사용하는 경우 off시킬 용접기 번호를 설정합니다. (1 ~ 2) | Variable |
| 지연시간 | 용접기를 2대 사용하는 경우 off시킬 지연시간을 설정합니다. (0 ~ 2) | Variable |


### Example

```python
    arcoff                    #특별한 종료처리 없이 Arc 용접을 종료 함
    arcoff welder=2, delay=1  #2번째 용접기 아크를 1초 후 off 
```  
<br/>


### Details 

Refer to [[5. Editing Arc Welding Conditions]](../5_Condition_editing/README.md) 
