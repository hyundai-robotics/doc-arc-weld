# 2.15 calshift



### 설명     
```calshift``` 문은 2개의 포즈변수를 이용해 쉬프트를 계산하는 함수입니다.
터치센싱으로 저장한 포즈 변수들을 이용해 쉬프트를 계산할 때 많이 사용됩니다.


### 문법
```python
<쉬프트변수인자>=calshift(<포즈변수인자1>, <포즈변수인자2>)
<쉬프트변수인자>=calshift(<포즈변수인자1>, <포즈변수인자2>,"TV")
```

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
      <td>포즈변수 인자</td>
      <td>
        포즈변수를 입력합니다.(1 ~ 9999)
      </td>
      <td>포즈변수</td>
    </tr>
    <tr>
      <td>쉬프트변수 인자</td>
      <td>
        쉬프트 값을 저장 할 쉬프트 변수를 입력합니다.
      </td>
      <td>쉬프트변수</td>
    </tr>    
    <tr>
      <td>TV</td>
      <td>
        툴에 수직인 방향으로 쉬프트를 계산합니다.
      </td>
      <td>문자열</td>
    </tr>
  </tbody>
</table>  

### 사용 예
```python
    move L, spd=30%, …
    var pose_1 = cpo()
    move L, spd=30%, …
    var pose_2 = cpo()
    var sft_1
    sft_1=calshift(pose_1,pose_2)   
    # pose_1 – pose_2 의 벡터 쉬프트량을 계산하여 sft_1에 저장
```
  