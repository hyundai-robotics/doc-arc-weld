# 2.11 多重通道

### 描述  

```multipass``` 命令用于多重通道焊接，以重现电弧感应路径。  
使用此命令，您可以通过指定的位移量重现原始的电弧焊接路径进行焊接。  
<br/>

### 语法

```python  
multipass save, trj=<多重通道轨迹编号>, period=<轨迹保存间隔距离>
multipass load, trj=<多重通道轨迹编号>, side=<横向位移距离>, height=<纵向位移距离>, reverse=<多重通道运行方向>, tas=<火炬位移角度（前/后）>, was=<火炬位移角度（左/右）>
multipass off
```  

### 参数
<table>
  <thead>
    <tr>
      <th>主要类别</th>
      <th>子类别</th>
      <th>含义</th>
      <th>备注</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="4">multipass</td>
    </tr>
    <tr>
      <td>`保存 (save)`</td>
      <td>多重通道轨迹保存</td>
    </tr>
    <tr>
      <td>`load`</td>
      <td>多重通道轨迹加载</td>
    </tr>
    <tr>
      <td>` (off)`</td>
      <td>多重通道关闭</td>
    </tr>
    <tr>
      <td colspan="2">多重通道轨迹编号</td>
      <td>保存/加载多重通道的轨迹编号（1 ~ 50）</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">轨迹保存间隔距离</td>
      <td>保存多重通道轨迹时的采样间隔距离（5 ~ 100）[mm]</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">横向位移距离</td>
      <td>从原点电弧感应路径的左右方向位移距离（-20 ~ 20）[mm]</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">纵向位移距离</td>
      <td>从原点电弧感应路径的上下方向位移距离（-20 ~ 20）[mm]</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">多重通道运行方向</td>
      <td>是否以反方向重现路径（0：前进，1：反向）</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">火炬位移角度（前/后）</td>
      <td>在多重通道重现过程中，火炬在前/后方向的倾斜角度位移（-20 ~ 20）[度]</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">火炬位移角度（左/右）</td>
      <td>在多重通道重现过程中，火炬在左右方向的倾斜角度位移（-20 ~ 20）[度]</td>
      <td>变量</td>
    </tr>
  </tbody>
</table>  

### 示例

```python
     weaving on, cnd=1 
     multipass save, trj=1, period=10       # 以10mm的间隔保存到轨迹1
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
     # 加载轨迹1，左移3mm，向上3mm，前进方向，无角度位移
S15  move L,R2,spd=50%,accu=0,tool=1       # 移动到多重通道起始位置
     weaving on, cnd=11
     arcon cnd=1 
S16  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1  
S17  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
     arcoff
     weaving off  
     multipass off
```  
