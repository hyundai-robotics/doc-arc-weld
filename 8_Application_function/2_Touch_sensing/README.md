# 8.2	터치센싱 기능

터치센싱이란 작업물의 위치 및 용접시작점 혹은 용접끝점 검출을 위해 사용하는 기능입니다.

<p align="center">
 <img src="../../_assets/8_6.png"></img>
 <em><p align="center">그림 8.6 터치센싱의 예</p></em>
</p>


작업물은 지그 또는 포지셔너의 오차, 작업물의 갭들이 다르기 때문에 항상 일정한 위치에 있다고 볼 수 없습니다. 이러한 경우 터치센싱을 이용해 용접 시작점과 용접 끝점을 검출하여 용접할 수 있습니다. 또는 터치센싱을 이용하여 기준 위치를 기록해 놓으면 작업물이 들어왔을 때 기준위치에서 얼만큼 쉬프트 되어있는지 계산할 수 있습니다. 이러한 쉬프트량이 자동으로 계산되어 보정되는 기능 또한 사용 가능합니다.
 터치센싱은 그림 8.5와 같이 총 8가지 타입 (필렛, VGroove, Butt, LRCen, DetectGroove, Wall) 을 지원합니다. 

       
<p align="center">
 <img src="../../_assets/8_7.png" width="90%"></img>
 <em><p align="center">그림 8.7 터치센싱 타입</p></em>
</p>


터치센싱은 명령어에서 [속성]을 누르면 그림 8.8와 같은 창에 진입합니다. 탐색속도, 퇴피속도, 탐색거리, 진행거리, 오차보정량, 터치방식 등과 같은 조건들이 제어기에 저장됩니다. 


<p align="center">
 <img src="../../_assets/8_8.png" width="70%" ></img>
 <em><p align="center">그림 8.8 터치센싱 조건 편집화면</p></em>
</p>



터치센싱 명령은 T.P화면에서 [명령입력]-[아크]-[touchsen]을 입력하여 기록할 수 있습니다.

- 명령어 구성
   - ```touchsen``` cnd=조건번호, crd=좌표계, dir=[탐색방향1, 탐색방향2, 탐색방향3], pose=결과포즈 저장변수, gap=butt gap 변수
   - ```touchsen``` cnd=조건번호, crd=좌표계, dir=[탐색방향1, 탐색방향2, 탐색방향3], angle=탐색방향각도, pose=결과포즈 저장변수, gap=butt gap 변수
   - ```touchsen``` cnd=조건번호, crd=좌표계, dir=[탐색방향1, 탐색방향2, 탐색방향3], angle=탐색방향각도, mpose=결과포즈 저장변수, mshift=계산된시프트 변수, gap=butt gap 변수

   - ```touchsen``` cnd=1, crd="robot", dir=[+tx, +tz], lift_up=3, pose=P10, gap=var_gap
      - cnd=1		: 터치센싱 조건번호
      - crd="robot" : 터치센싱 좌표계
      - dir=[+tx, +tz]	: 탐색방향 파라미터 (직교, 포즈, 툴좌표, 툴프로젝션 입력 가능)
      - lift_up=3		: 바닥찍고 들어올릴 량 [mm] (Butt, V그루브), 탐지기준거리 (DetectGroove)
      - pose=P10		: 센싱하여 계산된 포즈가 저장될 포즈변수.
      - gap=var_gap 	: BUTT 작업물일 경우 gap이 저장될 변수 (소수점 첫째 자리에서 반올림됨)
      - [quick open] 키 	: 탐색속도, 퇴피속도, 탐색거리, 진행거리, 오차보정량, 터치방식(닿을 때, 땔 때) 지정가능

센싱방향은 작업물 타입에 따라 다음과 같이 지정할 수 있습니다.

- Fillet	: 베이스좌표방향, 포즈방향, 툴프로젝션 방향, +TZ 방향
- Butt 	: 포즈방향, 툴방향
- V Groove 	: 포즈방향, 툴방향
- LRCen 	: 툴방향
- DetectGroove: 툴방향, 툴프로젝션방향

<center>

|타입|	최대탐색 </br>방향개수 |	직교XYZ </br>모든타입 </br>지원예정	| 툴좌표계|	툴프로젝션</br>좌표계 |	포즈 |기타 입력인자|
|:---:|	:---: |	:---:	| :---:|	:---: |	:---: |:---:|
|Fillet|	3	|O|	O (1타점)|	O	|O|	후퇴거리|
|Butt	|1 |	X	|O	|X	|O	|오차보정량 |
|VGroove |	1 |	X |	O	|X	|O	| |
|LRCen |	1	|O |	O	|X |	X |  |	
|DetectGroove|	2 |	X |	O |	O |	X	| 진행거리1 </br> 후퇴거리1 |

</center>

1번 터치센싱조건 (명령어에서 [quick open]으로 사용자가 설정해놓은 조건들)에는 필렛, 2번 조건에는 버트, 3번 조건에는 V그루브로 작업물 타입이 지정되어있다고 가정할 때 예시는 아래와 같습니다. 

 ```python
   touchsen cnd=1, crd="robot", dir=[tf,td], pose=P10        #1번 조건, 툴프로젝션 방향, 2점 터치
   touchsen cnd=1, crd="robot", dir=[+x,-y,-z], pose=P10     #1번 조건, 베이스좌표 방향, 3점 터치
   touchsen cnd=1, crd="robot", dir[+tz], pose=P10           #1번 조건, +TZ방향, 1점 터치
   touchsen cnd=2, crd="robot", dir="+tx", lift_up=3, pose=P10, gap=var1 #2번 조건, 툴좌표계 방향, 바닥터치 후3mm 상승
   touchsen cnd=3, crd="robot", crd="robot", dir="-ty", lift_up=3, pose=P10   #3번 조건, 툴좌표계 방향
 ```

</br>

---
제공하는 터치센싱 방식 (작업물 타입)은 다음과 같습니다.

[1] Fillet 타입

<p align="center">
 <img src="../../_assets/8_9.png" width="60%"></img>
 <em><p align="center">그림 8.9 터치센싱 예 Fillet 타입</p></em>
</p>

- 명령어 작성 예시
```python
  touchsen cnd=1, crd="robot", dir=["+x","-y", "-z"], pose=P10
  touchsen cnd=1, crd="robot", dir=["tf", "td"], pose=P10
  touchsen cnd=1, crd="robot", dir=["+tz"], pose=P10
```
- 1점 센싱은 탐색방향을 한 개만 지정하고 2점 센싱은 탐색방향을 순차적으로 2개 지정, 3점 센싱은 탐색방향을 순차적으로 3개 지정합니다.
- 툴 프로젝션 방식 : +ToolZ축을 베이스 XYZ 평면에 사영시켜 전진, 좌우, 하강 방향을 결정하는 방식입니다. TF(전진), TD(하강), TL(좌), TR(우)로 방향을 지정할 수 있습니다. TL은 TFRotZ(90), TR은 TFRotZ(-90) 방향입니다.
- 용접점이 너무 많아 포즈변수 관리가 어려울 경우 툴프로젝션 방식 (TPM)을 사용합니다.
- 작업물에 회전량(RX, RY, RZ)이 존재하는 틀어진 Fillet의 경우 각도지정 옵션을 이용해 탐색방향을 변경할 수 있습니다.



[2] V Groove 타입

<p align="center">
 <img src="../../_assets/8_10.png" width="70%"></img>
 <em><p align="center">그림 8.10 터치센싱 예 V Groove 타입</p></em>
</p>   




- 명령어 작성 예시
```python
  touchsen cnd=3, crd="tool", dir=[-ty,+tz], lift_up=3, pose=P10    #3번 조건, 툴좌표계 방향
```
- V그루브 타입은 VGroove 센싱에 사용할 수 있습니다. 단, 이때 센싱 시작 전 툴은 위 그림과 유사하게 각의 2등분선 상에 위치 시키는 것을 권장합니다.
- 센싱을 위해 상승량은 최소 3mm이상 설정하는 것을 권장합니다.


 
[3] BUTT 타입

<p align="center">
 <img src="../../_assets/8_11.png" width="30%"></img>
 <em><p align="center">그림 8.11 터치센싱 예 Butt 타입</p></em>
</p>   


- 명령어 작성 예시
```python
    touchsen cnd=2, crd="tool", dir=["+tx","+tz"], lift_up=3, pose=P10, gap=var_gap   
    #2번 조건, 툴좌표계 방향, 바닥 센싱 후3mm 상승상승
```

- Butt 타입은 그림과 같이 바닥면에 수직으로 툴을 위치시키는 것이 중요합니다.
-	센싱을 위해 바닥센싱 후 상승량은 최소 3mm이상 설정하는 것을 권장합니다. 상승량에 따라서 Butt gap의 크기가 바뀔 수 있습니다. 이 경우에는 명령어의 [속성] 창에 진입하여 오차보정량을 입력하면 이 값을 뺀 값으로 butt gap을 계산할 수 있습니다.


센싱 시퀀스는 다음과 같습니다. 
Fillet의 경우 4가지 옵션에 따라 직교방향, 포즈방향, 툴프로젝션방향, 툴좌표방향으로 “전진->복귀” 를 반복하여 용접 시작점을 계산합니다. Butt나 VGroove의 경우 아래와 같은 형태로 센싱이 진행됩니다. (상 좌우센싱 → 바닥센싱 → 상승 → 하 좌우센싱)



<p align="center">
 <img src="../../_assets/8_12.png" width="40%"></img>
 <em><p align="center">그림 8.12 터치센싱 시퀀스 VGroove, Butt 타입</p></em>
</p>   

VGroove와 Butt의 경우 하단 좌우센싱 중점에서 작업물 방향으로 내린 점이 계산된 포즈가 됩니다. DetectGroove의 경우 하단센싱→상승량만큼 상승→전진을 반복합니다. 사용자가 지정한 탐지기준보다 더 내려갈 경우 하단센싱 중 멈추게 되고 그 점이 찾은 포즈가 됩니다. 터치센싱 명령어에서 [속성]을 누르면 해당 조건번호에 대한 터치센싱 조건들을 편집할 수 있습니다.

- 탐색거리 : 탐색방향에 대한 거리들이며 이 거리에 도달해도 작업물을 감지하지 못할 경우 에러가 발생합니다.  
- 탐색속도와 퇴피속도 : 탐색 또는 후퇴시 속도를 지정할 수 있습니다.  
- 오차보정량 : butt gap 보정시 사용됩니다.  
- 후퇴거리 : 필렛에선 처음 센싱 후 퇴피할 거리이고  DetectGroove 타입에서는 바닥을 찍고 들어올릴 거리입니다.  
- 센싱시점 : 접촉시와 접촉해제시를 지원합니다. 일반적으로 접촉시 센싱을 많이 사용하며 오차는 거의 없습니다. 만약 센싱시 와이어 휨에 의한 미세한 오차까지도 고려해 센싱해야 하는 상황에서만 후퇴시 센싱을 사용하십시오.  

각도지정옵션은 탐색방향에 대한 각도를 지정할 수 있습니다. 각도지정 옵션은 Fillet과 DetectGroove 타입에서 지원합니다. 각도지정은 TL축과 베이스 XYZ축 중 한가지 축으로 센싱각도만큼 센싱시퀀스 이동궤적을 모두 회전시킵니다. 
그림 8.13은 필렛과 DetectGroove작업물에서 Y축 또는 TL축으로 30도 회전한 예입니다.

<p align="center">
 <img src="../../_assets/8_13.png" width="300"></img>
 <em><p align="center">그림 8.13 터치센싱 예 각도설정</p></em>
</p>       

- 명령어 작성 예시

```python
   touchsen cnd=1, crd="robot", dir=["+x","-z"], angle=Y30, pose=P100
   touchsen cnd=1, crd="robot", dir=["+x","-z"], angle=TL30, pose=P100
   touchsen cnd=2, crd="robot", dir=["td","tf"], lift_up=5, angle=Y30, pose=P100
   touchsen cnd=2, crd="robot", dir=["td","tf"], angle=TL30, pose=P100   #DetectGroove
```

작업물 타입과 명령어에 지정된 센싱방향 지정좌표계에 따라 지정이 가능한 각도회전 축은 아래 표와 같습니다.

<center>

| 타입	| 센싱방향 </br> 지정좌표계	| 각도지정축|
|:---:|:---:|:---:|
|Fillet	| 모든 좌표계	| 직교 XYZ축 </br>TL축 |
|Detect Groove |	툴 |	불가능 |
|Detect Groove	|툴 프로젝션	|직교 XYZ축</br>TL축 |

</center>

Master/Execution Mode와 연동하는 터치센싱 사용법은 다음과 같습니다. 
Master 모드에선 사용자가 mpose 입력인자에 지정한 변수에 센싱한 포즈가 저장되며, Execution 모드에선 현재 센싱한 포즈를 Master 모드에서 센싱했던 포즈와 비교하여 쉬프트량을 계산하고 사용자가 mshift 입력인자에 지정한 변수에 시프트량이 기록됩니다.

- 명령어 작성 예시
```python
   touchsen cnd=1, crd="robot", dir=["+x","-z"], mpose=P10, mshift=sft_var1
```
위 명령어는 Master 모드에서 P10포즈변수에 센싱한 포즈가 저장되고 Execution 모드에서 센싱했을 때 Master 모드와의 시프트 양이 자동으로 계산되어 sft_var1변수에 저장됩니다.
