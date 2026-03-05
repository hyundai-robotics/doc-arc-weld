# 2.11 multipass

### Description  

```multipass``` command is used for multi-pass welding to reproduce the arc sensing path.  
Using this command, you can perform welding by reproducing the original arc welding path with a specified amount of shift.  
<br/>


### Syntax

```python  
multipass save, trj=<Multi-pass trajectory Number>, period=<trajectory save interval distance>
multipass load, trj=<Multi-pass trajectory Number>, side=<lateral shift distance>, height=<vertical shift distance>, reverse=<Multi-pass run direction>, tas=<torch shift angle (front/rear)>, was=<torch shift angle(left/right)>
multipass off
```  

### Parameter
<table>
  <thead>
    <tr>
      <th>Major Category</th>
      <th>Sub Category</th>
      <th>Meaning</th>
      <th>Remarks</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="4">multipass</td>
    </tr>
    <tr>
      <td>save</td>
      <td>Multi-pass trajectory save</td>
    </tr>
    <tr>
      <td>load</td>
      <td>Multi-pass trajectory load</td>
    </tr>
    <tr>
      <td>off</td>
      <td>Multi-pass off</td>
    </tr>
    <tr>
      <td colspan="2">Multi-pass trajectory Number</td>
      <td> Trajectory Number to save/load the multi-pass (1 ~ 50)</td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">trajectory save interval distance</td>
      <td> Sampling interval distance when saving the multi-pass trajectory (5 ~ 100)[mm] </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">lateral shift distance</td>
      <td> Shift distance in the left/right direction from the origin Arc sensing path (-20 ~ 20)[mm] </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">vertical shift distance</td>
      <td> Shift distance in the up/down direction from the origin Arc sensing path (-20 ~ 20)[mm] </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">Multi-pass run direction</td>
      <td> Whether to reproduce the path in the reverse direction (0: forward, 1: reverse) </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">torch shift angle (front/rear)</td>
      <td> Torch tilt angle shift in the front/rear direction during multi-pass reproduction (-20 ~ 20)[deg] </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">torch shift angle (left/right)</td>
      <td> Torch tilt angle shift in the left/right direction during multi-pass reproduction (-20 ~ 20)[deg] </td>
      <td>Variable</td>
    </tr>
  </tbody>
</table>  

### Example

```python
     weaving on, cnd=1 
     multipass save, trj=1, period=10       # Save to trajectory 1 at 10mm intervals
     arcon cnd=1
S10  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
S11  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
     arcoff
     weaving off
     multipass off
S12  move L,spd=50%,accu=3,tool=1
S13  move L,spd=50%,accu=3,tool=1
S14  move L,spd=50%,accu=3,tool=1
     multipass load,trj=1,side=3,height=3,reverse=0,tas=0,was=0
     # Load trajectory 1 with a 3mm shift to the left, 3mm upward, in forward direction, with no angle shift
S15  move L,R2,spd=50%,accu=0,tool=1       # Move step to the Multi-pass starting position
     weaving on, cnd=11
     arcon cnd=1 
S16  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1  
S17  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
     arcoff
     weaving off  
     multipass off
```  
