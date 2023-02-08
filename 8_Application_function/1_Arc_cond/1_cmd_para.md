# 8.1.1 명령어 인자를 이용한 계단형 변경

명령어 인자에 다음과 같은 방식으로 계단형 변경 기능을 사용할 수 있습니다.


| 방식 | 사용 예시 |
| :--- | :--- |
| 전류, 전압 변경 |move L, spd=60%, …  <br>    move L, spd=10%, …   <span style="color: green"> ‘용접점 진입 스텝 </span> <br>    arcon cnd=1  <br>    move L, spd=40cm/min, ... <br>   <b>  arccond D, cur=175, vol=20 </b>  <span style="color: green"> ‘전류는 175A, 전압은 20V로 변경 </span> <br>   move L, spd=30cm/min, …  <br>    arcof <br>   end |
| 용접속도 및 위빙 파라미터 변경 | move L, spd=60%, …  <br>   move L, spd=10%, …    <span style="color: green"> ‘용접점 진입 스텝  </span> <br> weaving on, cnd=1 <br>   arcon cnd=1   move L, spd=40cm/min, … <br> <b>  arccond D, spd=80, rd=20, ld=10, freq=1.5, cur=175, vol=20 </b> <br> <span style="color: green">  ‘용접속도 80cm/min, 위빙폭 20, 10 mm, 주파수 1.5Hz, 전류175A, 전압20V로 변경 </span> <br>  move L, spd=30cm/min, …  <br>   weaving off <br>   arcof  <br> end |