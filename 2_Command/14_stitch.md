﻿# 2.14 stitch

- 설명 
    
    stitch 문은 스티치 용접을 수행하는 명령어 입니다. 퀵 오픈창으로 스티치 조건을 설정할 수 있으며 이 정보들은 ROBOT.STC에 저장됩니다. 스티치 용접을 하려는 위치로 ```move``` 수행하고 ```arc on```문과 함께 사용해야 하며 스티치 기능을 수행하면 해당 위치에서 스티치 용접을 시작하며,  스티치 기능이 종료 되는 지점까지 스티치 용접을 진행 합니다.


- 문법
  
    - stitch on#=<조건번호>
    - stitch off

- 파라미터
  
   ① 조건번호
     - 내용 : 스티치 조건 번호 
     - 범위 : 1 ~ 20
   
</br>  

- 사용 예
  
   - ```stitch on#=2```  <span style="color: green">#  스티치 2번 조건 실행</span>
   - ```stitch off ```   <span style="color: green">#  스티치 기능 종료</span>
