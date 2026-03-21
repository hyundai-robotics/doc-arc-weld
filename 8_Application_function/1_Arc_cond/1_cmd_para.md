# 8.1.1 使用命令因子的阶跃变化

阶跃变化功能可以在命令参数中使用，如下所示：

| 方法 | 示例 |
| :--- | :--- |
| 更改电流（IV、电压） |move L, spd=60%, ...<br/>move L, spd=10%, ...   <span style="color: green"> # 焊接点（缝）进入步骤 </span> <br>    arcon cnd=1  <br>    move L, spd=40cm/min, ... <br>   <b>  arccond D, cur=175, vol=20 </b>  <span style="color: green"> # 将电流更改为175A，电压更改为20V </span> <br>   move L, spd=30cm/min, ...  <br>    arcof <br>   end |
| 更改焊接速度和织造参数 | move L, spd=60%, ...  <br>   move L, spd=10%, ...    <span style="color: green"> # 焊接点（缝）进入步骤  </span> <br> weaving on, cnd=1 <br>   arcon cnd=1   move L, spd=40cm/min, ... <br> <b>  arccond D, spd=80, rd=20, ld=10, freq=1.5, cur=175, vol=20 </b> <br> <span style="color: green">  # 将焊接速度更改为80cm/min，织造宽度更改为20/10mm，频率更改为1.5HZ，电流更改为175A，电压更改为20V </span> <br>  move L, spd=30cm/min, ...  <br>   weaving off <br>   arcof  <br> end |