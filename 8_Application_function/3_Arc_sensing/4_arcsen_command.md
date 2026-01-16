# 8.3.4 Setting Weaving and Arc Sensing Conditions Using Commands

### (1) Necessity of Functionality

Weaving and arc sensing conditions cannot be automatically adjusted during operation. <br>
Therefore, the conditions can be modified using commands, and the changes will only be effective within the specific weaving section.  


### (2) Method of Using Commands  

To insert the command, enter `cmd input > var_io > assignment` while in manual mode. Then, move the cursor to the left variable and select `System Variables > arcweld > _weaving.`parameter``, where you can input the desired value.  <br>

The entered command will appear in the following format:  
```e.g. _weaving.frequency=2.0```  


- Example)
```py
    weaving on, cnd=1	                # Weaving Command (cmd)
    arcon cnd=1
    move L,S=5mm/s,accu=1,tool=2
    _weaving.right_distance = 4	        # Set the wall direction dist using a cmd
    _weaving.left_distance = 3	        # Set the wall direction dist using a cmd
    MOVE L,S=5mm/s,A=1,T=2	            # parameter will be modified starting from this section
```

The input values for each command are restricted within the range of condition settings defined in the condition file.  
For parameters that are not explicitly specified by the command, the conditions set in the weaving command will be used.  

The applicability of the settings for each element of _weaving to the functionality is as follows:  

<br>

| Variable Name | Immediately after Weaving Cmd | Weaving without Arc sensing | Weaving with Arc sensing | Continuous Change of Welding Conditions |
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


<!-- ### (3) 위빙 파라미터 명령어 종류 및 내용은 다음 링크를 참고해주세요.

[로봇언어 HRScript_weaving문](https://hrbook-hrc.web.app/#/view/doc-hrscript/ko/10-etc/3-sysvar/_weaving)   -->



<!-- 
(2)에서 설명한 각 파라미터 종류와 설명은 

weave: 위빙 패턴

frequency: 위빙 주파수

left_distance: 벽방향 거리

right_distance: 타방향 거리

angle: 기본패턴의 각도

wall_direction: 기본패턴의 벽방향

forward_angle: 진행각도

boundary_limit: 경계제한 사용 여부

segment_time_1: 이동시간 사용 시 각 구간의 시간

Dwesegment_delay_1: 이동시간 사용 시 위빙만 정지하는 시간

height_sensing_mode: 아크 센싱 중 상하센싱 실행방법

side_sensing_sensitivity: 좌우방향 아크 센싱 민감도

height_sensing_sensitivity: 상하방향 아크 센싱 민감도

BaseCur: 상하센싱 기준전류

이 값을 설정하여 토치와 모재간 거리를 설정할 수 있습니다. 
토치와 모재의 거리를 더 멀리 하려면 이 값을 낮추십시오. 
반대로 토치와 모재를 가까이 하려면 이 값을 높이십시오.

StickOut: 아크 센싱 중 상하방향으로 토치를 이동시키기 위한 값. 입력된 mm만큼 토치 높이가 변경됩니다. +값 입력 시 토치와 모재간 거리가 멀어지고 -값 입력 시 토치가 모재와 가까워 집니다.

asymetric_sensing_ratio: 좌우 비대칭 센싱 비율

 -->
