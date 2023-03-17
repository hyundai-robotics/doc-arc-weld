# 2.11 multipass

### 설명  
```multipass``` 는 아크센싱의 경로를 재현하기 위한 멀티패스 용 명령어 입니다. 이 명령어를 이용하면 원래 아크용접 경로에서 원하는 만큼 시프트 시킨 경로를 재현하여 용접할 수 있습니다. 


### 문법
```python  
multipass save, trj=<멀티패스 궤적 번호>, period=<궤적 저장 주기 거리>
multipass load, trj=<멀티패스 궤적 번호>, side=<좌우 시프트 거리>, height=<상하 시프트 거리>, reverse=<멀티패스 재생방향>, tas=<토치 전후방향 각도 시프트>, was=<토치 좌우방향 각도 시프트>
multipass off
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
      <td style="text-align:left">멀티패스 궤적 번호</td>
      <td style="text-align:left">
        저장/로딩 할 멀티패스 궤적 번호
        (1 ~ 50)
      </td>
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">궤적 저장 주기 거리</td>
      <td style="text-align:left">
        멀티패스 궤적을 저장할 샘플링 거리
        (5 ~ 100)[mm]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">좌우 시프트 거리</td>
      <td style="text-align:left">
        멀티패스 재현 시 원래 아크센싱 궤적에서 좌우 방향으로 시프트 할 거리
        (-20 ~ 20)[mm]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">상하 시프트 거리</td>
      <td style="text-align:left">
        멀티패스 재현 시 원래 아크센싱 궤적에서 좌우 방향으로 시프트 할 거리
        (-20 ~ 20)[mm]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">멀티패스 재생방향</td>
      <td style="text-align:left">
        멀티패스 재현 시 원래 아크센싱 궤적과 반대 방향부터 재생할 것인지 설정
        (0: 정방향, 1: 역방향)
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">토치 전후방향 각도 시프트</td>
      <td style="text-align:left">
        멀티패스 재현 시 토치를 전후 방향으로 기울이는 시프트 각도
        (-20 ~ 20)[deg]
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">토치 좌우방향 각도 시프트</td>
      <td style="text-align:left">
        멀티패스 재현 시 토치를 좌우 방향으로 기울이는 시프트 각도
        (-20 ~ 20)[deg]
      <td style="text-align:left">변수</td>
    </tr>
  </tbody>
</table>

### 사용 예
```python
     weaving on, cnd=1 
     multipass save, trj=1, period=10       # 1번 궤적에 10mm 간격으로 저장  
     arcon cnd=1
S10  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
S11  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
     arcoff
     weaving off
     multipass off
S12  move L,spd=50%,accu=3,tool=1
S13  move L,spd=50%,accu=3,tool=1
S14  move L,spd=50%,accu=3,tool=1
     multipass load,trj=1,side=3,height=3,reverse=0,tas=0,was=0   
     # 1번 궤적을 읽어 우측 3mm, 위로 3mm 시프트, 정방향, 각도 시프트 없음.  
S15  move L,R2,spd=50%,accu=0,tool=1       #  멀티패스 시작 위치로 시프트하며 이동할 스텝  
     weaving on, cnd=11
     arcon cnd=1 
S16  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1  
S17  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
     arcoff
     weaving off  
     multipass off
```