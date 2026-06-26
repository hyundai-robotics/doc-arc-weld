# 3.2 详细内容

每个命令中按下 `属性` 按钮时出现的内容如下所示。

<style>
  table th,
  table td {
    text-align: left;
  }
</style>

<table>
  <thead>
    <tr>
      <th>项目</th>
      <th>内容</th>
      <th>详细</th>
      <th>备注</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>move</th>
      <td>记录的位置</td>
      <td>
        - 当前位置（机器人坐标系，基坐标系，轴坐标系，编码器等）<br>
        - X Y Z(mm) Rx Ry Rz(deg)<br>
        - 机器人配置
      </td>
      <td>指令值可修改</td>
    </tr>
    <tr>
      <th>赋值语句</th>
      <td>变量确认与更改</td>
      <td>
        根据变量类型监控该变量并更改值
      </td>
      <td></td>
    </tr>
    <tr>
      <th>arcon</th>
      <td>
        焊接条件确认与更改<br>
        - 焊接开始条件<br>
        - 焊接本条件<br>
        - 焊接辅助条件<br>
        - 焊接结束条件<br>
      </td>
      <td>
        - 焊接开始及本条件 <br>
        条件编号，说明，助焊剂代码，气体输出，电流/送进速度，焊接电压（补偿）/弧长度，WCR待机时间，机器人延迟时间，...<br><br>
        - 焊接辅助条件 <br>
        - 重试：次数，重试条件，动作模式，速度，收回时间，收回速度，后退/焊接线移动量，移位移动量<br>
        - 重启：次数，重启条件，重叠量，移动速度，焊接速度<br><br>
        - 焊接结束条件<br>
        - 电流比，下降斜率时间，条件保持时间，气体后输出，...<br>
        - 焊接辅助条件（进入结束条件）<br>
        - 自动焊接解除：次数，焊接解除条件，条件保持时间 <br>
      </td>
      <td></td>
    </tr>
    <tr>
      <th>weaving on</th>
      <td>
        挥动条件确认与更改
      </td>
      <td>
        条件编号，挥动形态，频率，基本模式，进角，边界限制，移动时间，计时器
      </td>
      <td></td>
    </tr>
    <tr>
      <th>refp</th>
      <td>
        参考点确认与更改
      </td>
      <td>
        当前位置，指令值<br>
        - X Y Z(mm) Rx Ry Rz(deg) 机器人配置
      </td>
      <td>
        指令值可修改<br>
        "位置"屏幕相同
      </td>
    </tr>
    <tr>
      <th>lvs</th>
      <td>
        LVS条件确认与更改
      </td>
      <td>
        功能设置
    - 条件编号，关节形状，动作模式，起点检测，焊接点寻找设置
  - 探测条件 
    - 探测量 [mm]，探测方向 (+tx, -tx)，探测速度 (mm/s)
      </td>
      <td></td>
    </tr>
    <tr>
      <th>heightsen</th>
      <td>
        高度感应条件确认与更改
      </td>
      <td>
        条件编号，Input data type for height sensing, Reference data setting method, ...
      </td>
      <td></td>
    </tr>
    <tr>
      <th>arccond</th>
      <td>
        焊接条件数据库
      </td>
      <td>
        由焊接速度、电流、电压、挥动宽度、挥动频率组成的数据库确认与编辑
      </td>
      <td></td>
    </tr>
    <tr>
      <th>touchsen</th>
      <td>
        触摸感应功能设置
      </td>
      <td>
        由焊接速度、电流、电压、挥动宽度、挥动频率组成的数据库确认与编辑
      </td>
      <td></td>
    </tr>
  </tbody>
</table>