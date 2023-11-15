# 8.1.4 보간조건을 이용한 용접속도 및 위빙폭 변경 기능

이 기능은 위의 기능들과 별개인 기능입니다. 기준 gap에 따라 용접조건을 설정해 놓고, 실제 터치센싱으로 용접시점과 끝점의 gap을 계산하여 용접속도와 위빙폭을 자동으로 계산해주는 기능입니다.
```arccond``` 명령어의 속성창에서 “Gap correction” 항목 탭에 진입하면 조건별로 Gap에 따른 속도와 폭을 설정할 수 있습니다. 창분할에서 “아크보간”을 클릭하면 여기서 설정한 것을 그래프로 볼 수 있습니다.

<p align="center">
 <img src="../../_assets/8_3.png" width="70%"></img>
 <em><p align="center">그림 8.3 용접 조건(갭 보간) 대화상자</p></em>
</p> 

<p align="center">
 <img src="../../_assets/8_4.png" width="70%"></img>
 <em><p align="center">그림 8.4 아크보간 모니터링</p></em>
</p> 


<br>
이 기능의 동작은 다음과 같습니다.

 <p align="center">
 <img src="../../_assets/8_5.png" width="70%"></img>
 <em><p align="center">그림 8.5 용접 조건의 보간 동작</p></em>
</p> 

<br>
 

gap-속도 그래프로 예를 들어 보면 다음과 같습니다.
arccond 명령어의 속성창의 Gap correction 탭에 입력된 gap-Spd그래프를 생성합니다.
용접 시점에서는 WDB의 용접속도와 WDB의 기준 spd(그래프에서 기준 gap에서 spd값)에서의 속도의 차이를 dSpd라 할때, 현재 gap에서 원 그래프의 Spd 값에 dSpd를 적용한 값이 시작 Spd가 됩니다.
마찬가지로, 용접 종료점에서 WDB의 용접속도와 WDB의 기준 spd(그래프에서 기준 gap에서 spd값)에서의 속도차이를 dSpd2라 할때, 현재 gap에서 원 그래프의 Spd값에 dSpd2를 적용한 값이 종료 Spd가 됩니다.
위 그림과 같이 최종적으로 2개의 arccond 명령어 사이의 스텝에서 선형적으로 용접속도가 증가합니다.

JOB 구성예시는 다음과 같습니다.


```python
move L, spd=60%, …
move L, spd=10%, …	    #용접점 진입 스텝
arcon cnd=1
move L, spd=40cm/min, …
arccond L, cnd=1, gap=20  
move L, spd=30cm/min, …    #이 스텝에서 연속적으로 용접속도와 위빙폭이 선형변경된다.
arccond L, cnd=2, gap=10   
arcof
move L, spd=10%, …	    #용접점 탈출 스텝
end
```