# 8.2	터치센싱 기능

용접 작업물은 지그 또는 포지셔너의 오차, 작업물의 취부오차 등이 다르기 때문에 항상 일정한 위치에 있다고 볼 수 없습니다. 
이러한 경우 터치센싱을 이용해 용접 시작점과 경유점, 끝점을 검출하여 용접할 수 있습니다.

터치센싱 기능은 작업물의 위치 및 용접시작점 혹은 용접끝점, 용접 경유점 검출을 통해 포즈를 얻는 기능입니다.

터치센싱을 이용하여 기준 위치를 기록해 놓으면 작업물이 들어왔을 때 기준위치에서 얼만큼 쉬프트 되어있는지 계산할 수 있습니다. 
마스터모드 기능을 사용하면 기준 티칭을 통해 마스터포즈를 저장해놓고 실제 기동시 터치센싱을 통해 쉬프트량을 자동으로 계산할 수 있습니다.

<p align="center">
 <img src="../../_assets/8_6.png"></img>
 <em><p align="center">그림 8.6 터치센싱의 예</p></em>
</p>

(1) 터치센싱 타입

 터치센싱은 그림 8.5와 같이 총 8가지 타입 (필렛, VGroove, Butt, LRCen, DetectGroove, Wall) 을 지원합니다. 
       
<p align="center">
 <img src="../../_assets/8_7.png" width="90%"></img>
 <em><p align="center">그림 8.7 터치센싱 타입</p></em>
</p>

(2) 터치센싱 명령어 및 설정 파라미터

터치센싱 명령어는 T.P화면에서 [명령입력]-[아크]-[touchsen]을 입력하여 기록할 수 있습니다.

터치센싱 명령어에서 [속성]을 누르면 그림 8.8와 같은 창에 진입합니다. 

탐색속도, 퇴피속도, 탐색거리, 진행거리, 오차보정량, 터치방식 등과 같은 조건들이 제어기에 저장됩니다. 

<p align="center">
 <img src="../../_assets/8_8.png" width="70%" ></img>
 <em><p align="center">그림 8.8 터치센싱 조건 편집화면</p></em>
</p>

- 명령어 구성
   - ```touchsen``` cnd=조건번호, crd=좌표계, dir=[탐색방향1, 탐색방향2, 탐색방향3], pose=결과포즈 저장변수, gap=butt gap 변수
   - ```touchsen``` cnd=조건번호, crd=좌표계, dir=[탐색방향1, 탐색방향2, 탐색방향3], rotation=탐색방향각도, pose=결과포즈 저장변수, gap=butt gap 변수
   - ```touchsen``` cnd=조건번호, crd=좌표계, dir=[탐색방향1, 탐색방향2, 탐색방향3], rotation=탐색방향각도, mpose=결과포즈 저장변수, mshift=계산된시프트 변수, gap=butt gap 변수

   - ```touchsen``` cnd=1, crd="robot", dir=[+x, -z], lift_up=3, pose=P10, gap=var_gap
      - 터치센싱 조건번호 (cnd) : cnd=1	
      - 터치센싱 좌표계 (crd) : "robot", "base", "tool", "tool_prj" 
      - 탐색방향 파라미터 (dir) : "+x", ["+x","-z"], [+tx, +tz], ["tf","td"],  
      - butt,groove 바닥 탐색 후 상승량 [mm] : lift_up=3		
      - detect groove 탐지기준거리 [mm] : criteria=5
      - 센싱 결과 포즈변수 : pose=var_po10
      - butt 하단 갭 변수 (소숫점 첫째 자리에서 반올림) : gap=var_gap 
      - touchsen 명령어의 속성창 설정항목 	: 탐색속도, 퇴피속도, 탐색거리, 진행거리, 오차보정량, 터치방식(접촉시, 접촉해제시)

센싱방향(dir)은 작업물 타입에 따라 다음과 같이 지정할 수 있습니다.

- Fillet	: 최소 1개 ~ 3개 지정
            +x, -x, +y, -y, +z, -z (crd="robot" 또는 "base")
            tf, td, tl, tr (crd="tool_prj")
            +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
- Butt 	: 1개 지정, 하강방향은 +tz 방향
          +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
- V Groove 	: 1개 지정, 하강방향은 +tz 방향
              +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
- LRCen 	: 1개 지정
            +x, -x, +y, -y, +z, -z (crd="robot" 또는 "base")
            +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
- DetectGroove: 2개 지정 (하강방향, 전진방향 순서)
                tf, td, tl, tr (crd="tool_prj")
                +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")

<center>

|타입|	최대탐색 </br>방향개수 |	직교XYZ </br>(모든타입 </br>지원예정)	| 툴좌표계|	툴프로젝션</br>좌표계 | 기타 입력인자 |
|:---:|	:---: |	:---:	| :---:|	:---: |:---:|
|Fillet|	3	|O|	O |	O	|	후퇴거리|
|Butt	|1 |	X	|O	|X	| 오차보정량 |
|VGroove |	1 |	X |	O	|X | |
|LRCen |	1	|O |	O	|X |  |	
|DetectGroove|	2 |	O |	O |	O | 진행거리1 </br> 후퇴거리1 </br> criteria |

</center>

(3) 터치센싱 명령어 작성 예제

1번 터치센싱조건 (명령어에서 [quick open]으로 사용자가 설정해놓은 조건들)에는 필렛, 2번 조건에는 버트, 3번 조건에는 V그루브로 작업물 타입이 지정되어있다고 가정할 때 예시는 아래와 같습니다. 

 ```python
   move L,spd=60%,accu=0,tool=0  # 터치센싱 위치로 accu 0으로 이동
   var P10=cpo() # 터치센싱 전 현재 포즈를 P10이라는 로컬변수에 저장
   touchsen cnd=1, crd="tool_prj", dir=["tf","td"], pose=P10       #1번 조건, 툴프로젝션 방향, 2점 터치
   touchsen cnd=1, crd="robot", dir=["+x","-y","-z"], pose=P10     #1번 조건, 로봇좌표 방향, 3점 터치
   touchsen cnd=1, crd="tool", dir="+tz", pose=P10           #1번 조건, 툴좌표 방향, +TZ방향으로 1점 터치 
   touchsen cnd=2, crd="tool", dir="+tx", lift_up=3, pose=P10, gap=var1 #2번 조건, 툴좌표계 방향, 바닥터치 후 3mm 상승
   touchsen cnd=3, crd="tool", dir="-ty", lift_up=5, pose=P10   #3번 조건, 툴좌표계 방향, 바닥터치 후 5mm 상승
 ```

</br>

---
(4) 센싱 타입 별 터치센싱 상세 설명

[1] Fillet 타입

<p align="center">
 <img src="../../_assets/8_9.png" width="60%"></img>
 <em><p align="center">그림 8.9 터치센싱 예 Fillet 타입</p></em>
</p>

- 명령어 작성 예시
```python
  touchsen cnd=1, crd="robot", dir=["+x","-y", "-z"], pose=P10
  touchsen cnd=1, crd="tool_prj", dir=["tf", "td"], pose=P10
  touchsen cnd=1, crd="tool", dir=["+tz"], pose=P10
```
- 1점 센싱 : 탐색방향을 한 개만 지정
- 2점 센싱 : 탐색방향을 순차적으로 2개 지정
- 3점 센싱 : 탐색방향을 순차적으로 3개 지정
- 툴 프로젝션 방식 (crd="tool_prj"): 사용 편리상 토치 자세를 기준으로 전진, 하강, 좌우 방향을 결정하는 방식
  tf(전진), td(하강), tl(좌), tr(우)로 방향을 지정할 수 있습니다. (tl=RotZ(90)*tf, tr=RotZ(-90)*tf 방향입니다)
- 작업물에 회전량(RX, RY, RZ)이 존재하는 틀어진 Fillet의 경우 각도지정 옵션을 이용해 탐색방향을 변경할 수 있습니다. 
  사용법은 메뉴얼 하단을 참고하십시오.



[2] V Groove 타입

<p align="center">
 <img src="../../_assets/8_10.png" width="70%"></img>
 <em><p align="center">그림 8.10 터치센싱 예 V Groove 타입</p></em>
</p>   




- 명령어 작성 예시
```python
  touchsen cnd=3, crd="tool", dir=[-ty], lift_up=3, pose=P10    #3번 조건, 툴좌표계 방향
```
- V그루브 타입은 Groove 형상의 작업물 센싱에 사용할 수 있습니다. 단, 센싱시작 전 툴자세는 위 그림과 유사하게 각의 2등분선 상에 위치하도록 티칭을 권장합니다.
- 방향인자는 좌우 시퀀스에 해당하는 방향으로 1가지 입니다. 하강 시퀀스 방향은 +tz 방향으로 고정됩니다.
- 안정적인 센싱을 위해 상승량(lift_up)은 최소 3mm이상 설정하는 것을 권장합니다.


 
[3] BUTT 타입

<p align="center">
 <img src="../../_assets/8_11.png" width="30%"></img>
 <em><p align="center">그림 8.11 터치센싱 예 Butt 타입</p></em>
</p>   


- 명령어 작성 예시
```python
    touchsen cnd=2, crd="tool", dir="+tx", lift_up=3, pose=P10, gap=var_gap   
    #2번 조건, 툴좌표계 방향, 바닥 센싱 후3mm 상승상승
```

- Butt 타입은 그림과 같이 센싱시작 전 툴 자세를 바닥면에 수직으로 티칭하는 것을 권장합니다.
- 방향인자는 좌우 시퀀스에 해당하는 방향으로 1가지 입니다. 하강 시퀀스 방향은 +tz 방향으로 고정됩니다.
-	센싱을 위해 바닥센싱 후 상승량(lift_up)은 최소 3mm이상 설정하는 것을 권장합니다. 상승량에 따라서 센싱한 gap의 크기가 바뀔 수 있습니다. 이 경우에는 명령어의 [속성] 창에 진입하여 오차보정량을 입력하면 이 값을 뺀 값으로 butt gap을 계산할 수 있습니다.


센싱 시퀀스는 다음과 같습니다. 

Fillet의 경우 dir에 입력된 순서대로 “전진->센싱 시작점 복귀” 를 반복하여 센싱 포즈를 계산합니다. 

Butt나 VGroove의 경우 아래와 같은 형태로 센싱이 진행됩니다. (상 좌우센싱 → 바닥센싱 → 상승 (lift_up 에 설정한 mm) → 하 좌우센싱)


<p align="center">
 <img src="../../_assets/8_12.png" width="60%"></img>
 <em><p align="center">그림 8.12 터치센싱 시퀀스 VGroove, Butt 타입</p></em>
</p>   

VGroove와 Butt의 경우 하단 좌우센싱 중점에서 작업물 방향으로 내린 점이 계산된 포즈가 됩니다. 

DetectGroove의 경우 하단센싱→상승량만큼 상승(후퇴거리 mm)→전진(진행거리 mm)을 반복합니다. 사용자가 지정한 탐지기준보다 더 내려갈 경우 하단센싱 중 멈추고 그 점이 계산된 포즈가 됩니다. 

(5) 터치센싱 조건

터치센싱 명령어에서 [속성]을 누르면 해당 조건번호에 대한 터치센싱 조건들을 편집할 수 있습니다.

- 탐색거리 : 탐색방향에 대한 거리[mm]이며 이 거리에 도달해도 작업물을 감지하지 못할 경우 에러가 발생합니다.  
- 탐색속도와 퇴피속도 : 탐색 또는 후퇴시 속도를 지정할 수 있습니다.  
- 오차보정량 : butt gap 보정시 사용됩니다. 
- 후퇴거리 : 필렛에선 처음 센싱 후 퇴피할 거리이고  DetectGroove 타입에서는 바닥을 찍고 들어올릴 거리입니다.  
- 센싱시점 : 접촉시와 접촉해제시를 지원합니다. 일반적으로 접촉시 센싱을 많이 사용하며 오차는 거의 없습니다. 
            만약 센싱시 와이어 휘어짐에 의한 미세오차까지도 고려해 센싱해야 하는 상황에서만 후퇴시 센싱을 사용하십시오.  

(6) 탐색방향 각도 변환

탐색방향에 대한 각도를 지정할 수 있습니다. Fillet과 DetectGroove 타입에서 지원합니다. 
명령어의 rotation 인자에 "X30", "Y-30", "TL20" 등과 같이 입력합니다.
각도지정은 TL축과 베이스 XYZ축 중 한가지 축으로 센싱각도만큼 센싱시퀀스 이동궤적을 모두 회전시킵니다. 
그림 8.13은 필렛과 DetectGroove작업물에서 Y축 또는 TL축으로 30도 회전한 예입니다.

<p align="center">
 <img src="../../_assets/8_13.png" width="300"></img>
 <em><p align="center">그림 8.13 터치센싱 예 각도설정</p></em>
</p>       

- 명령어 작성 예시

```python
   touchsen cnd=1, crd="robot", dir=["+x","-z"], rotation="Y30", pose=P100
   touchsen cnd=1, crd="robot", dir=["+x","-z"], rotation="TL30", pose=P100
   touchsen cnd=2, crd="tool_prj", dir=["td","tf"], lift_up=5, rotation="Y-30", pose=P100
   touchsen cnd=2, crd="tool_prj", dir=["td","tf"], rotation="TL-30", pose=P100   #DetectGroove
```

작업물 타입과 명령어에 지정된 센싱방향 지정좌표계에 따라 지정이 가능한 각도회전 축은 아래 표와 같습니다.

<center>

| 타입	| 센싱방향 </br> 지정좌표계	| 각도지정축|
|:---:|:---:|:---:|
|Fillet	| 모든 좌표계	| 직교 XYZ축 </br>TL축 |
|Detect Groove |	툴 (crd="tool") </br> 툴 프로젝션 (crd="tool_prj") |	직교 XYZ축</br>TL축 |

</center>


Master/Execution Mode 터치센싱 기능

Master 모드는 사용자키에서 On/Off 할 수 있습니다.
마스터 모드를 On한 상태에서 터치센싱을 하면 마스터 포즈를 저장할 수 있으며, 이를 기준 티칭으로 사용합니다. 실제 작업시에는 마스터모드를 Off하고 터치센싱을 수행하게 되는데 이때에는 마스터 포즈대비 현재 센싱 포즈로 작업물이 쉬프트된 양을 자동으로 계산해 줍니다.

Master 모드에선 사용자가 터치센싱 명령어의 mpose 입력인자에 지정한 변수에 센싱한 포즈가 저장되며, Execution 모드 (Master 모드 off)에선 현재 센싱한 포즈를 Master 모드에서 센싱했던 포즈와 비교하여 쉬프트량을 계산하고 사용자가 mshift 입력인자에 지정한 변수에 시프트량이 기록됩니다.

- 명령어 작성 예시
```python
   var P10=cpo()
   var sft_var1=Shift(0,0,0,0,0,0,"base")
   ....
   touchsen cnd=1, crd="robot", dir=["+x","-z"], mpose=P10, mshift=sft_var1
```
위 명령어는 Master 모드에서 P10포즈변수에 센싱한 포즈가 저장되고 Execution 모드에서 센싱했을 때 Master 모드와의 시프트 양이 자동으로 계산되어 sft_var1변수에 저장됩니다.
