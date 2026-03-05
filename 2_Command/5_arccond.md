# 2.5 arccond


### Description

```arccond``` command is used to configure a job using the welding database(DB), or to continuously change welding conditions using the welding DB.  
<br/>

### Syntax

```python
arccond <Interpolation type>, cnd=<Condition Number>, gap=<Gap>, spd=<Welding Speed>, rd=<Wall Direction(right distance)>, ld=<Cross Direction(left distance)>, freq=<Weaving Frequency>, cur=<Current>, vol=<Voltage>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Interpolation Type** | Interpolation condition setting (D: Immediate change, L: Linear interpolation change)| Character |
| **Condition Number**| The condition number that stores the welding DB (WDB) and interpolation conditions (1 ~ 1000) | Variable  |
| **Gap** | The gap value to be input (-1 ~ 1000) [mm]| Variable  |
| **Welding Speed**| Welding speed for immediate change (1 ~ 1000) [cm/min]| Variable  |
| **Wall Direction**  | Weaving wall direction width for immediate change (1 ~ 50) [mm]| Variable  |
| **Cross Direction** | Weaving cross direction width for immediate change (1 ~ 50) [mm]  | Variable  |
| **Weaving Frequency**  | Weaving frequency for immediate change (1 ~ 10) [Hz]  | Variable  |
| **Current**| Welding current for immediate change (1 ~ 1000) [A]| Variable  |
| **Voltage**| Welding voltage for immediate change (1 ~ 200) [V] | Variable  |


### Example

```python
  	arccond D, cur=170, vol=10 # Change immediately with a current of 170A and a voltage of 10V
  	arccond D, spd=80, rd=20, ld=20, freq=1.5 # Change immediately with a welding speed 80cm/min, weaving width of 20mm, and frequency of 1.5Hz
  	arccond D, cnd=1 # Change immediatelyto condition number 1
  
  	arccond L, cnd=1  
    ...               # welding step (move command for welding section)
    arccond L, cnd=2  # Change continuously from condition 1 to condition 2 using WDB data with linear interpolation
```  

### Details  

  Refer to [[8.1 Arccond - Arc Weld Condition]](../8_Application_function/1_Arc_cond/README.md)