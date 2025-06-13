# 2.3 weaving on


### Description
```weaving on``` command is used to enable the weaving condition. You can enter the properties window to set the corresponding weaving condition for the specified condition number.  
<br/>

### Syntax

```python
    weaving on, cnd=<Weaving Condition number>
```  
<br/>

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Weaving Condition number** | 불러올 위빙 조건 번호 (1 ~ 1000) | Variable |


### Example

```python  
   weaving on, cnd=1    # 위빙 조건 1번을 로딩하여 실행
   arcon cnd=1          # arcon 1번 조건으로 실행
   move L,spd=100cm/min,accu=0,tool=0   # 위의 위빙 조건대로 실행하며 로봇 이동
```  
<br/>


### Details  
  Refer to [[6. Weaving Function]](../6_Weaving_function/README.md)
