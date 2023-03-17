# 2.14 stitch

### 설명 
```stitch``` 문은 스티치 용접을 수행하는 명령어 입니다. 퀵 오픈창으로 스티치 조건을 설정할 수 있으며 이 정보들은 ROBOT.STC에 저장됩니다. 스티치 용접을 하려는 위치로 ```move``` 수행하고 ```arc on```문과 함께 사용해야 하며 스티치 기능을 수행하면 해당 위치에서 스티치 용접을 시작하며,  스티치 기능이 종료 되는 지점까지 스티치 용접을 진행 합니다.


### 문법
```python
stitch on, cnd=<조건번호>
stitch off
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
      <td style="text-align:left">조건 번호</td>
      <td style="text-align:left">
        스티치 조건 번호
        (1 ~ 20)
      </td>
      <td style="text-align:left">변수</td>
    </tr>
  </tbody>
</table>

- 사용 예
```python
   stitch on, cnd=2         #  스티치 2번 조건 실행
   stitch off               #  스티치 기능 종료
```
