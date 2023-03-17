# 2.13 touchsen

### 설명
```touchsen``` 문은 와이어 터치센싱을 수행하는 명령어 입니다. 속성창에서 센싱타입 및 센싱조건을 설정할 수 있습니다. 터치센싱 하려는 위치로 move를 수행하고 touchsen문을 수행하면 해당 위치에서 센싱타입 및 조건에 맞추어 자동으로 터치센싱 합니다.


### 문법
```python
touchsen cnd=<조건번호>, crd=<좌표계>, dir=<방향>, pose=<저장할 포즈>
touchsen cnd=<조건번호>, crd=<좌표계>, dir=<방향>, angle=<탐색각도>, pose=<저장할 포즈>
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
        터치센싱 조건 번호 
        (1 ~ 8)
      </td>
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">방향</td>
      <td style="text-align:left">
        터치센싱 방향(센싱타입별 지원 방향 상이함)
        (+x, [+x,-z], [+ty, +tz])
      <td style="text-align:left">문자열 배열</td>
    </tr>
    <tr>
      <td style="text-align:left">저장할 포즈</td>
      <td style="text-align:left">
        포즈번호를 지정합니다.
      <td style="text-align:left">변수</td>
    </tr>
        <tr>
      <td style="text-align:left">Butt gap 변수</td>
      <td style="text-align:left">
        Butt/VGroove 타입에서 터치센싱으로 측정한 gap이 저장될 변수
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">센싱각도</td>
      <td style="text-align:left">
        베이스, 툴, 툴프로젝션 좌표계에 대한 축으로 모든 센싱방향을 회전
        (Y30, Y-30, X30, X-30, TL30, TL-30, TY30, TY-30)
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">mpose/mshift</td>
      <td style="text-align:left">
       포즈와 시프트 변수로 마스터모드 기능 사용시 사용, 마스터모드에서는 해당번호의 포즈에 센싱결과를 저장하며, 실행모드에서는  시프트변수에  센싱하여 측정된 포즈의 마스터모드 대비 시프트값이 계산되어 저장됩니다.
      <td style="text-align:left">포즈변수/시프트변수</td>
    </tr>
  </tbody>
</table>

### 사용 예
```python
  var var1=0      # butt 작업물 센싱시 측정된 gap을 저장할 변수를 선언한다.
  var P10=cpo()   # 포즈변수 P10을 선언하고 현재포즈를 저장해둔다.
  touchsen cnd=2, crd="tool", dir=[+y], lift_up=3, pose=P10, gap=var1
  # 2번 조건, 툴좌표계 방향, 바닥센싱 후3mm 상승, 갭은 var1변수에 저장
  touchsen cnd=1, crd="tool", dir=[tf, td], pose=P10, 0
  # 1번 조건, 툴프로젝션 방향, 2점 터치
  touchsen cnd=1, crd="base", dir=[+x,-y,-z], pose=P10, 0     
  # 1번 조건, 베이스좌표 방향, 3점 터치
```

