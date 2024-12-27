# 2.16 lps


### 설명
```lps``` 문은 레이저 포인트 센싱을 수행하는 명령어 입니다. 최초 툴과 레이저 사이 캘리브레이션을 진행하고, 원하는 모드에 맞게 명령문을 작성하면 용접하고자 하는 점(seam)을 탐지합니다. 

- 세부 설명  
  **[[8.9 LPS 기능]](../8_Application_function/9_LPS/README.md)** 참고

### 문법  
```py
# 캘리브레이션 과정
lps calib1,cnd=<조건번호>
lps calib2,cnd=<조건번호>,pose=<저장할 포즈>
lps calib3,cnd=<조건번호>,pose=<저장할 포즈>
lps calib4,cnd=<조건번호>

# 기능 사용
lps spot,  cnd=<조건번호>,pose=<저장할 포즈>
lps gap,   cnd=<조건번호>,Tx=<탐색거리>,Ty=<탐색거리>,spd=<탐색속도>,pose=<저장할 포즈>
lps scan,  cnd=<조건번호>,Tx=<탐색거리>,Ty=<탐색거리>,spd=<탐색속도>,pose=<저장할 포즈>
lps gather,cnd=<조건번호>,Tx=<탐색거리>,Ty=<탐색거리>,spd=<탐색속도>
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
      <td style="text-align:left">cmd</td>
      <td style="text-align:left">
        calib1 ~ 4, spot(한 점), gap(단차), scan(필렛), gather(데이터 수집)
      </td>
      <td style="text-align:left">(명렁어)</td>
    </tr>
    <tr>
      <td style="text-align:left">cnd</td>
      <td style="text-align:left">
        센싱 조건 번호 (1 ~ 8)
      </td>
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">Tx, Ty</td>
      <td style="text-align:left">
        툴 기준 x축과 y축 방향으로 탐색하는 거리
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">spd</td>
      <td style="text-align:left">
        각 모드에서 로봇이 탐색하는 속도
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">pose</td>
      <td style="text-align:left">
        포즈변수를 지정합니다.
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">mpose/mshift</td>
      <td style="text-align:left">
        (예정)
        마스터모드에서 사용되는 포즈, 쉬프트 변수, 마스터모드에서는 mpose에 센싱결과를 저장하며, 실행모드에서는  mshift에 할당된 변수에 쉬프트값 (현재센싱포즈 - 마스터포즈 의 벡터)이 계산되어 저장됩니다.
      <td style="text-align:left">포즈변수/시프트변수</td>
    </tr>
  </tbody>
</table>


### 사용 예

- 캘리브레이션
```py
  lps calib1,cnd=1   # 1번 캘리 과정을 수행한다.
  var p2=cpo()        # 포즈변수 p2을 선언하고 현재 포즈를 저장해둔다.
  lps calib2,cnd=1,pose=p2      # 2번 캘리 과정을 수행하여 p2에 저장한다.
  move L,spd=60%,acc=0,tool=0  # 3번 과정을 위해 평면에서 최대한 떨어진 위치로 이동시킨다.
  var p3=cpo()        # 포즈변수 p3을 선언하고 현재 포즈를 저장해둔다.
  lps calib3,cnd=1,pose=p3      # 3번 캘리 과정을 수행하여 p3에 저장한다.
  lps calib4,cnd=1   # 3번 과정이 끝난 위치에서 높이를 낮춰가며 오차 보정 결과를 얻는다.
```

- 용접점 탐색(scan)
```py
# 단차 모드
  var p10=cpo()     # 포즈변수 p10을 선언하고 현재포즈를 저장해둔다.
  lps scan,cnd=1,Ty=40,spd=5,pose=po1     # 툴 기준 y 방향으로 40만큼 5의 속도로 이동하며 센싱
  move L,tg=po1,spd=60%,acc=0,tool=0      # 위에서 찾은 점으로 이동
```
