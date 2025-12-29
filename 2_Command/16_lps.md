# 2.16 lps

### 설명 

```lps``` 문은 레이저 변위 센서를 이용하여 레이저가 위치한 곳의 포즈를 얻어내거나(spot 모드), 단차 검출(stepp 모드), 용접심 탐색(scan 모드) 기능을 수행하는 명령어입니다.  
<br/>

### 문법

```python
lps auto_calib, cnd=<조건 번호>, Tx=<툴 기준 X 방향 이동거리>, Ty=<툴 기준 Y 방향 이동거리>
lps spot, cnd=<조건 번호>, sp=<저장 포즈>
lps stepp, cnd=<조건 번호>, Tx=<툴 기준 X 방향 이동거리>, Ty=<툴 기준 Y 방향 이동거리>, spd=<로봇 속도>, sp=<저장 포즈>
lps scan, cnd=<조건 번호>, Tx=<툴 기준 X 방향 이동거리>, Ty=<툴 기준 Y 방향 이동거리>, spd=<로봇 속도>, sp=<저장 포즈>
```  
<br/>

### 파라미터

<table>
  <thead>
    <tr>
      <th>대항목</th>
      <th>소항목</th>
      <th>의미</th>
      <th>기타</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="5">lps</td>
      <tr>
      <td>auto_calib</td>
      <td>
        툴-센서 간 자동 캘리브레이션을 수행합니다.
      </td>
      </tr>
      <tr>
      <td>spot</td>
      <td>
        한 점 모드로, 현재 레이저가 가리키는 곳의 포즈를 얻습니다.
      </td>
      </tr>
      <tr>
      <td>stepp</td>
      <td>
        단차 모드로, 레이저가 움직이며 출력값이 갑자기 변하는 곳의 포즈를 얻습니다.
      </td>
      </tr>
      <tr>
      <td>scan</td>
      <td>
        스캔 모드로, 레이저가 움직인 경로에서 용접점으로 추정되는 곳의 포즈를 얻습니다.
      </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">cnd</td>
      <td>
        LPS 기능 수행 시 사용되는 조건 번호(1 ~ 8), 각 조건 번호마다 명령어의 속성창에 있는 정보가 달라지며 자동 캘리브레이션과 단차 모드에서의 민감도, 포즈 저장 시 좌표계 설정할 때 이 정보를 사용합니다.
      <td>변수</td>
    </tr>
    <tr>
      <td colspan="2">Tx / Ty</td>
      <td>
        툴 기준 x 혹은 y 방향으로 이동할 거리를 설정합니다. auto_calib 외에는 두 값 중 하나의 값만 입력해야 합니다.
      <td>변수</td>
    </tr>
    <tr>
      <td colspan="2">spd</td>
      <td>
        로봇이 동작 수행 시 움직이는 속도를 지정합니다.
      <td>변수</td>
    </tr>
    <tr>
      <td colspan="2">sp</td>
      <td>
        각 명령어로 찾은 현재 포즈를 저장할 포즈 변수를 지정합니다.
      <td>포즈 변수</td>
    </tr>
    <tr>
      <td colspan="2">mp</td>
      <td>
        마스터 모드에서는 mp(마스터 포즈)에 센싱 결과를 저장하며, 양산 모드에서는 ms(마스터 시프트)를 계산할 때 사용됩니다.
      <td>포즈 변수</td>
    </tr>
    <tr>
      <td colspan="2">ms</td>
      <td>
        양산 모드에서 사용되는 시프트 변수. 마스터 포즈와 현재 포즈의 차이가 계산되어 저장됩니다.
      <td>시프트 변수</td>
    </tr>
  </tbody>
</table>  
<br/>


### 사용 예

```python
   lvs auto_calib, cnd=1, Tx=50, Ty=-100
   # 조건 번호 1번, 툴 기준 x 방향으로 50, y 방향으로 -100만큼 설정된 거리 내에서 자동 캘리브레이션을 수행
   lvs spot, cnd=1, sp=p10
   # 조건 번호 1번, 조건에 설정된 좌표계로 현재 레이저 지점의 포즈를 p10에 저장

   lvs stepp, cnd=1, Tx=50, sp=p10
   # 조건 번호 1번, 툴 기준 X 방향으로 50만큼 설정된 거리를 이동하며 단차가 검출될 때 즉시 멈추어 포즈를 p10에 저장
   lvs scan, cnd=1, Tx=50, spd=10, sp=p10
   # 조건 번호 1번, 툴 기준 X 방향으로 50만큼 설정된 거리만큼 이동이 완료되면 용접점을 검출하여 p10에 저장
```  
<br/><br/>


{% hint style="info" %}
옵션 기능으로 사용을 위해서는 당사에 문의하시기 바랍니다.
{% endhint %}


### 세부 설명

  [8.8 LPS(Laser Point Sensing)](../8_Application_function/8_LPS/README.md) 참고
