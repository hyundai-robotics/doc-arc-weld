# 2.13 touchsen

### 설명
```touchsen``` 문은 와이어 터치센싱을 수행하는 명령어 입니다. 속성창에서 센싱타입 및 센싱조건을 설정할 수 있습니다. 터치센싱 하려는 위치로 move를 수행하고 `touchsen`문을 수행하면 해당 위치에서 센싱타입 및 조건에 맞추어 자동으로 터치센싱 합니다.

- 세부 설명  
  [[8.2 터치센싱 기능]](../8_Application_function/2_Touch_sensing/README.md) 참고


### 문법
```python
touchsen cnd=<조건번호>, crd=<좌표계>, dir=<방향>, pose=<저장할 포즈>
touchsen cnd=<조건번호>, crd=<좌표계>, dir=<방향>, rotation=<센싱각도>, pose=<저장할 포즈>
touchsen cnd=<조건번호>, crd=<좌표계>, dir=<방향>, lift_up=<들어올릴 양>, pose=<저장할 포즈>, gap=<butt gap 변수>
touchsen cnd=<조건번호>, crd=<좌표계>, dir=<방향>, mpose=<마스터모드 저장할 기준포즈>, mshift=<양산모드 계산된 쉬프트 변수>
```

### 파라미터
<table>
  <thead>
    <tr>
      <th style="text-align:left">항목</th>
      <th style="text-align:left">의미</th>
      <th style="text-align:left">기타</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">조건번호</td>
      <td style="text-align:left">
        터치센싱 조건 번호 (1 ~ 8)
      </td>
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">좌표계</td>
      <td style="text-align:left">
        센싱방향 지정좌표계("robot", "base", "tool", "tool_prj")
      </td>
    </tr>
    <tr>
      <td style="text-align:left">방향</td>
      <td style="text-align:left">
        터치센싱 방향 (센싱 타입별 지원 방향 상이함)
        ("+x", ["+x","-z"], ["+ty", "+tz"])
      <td style="text-align:left">문자열 배열</td>
    </tr>
    <tr>
      <td style="text-align:left">저장할 포즈</td>
      <td style="text-align:left">
        포즈변수를 지정합니다.
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">센싱각도</td>
      <td style="text-align:left">
        베이스/툴 (X+30 또는 Y-20 등..) 또는 툴프로젝션 (TL+30, TL-10 등..) 좌표계에 대한 축으로 모든 센싱방향을 회전
        (Y+30, Y-30, X+30, X-30, TL+30, TL-30, TY+30, TY-30)
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">들어올릴 양</td>
      <td style="text-align:left">
        바닥 탐색 후 상승량[mm]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">탐지기준거리</td>
      <td style="text-align:left">
        detect groove 탐지기준거리[mm]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">Butt gap 변수</td>
      <td style="text-align:left">
        Butt, VGroove 센싱 타입에서 터치센싱으로 측정한 하단 gap이 저장될 변수
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">mpose<br>(마스터모드)</td>
      <td style="text-align:left">
        마스터모드에서는 mpose에 센싱결과를 저장하며, 양산모드에서 mpose는 mshift를 계산할 때 사용됩니다.
      <td style="text-align:left">포즈변수</td>
    </tr>
    <tr>
      <td style="text-align:left">mshift<br>(양산모드)</td>
      <td style="text-align:left">
       양산모드에서 사용되는 쉬프트 변수. mshift에 할당된 변수에 쉬프트값(현재센싱포즈 - 마스터포즈의벡터)이 계산되어 저장됩니다.
      <td style="text-align:left">시프트변수</td>
    </tr>
  </tbody>
</table>

### 사용 예
```python
  var var1=0      # butt 작업물 센싱시 측정된 gap을 저장할 변수를 선언한다.
  var P10=cpo()   # 포즈변수 P10을 선언하고 현재포즈를 저장해둔다.
  touchsen cnd=2, crd="tool", dir=["+y"], lift_up=3, pose=P10, gap=var1  # 2번 조건, 툴좌표계 방향, 바닥센싱 후 3mm 상승, 갭은 var1변수에 저장
  touchsen cnd=1, crd="tool", dir=["tf", "td"], pose=P10, 0  # 1번 조건, 툴프로젝션 방향, 2점 터치
  touchsen cnd=1, crd="base", dir=["+x","-y","-z"], pose=P10, 0  # 1번 조건, 베이스좌표 방향, 3점 터치
```

