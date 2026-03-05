# 2.14 stitch

### Description 

```stitch``` command performs stitch welding. You can set the stitch conditions by placing the cursor on the command and clicking the **Properties** button.
After moving to the desired stitch welding position using a `move` command, use stitch together with the `arcon` command.
When the stitch function is executed, stitch welding starts at the specified position and continues until the stitch operation is completed.  
<br/>

### Syntax

```python
stitch on, cnd=<Condition Number>
stitch off
```  


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Condition number** | Stitch Condition Number (1 ~ 1000) | Variable |


### Example
```python
   stitch on, cnd=2         #  execute stitch on condition 2
   stitch off               #  terminate stitch
```


### Details  
  Refer to [[8.6 STITCH Function]](../8_Application_function/6_Stitch/README.md)
