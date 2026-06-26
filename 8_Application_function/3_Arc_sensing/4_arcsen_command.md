# 8.3.4 使用命令设置编织和弧传感条件

### (1) 功能的必要性

编织和弧传感条件在操作期间无法自动调整。 <br>
因此，可以使用命令修改条件，这些更改只对特定的编织部分有效。  

### (2) 使用命令的方法  

要插入命令，请在手动模式下输入 `[F6: cmd input] - var_io - assignment`。然后，将光标移至左侧变量并选择 `[F3: System Variables] - arcweld - _weaving.{parameter}`，在这里您可以输入所需的值。 <br>

输入的命令将以以下格式出现：  
```e.g. _weaving.frequency=2.0```  

- 示例)
```py
    weaving on, cnd=1	                # Weaving Command (cmd)
    arcon cnd=1
    move L,S=5mm/s,accu=1,tool=2
    _weaving.right_distance = 4	        # 使用命令设置墙壁方向距离
    _weaving.left_distance = 3	        # 使用命令设置墙壁方向距离
    MOVE L,S=5mm/s,A=1,T=2	            # 参数将从此部分开始修改
```

每个命令的输入值限制在条件文件定义的条件设置范围内。  
对于命令未明确指定的参数，将使用在编织命令中设置的条件。  

_weaving 的每个元素的设置对功能的适用性如下：  

<br>

| 变量名称 | 编织命令之后立即 | 没有弧传感的编织 | 具有弧传感的编织 | 持续变化焊接条件 |
|-------|-------|-------|-------|-------|
| weave | O | O | O | O |
| frequency | O | O | O | O |
| left_distance | O | O | O | O |
| right_distance | O | O | O | O |
| angle | O | O | O | O |
| wall_direction | O | O | O | O |
| offset_angle | O | O | O | O |
| forward_angle | O | O | O | O |
| boundary_limit | O | O | O | O |
| segment_time_1 | O | O | O | O |
| segment_delay_1 | O | O | O | O |
| height_sensing_mode | O | - | O | O |
| side_sensing_sensitivity | O | - | O | O |
| height_sensing_sensitivity | O | - | O | O |
| BaseCur | O | - | O | O |
| StickOut | O | - | O | O |
| asymetric_sensing_ratio | O | - | O | O |


<!-- ### (3) 编织参数命令种类及内容请参考以下链接。

[机器人语言 HRScript_weaving文](https://hrbook-hrc.web.app/#/view/doc-hrscript/ko/10-etc/3-sysvar/_weaving)   -->



<!-- 
(2)中说明的各参数种类和说明是 

weave: 编织模式

frequency: 编织频率

left_distance: 墙壁方向距离

right_distance: 另一方向距离

angle: 基本模式的角度

wall_direction: 基本模式的墙壁方向

forward_angle: 前进角度

boundary_limit: 是否使用边界限制

segment_time_1: 使用移动时间时各区间的时间

segment_delay_1: 使用移动时间时编织仅停止的时间

height_sensing_mode: 弧传感中上下传感执行方法

side_sensing_sensitivity: 左右方向弧传感敏感度

height_sensing_sensitivity: 上下方向弧传感敏感度

BaseCur: 上下传感基准电流

此值设置可用于设置焊炬和工件之间的距离。 
要使焊炬和工件之间的距离更远，请降低此值。 
相反，要使焊炬和工件更近，请提高此值。

StickOut: 在弧传感中上下方向移动焊炬的值。 输入的mm数量将改变焊炬高度。 输入正值时，焊炬和工件之间的距离变远，输入负值时，焊炬与工件之间的距离变近。

asymetric_sensing_ratio: 左右不对称传感比率

 -->