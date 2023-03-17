# 2.3 weaving on


### 설명
```weaving on```은 위빙조건을 실행하는 명령어 입니다. 속성 창에 진입하여 해당 조건번호에 해당하는 위빙조건을 설정할 수 있습니다.


### 문법

```python
weaving on <위빙조건번호>
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
      <td style="text-align:left">위빙조건번호</td>
      <td style="text-align:left">
        불러올 위빙 조건 번호
        (1 ~ 1000)
      </td>
      <td style="text-align:left">변수</td>
    </tr>
  </tbody>
</table>

### 사용 예
```python  
   weaving on, cnd=1    # 위빙 조건 1번을 로딩하여 실행
   arcon cnd=1          # arcon 1번 조건으로 실행
   move L,spd=100cm/min,accu=0,tool=0   # 위의 위빙 조건대로 실행하며 로봇 이동
```

- 세부 설명  
  [[6장 위빙기능(Weaving)]](../6_Weaving_function/README.md) 참고
