# 2.15 calshift

### Description  

```calshift``` command calculates the shift using two Pose variables.
It is frequently used to calculate shifts based on pose variables saved from touch sensing.  
<br/>


### Syntax

```python
<Shift Val>=calshift(<Pose Val 1>, <Pose Val 2>)
<Shift Val>=calshift(<Pose Val 1>, <Pose Val 2>,"TV")
```  
<br/>


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Shift Variable Input** | Enter the shift variable to store the calculated shift | Shift Variable |
| **Pose Variable Input** | Enter the pose variable (1 ~ 9999) | Pose Variable |
| **TV** | Calculates the shift in the direction perpendicular to the tool (1 ~ 9999) | string |


### Example

```python
    move L, spd=30%, ...
    var pose_1 = cpo()
    move L, spd=30%, ...
    var pose_2 = cpo()
    var sft_1
    sft_1=calshift(pose_1,pose_2)   
    # calculate the vector shift between pose_1 and pose_2, and store the result in sht_1
```  
<br/>
  