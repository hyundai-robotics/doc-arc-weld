# 8.3.4 명령어를 이용한 위빙 및 아크 센싱 조건 설정

### (1) 기능 필요성

위빙과 아크 센싱 조건은 작업 중 자동으로 조건을 변경할 수 없습니다.
따라서 명령어를 이용하여 조건을 바꿔줄 수 있으며, 해당 위빙 구간에서만 요효합니다.


### (2) 명령어 사용 방법 

명령어를 삽입할 떄는 수동모드 상태에서 **[명령입력 > var_io > assignment]**를 입력한 후에, 왼쪽 변수로 커서를 움직여 **[시스템 변수 > arcweld > _weaving.파라미터]**를 선택하여 값을 입력하면 됩니다.  

입력된 명령어는 다음과 같은 형태가 됩니다: 
```_weaving.위빙 파라미터=입력값```  


- 예시)
```py
    weaving on, cnd=1	                # 위빙 명령문
    arcon cnd=1
    move L,S=5mm/s,accu=1,tool=2
    _weaving.right_distance = 4	        # 벽방향 거리를 명령어로 설정
    _weaving.left_distance = 3	        # 타방향 거리를 명령어로 설정
    MOVE L,S=5mm/s,A=1,T=2	            # 이구간부터 파라미터가 변경됨
```

각 명령어의 입력값은 조건 파일 내부의 조건설정 범위와 동일하게 제한됩니다.

명령어로 별도 지정되지 않은 파라미터는 weaving 명령어에서 설정한 조건을 사용합니다.

_weaving의 element 별로 설정값이 기능에 적용되는 지 여부는 다음 표와 같습니다.

| 변수명 | weaving 명령 직후 | 아크 센싱 없는 위빙 동작 | 아크 센싱 사용 위빙 동작 | 용접조건 연속변경 |
|-------|-------|-------|-------|-------|
| weave	| 적용	| 적용	| 적용	| 적용 |
| frequency	| 적용	| 적용	| 적용	| 적용 |
| left_distance	| 적용	| 적용	| 적용	| 적용 |
| right_distance	| 적용	| 적용	| 적용 | 적용 |
| angle | 적용	| 적용	| 적용	| 적용 |
| wall_direction | 적용	| 적용 | 적용	| 적용 |
| offset_angle | 적용	| 적용 | 적용	| 적용 |
| forward_angle | 적용	| 적용 | 적용	| 적용 |
| boundary_limit | 적용	| 적용 | 적용	| 적용 |
| segment_time_1 | 적용	| 적용 | 적용	| 적용 |
| segment_delay_1 | 적용	| 적용 | 적용	| 적용 |
| height_sensing_mode | 적용	| 해당 없음 | 적용 | 적용 |
| side_sensing_sensitivity | 적용	| 해당 없음 | 적용 | 적용 |
| height_sensing_sensitivity | 적용	| 해당 없음 | 적용 | 적용 |
| BaseCur	| 적용	| 해당 없음 | 적용 | 적용 |
| StickOut | 적용	| 해당 없음 | 적용 | 적용 |
| asymetric_sensing_ratio | 적용	| 해당 없음 | 적용 | 적용 |


### (3)	위빙 파라미터 명령어 종류 및 내용은 다음 링크를 참고해주세요.

[로봇언어 HRScript_weaving문](https://hrbook-hrc.web.app/#/view/doc-hrscript/ko/10-etc/3-sysvar/_weaving?cont_model=${cont_model})  
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
