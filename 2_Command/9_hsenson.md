# 2.9 heightsen on

### 설명 
```heightsen on``` 문은 높이센싱(AVC, Arc 길이제어)을 시작하는 명령문입니다.
자세한 내용은 ‘높이 센싱’ 부분을 참고하십시오.


### 문법
  
```python
heightsen on, cnd=<높이센싱 조건번호>
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
      <td style="text-align:left">높이센싱 조건번호</td>
      <td style="text-align:left">
        높이센싱 실행 시 사용하는 조건 번호
        (1 ~ 8)
      </td>
      <td style="text-align:left">변수</td>
    </tr>

  </tbody>
</table>

### 사용 예
```python   
   heightsen on, cnd=1        # 높이센싱 1번 조건으로 높이센싱을 시작
```

- 세부 설명
  
  [[8.3 높이센싱(Height Sensing)]](../8_Application_function/3_Height_sensing/README.md) 참고