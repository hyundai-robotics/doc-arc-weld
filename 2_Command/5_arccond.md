# 2.5 arccond


### Description

```arccond``` 命令用于使用焊接数据库 (DB) 配置作业，或使用焊接数据库持续更改焊接条件。  
<br/>

### Syntax

```python
arccond <Interpolation type>, cnd=<Condition Number>, gap=<Gap>, spd=<Welding Speed>, rd=<Wall Direction(right distance)>, ld=<Cross Direction(left distance)>, freq=<Weaving Frequency>, cur=<Current>, vol=<Voltage>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Interpolation Type** | 插值条件设置 (D: 立即更改, L: 线性插值更改)| Character |
| **Condition Number**| 存储焊接数据库 (WDB) 和插值条件的条件编号 (1 ~ 1000) | Variable  |
| **Gap** | 输入的间隙值 (-1 ~ 1000) [mm]| Variable  |
| **Welding Speed**| 立即更改的焊接速度 (1 ~ 1000) [cm/min]| Variable  |
| **Wall Direction**  | 立即更改的编织墙面方向宽度 (1 ~ 50) [mm]| Variable  |
| **Cross Direction** | 立即更改的编织交叉方向宽度 (1 ~ 50) [mm]  | Variable  |
| **Weaving Frequency**  | 立即更改的编织频率 (1 ~ 10) [Hz]  | Variable  |
| **Current**| 立即更改的焊接电流  (范围因焊机设置而异)| Variable  |
| **Voltage**| 立即更改的焊接电压  (范围因焊机设置而异)| Variable  |


### Example

```python
  	arccond D, cur=170, vol=10 # 用170A电流和10V电压立即更改
  	arccond D, spd=80, rd=20, ld=20, freq=1.5 # 用80cm/min的焊接速度、20mm的编织宽度和1.5Hz的频率立即更改
  	arccond D, cnd=1 # 立即更改到条件编号1
  
  	arccond L, cnd=1  
    ...               # 焊接步骤 (焊接区域的移动命令)
    arccond L, cnd=2  # 使用WDB数据通过线性插值从条件1连续更改到条件2
```  

### Details  

  Refer to [[8.1 Arccond - Arc Weld Condition]](../8_Application_function/1_Arc_cond/README.md)