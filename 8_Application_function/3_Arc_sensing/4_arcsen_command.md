# 8.3.4 使用命令设置编织和弧感应条件

### (1) 功能的必要性

在操作过程中，编织和弧感应条件无法自动调整。<br>
因此，可以使用命令修改条件，变化仅在特定的编织部分有效。  

### (2) 使用命令的方法  

在手动模式下，输入 `[F6: cmd input] - var_io - assignment`以插入命令。然后，将光标移到左侧变量并选择`[F3: System Variables] - arcweld - _weaving.{parameter}`，在这里可以输入所需的值。<br>

输入的命令将以以下格式出现：  
```e.g. _weaving.frequency=2.0```  

- 示例)
```py
    weaving on, cnd=1	                # 编织命令 (cmd)
    arcon cnd=1
    move L,S=5mm/s,accu=1,tool=2
    _weaving.right_distance = 4	        # 使用命令设置墙面方向距离
    _weaving.left_distance = 3	        # 使用命令设置墙面方向距离
    MOVE L,S=5mm/s,A=1,T=2	            # 参数将从该部分开始修改
```

每个命令的输入值限制在条件文件中定义的条件设置范围内。  
对于命令未明确指定的参数，将使用编织命令中设置的条件。  

每个元素的 _weaving 设置对功能的适用性如下：  

<br>

| 变量名称 | 编织命令后立即调整 | 无弧感应的编织 | 有弧感应的编织 | 焊接条件的连续变化 |
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
(2) 中说明的各参数种类及说明 

weave: 编织模式

frequency: 编织频率

left_distance: 墙面方向距离

right_distance: 另一方向距离

angle: 基本模式的角度

wall_direction: 基本模式的墙面方向

forward_angle: 前进角度

boundary_limit: 边界限制使用情况

segment_time_1: 移动时间使用时各段的时间

segment_delay_1: 移动时间使用时编织仅停止的时间

height_sensing_mode: 弧感应中上下感应执行方法

side_sensing_sensitivity: 左右方向弧感应灵敏度

height_sensing_sensitivity: 上下方向弧感应灵敏度

BaseCur: 上下感应基准电流

通过设置此值，可以确定焊枪与工件之间的距离。 
要使焊枪与工件之间的距离更远，请降低此值。 
反之，要使焊枪与工件更近，请提高此值。

StickOut: 为在弧感应期间上下移动焊枪而设置的值。 输入的mm数量将改变焊枪的高度。 输入正值时，焊枪与工件之间的距离增加，而输入负值时，焊枪与工件的距离减小。

asymetric_sensing_ratio: 左右不对称感应比例

 -->
