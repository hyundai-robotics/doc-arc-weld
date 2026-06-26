# 2.11 multipass

### Description  

```multipass``` 命令用于多次焊接，以重现弧感应路径。  
使用此命令时，您可以通过指定的偏移量重现原始弧焊路径来进行焊接。  
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
      <td>`保存 (save)`</td>
      <td>多次轨迹保存</td>
    </tr>
    <tr>
      <td>`load`</td>
      <td>多次轨迹加载</td>
    </tr>
    <tr>
      <td>` (off)`</td>
      <td>多次关闭</td>
    </tr>
    <tr>
      <td colspan="2">多次轨迹编号</td>
      <td> 用于保存/加载多次的轨迹编号 (1 ~ 50)</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">轨迹保存间隔距离</td>
      <td> 保存多次轨迹时的采样间隔距离 (5 ~ 100)[mm] </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">横向偏移距离</td>
      <td> 从原始弧感应路径向左/右方向的偏移距离 (-20 ~ 20)[mm] </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">纵向偏移距离</td>
      <td> 从原始弧感应路径向上/下方向的偏移距离 (-20 ~ 20)[mm] </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">多次运行方向</td>
      <td> 是否在反向重新生成路径 (0: 向前, 1: 反向) </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">焊枪偏移角度 (前/后)</td>
      <td> 在多次重现过程中，焊枪在前/后方向的倾斜角度偏移 (-20 ~ 20)[度] </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">焊枪偏移角度 (左/右)</td>
      <td> 在多次重现过程中，焊枪在左/右方向的倾斜角度偏移 (-20 ~ 20)[度] </td>
      <td>变量</td>
    </tr>
  </tbody>
</table>  

### Example

```python
     weaving on, cnd=1 
     multipass save, trj=1, period=10       # 保存在轨迹1中，每10mm间隔
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
     # 加载轨迹1，左偏移3mm，向上3mm，前进方向，无角度偏移
S15  move L,R2,spd=50%,accu=0,tool=1       # 移动到多次开始位置
     weaving on, cnd=11
     arcon cnd=1 
S16  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1  
S17  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
     arcoff
     weaving off  
     multipass off
```  