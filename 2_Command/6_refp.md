﻿# 2.6 refp

### 설명     
```refp``` 명령어는 위빙 동작 시 필요한 참조점을 입력하기 위한 명령어 입니다. 위빙 벽, 진입방향 등의 참조점을 입력합니다.

### 문법
```python
refp <참조점 번호>,<포즈(번호)>
refp <참조점 번호>
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
      <td style="text-align:left">참조점 번호</td>
      <td style="text-align:left">
        참조점의 종류를 설정하는 번호
        (1 ~ 4)
      </td>
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">포즈번호</td>
      <td style="text-align:left">
        참조점의 포즈를 입력합니다.(단, 숨은 포즈로 입력한 경우는 생략됨)
      <td style="text-align:left">변수</td>
    </tr>
  </tbody>
</table>

### 사용 예
```python
   refp 1,P1                   # 위빙의 벽방향을 P1을 이용하여 지정
   refp 1                      # 위빙의 벽방향을 숨은 포즈를 이용하여 지정
   refp 2, (-1073.33, 739.01, 258.30, 0, 76, 23)  # 위빙면의 위치를 지정
```

- 세부 설명
  [[6장 위빙기능(Weaving)]](../6_Weaving_function/README.md) 참고

</br>
</br>

{% hint style="warning" %}
[**주의**]
 -	```refp``` 문은 ```move``` 문처럼 스텝에 속합니다.
 - 사용자키의 <refp>키를 이용해 refp 명령문을 입력한 경우 숨은 포즈 형식이 됩니다.
 - 실행단위를 Cmd, Step로 설정 후 스텝전진을 실행하여 티칭 된 위치로 이동할 수 있습니다.
{% endhint %}