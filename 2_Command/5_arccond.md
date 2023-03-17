# 2.5 arccond



### 설명
```arccond``` 용접 DB를 이용하여 JOB을 구성하거나, 용접 DB를 이용한 용접조건 연속변경 기능을 이용할 때 사용합니다.

### 문법
```python
arccond <보간종류>, cnd=<조건번호>, gap=<gap>, spd=<용접속도>, rd=<벽방향>, ld=<타방향>, freq=<위빙주파수>, cur=<전류>, vol=<전압>
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
      <td style="text-align:left">보간종류</td>
      <td style="text-align:left">
        보간조건 설정
        (D:즉시변경, L:선형보간변경)
      </td>
      <td style="text-align:left">문자</td>
    </tr>
    <tr>
      <td style="text-align:left">조건번호</td>
      <td style="text-align:left">
        용접 DB (WDB) 및 보간조건을 저장하는 조건번호<br>
        (1 ~ 1000)
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">gap</td>
      <td style="text-align:left">
        gap을 입력합니다.<br>
        (-1 ~ 1000)[mm]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">용접속도</td>
      <td style="text-align:left">
        즉시변경시 용접속도입니다.<br>
        (1 ~ 1000) [cm/min]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">벽방향</td>
      <td style="text-align:left">
        즉시변경시 위빙 벽방향 폭입니다.<br>
        (1 ~ 50)[mm]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">타방향</td>
      <td style="text-align:left">
        즉시변경시 위빙 타방향 폭입니다.<br>
        (1 ~ 50)[mm]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">위빙주파수</td>
      <td style="text-align:left">
        즉시변경시 위빙주파수 입니다.<br>
        (1 ~ 10)[Hz]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">전류</td>
      <td style="text-align:left">
        즉시변경시 용접 전류입니다.<br>
        (1 ~ 1000)[A]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">전압</td>
      <td style="text-align:left">
        즉시변경시 용접 전압입니다.<br>
        (1 ~ 200)[V]
      <td style="text-align:left">변수</td>
    </tr>
  </tbody>
</table>

### 사용 예
```python
	arccond D, cur=170, vol=10 # 전류 170A, 전압 10V로 즉시변경
	arccond D, spd=80, rd=20, ld=20, freq=1.5 # 용접속도 80cm/min, 위빙폭 20mm, 주파수 1.5Hz로 즉시변경
	arccond D, cnd=1 # 1번 조건으로 즉시변경
	arccond L, cnd=1, 용접스텝, arccond L, cnd=2 # 1번조건에서 2번조건으로 WDB데이터 연속보간 변경
```