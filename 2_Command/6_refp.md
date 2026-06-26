# 2.6 refp

### Description

```refp``` 命令用于输入编织运动的参考点。它输入编织墙和进入方向等参考点。
<br/>

### Syntax

```python
refp <参考点编号>
refp <参考点编号>,<姿态(数量)>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **参考点编号** | 设置参考点类型的编号 (1 ~ 8) | Variable |
| **姿态** | 输入参考点的姿态 (但是，如果使用了隐藏姿态，它将被省略) | Variable |


### Example

```python
   refp 1,P1                   # 使用 P1 指定编织的墙面方向
   refp 1                      # 指定编织隐藏姿态的墙面方向
   refp 2, (-1073.33, 739.01, 258.30, 0, 76, 23)  # 指定编织表面的位置信息
```  

### Details
  参见 [[6. Weaving Function]](../6_Weaving_function/README.md)  


{% hint style="warning" %}
-	```refp``` 命令与 ```move``` 命令一样，属于步骤类别。
- 当使用用户键输入 ```refp``` 命令时，它将采用隐藏姿态的形式。
- 在将执行单元设置为 Cmd 或 Step 之后，您可以移动到教导的位置。  
{% endhint %}