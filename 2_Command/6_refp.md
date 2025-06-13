# 2.6 refp

### Description

```refp``` command is used to input reference points for the weaving motion. It inputs reference points such as weaving wall and entry direction.
<br/>

### Syntax

```python
refp <Reference Point Number>
refp <Reference Point Number>,<Pose(Num)>
```  
<br/>

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Reference Point Number** | Set the number for the type of reference points (1 ~ 8) | Variable |
| **Pose** | Input the pose of the reference points (However, if a hidden pose is used, it will be omitted) | Variable |


### Example

```python
   refp 1,P1                   # Specify the wall direction of the weaving using P1
   refp 1                      # Specify the wall direction of the weaving hidden pose
   refp 2, (-1073.33, 739.01, 258.30, 0, 76, 23)  # Specify the position of the weaving surface
```  
<br/>

### Details
  Refer to [[6. Weaving Function]](../6_Weaving_function/README.md)  
<br/>  
<br/>


{% hint style="warning" %}
-	```refp``` command, likes ```move``` command, belongs to the step category.
- When the ```refp``` command is entered using a user key, it takes the form of a hidden pose.
- After setting the execution unit to Cmd or Step, you can move to the taught position.  
{% endhint %}