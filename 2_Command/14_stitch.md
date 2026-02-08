# 2.14 stitch

### 설명 
```stitch``` 문은 스티치 용접을 수행하는 명령어 입니다. 명령어에 커서를 둔 상태에서 `[속성]` 버튼을 눌러 스티치 조건을 설정할 수 있습니다. 스티치 용접을 하려는 위치로 ```move``` 수행 후 ```arcon```문과 함께 사용해야 합니다. 스티치 기능을 수행하면 해당 위치에서 스티치 용접을 시작하며,  스티치 기능이 종료 되는 지점까지 스티치 용접을 진행 합니다.  
<br/>

### 문법
```python
stitch on, cnd=<조건번호>
stitch off
```  
<br/>


### 파라미터
<table>
  <thead>
    <tr>
      <th>항목</th>
      <th>의미</th>
      <th>기타</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>조건 번호</td>
      <td>
        스티치 조건 번호
        (1 ~ 20)
      </td>
      <td>변수</td>
    </tr>
  </tbody>
</table>  
<br/>


### 사용 예
```python
   stitch on, cnd=2         #  스티치 2번 조건 실행
   stitch off               #  스티치 기능 종료
```

### 세부 설명

  [8.6 STITCH 기능](../8_Application_function/6_Stitch/README.md) 참고
