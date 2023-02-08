# 2.16 calc_shift



- 설명 
    
    ```calc_shift``` 문은 2개의 포즈변수를 이용해 쉬프트를 계산하는 함수입니다.
터치센싱으로 저장한 포즈 변수들을 이용해 쉬프트를 계산할 때 많이 사용됩니다.


- 문법
  
    - ```calc_shift``` p1=<포즈변수인자>, p2=<포즈변수인자>, sft=<쉬프트변수인자>

- 파라미터
  
   ① 포즈변수 인자
     - 내용 : 포즈변수를 입력합니다.
     - 범위 : 포즈변수
   
   ② 쉬프트변수 인자
     - 내용 : 쉬프트 값을 저장 할 쉬프트 변수를 입력합니다.
     - 범위 : 쉬프트변수

- 사용 예
```python
    move L, spd=30%, …
    var pose_1 = cpo()
    move L, spd=30%, …
    var pose_2 = cpo()
    var sft_1 = Shift(0,0,0,0,0,0,”robot”)
    calc_shift p1=pose_1, p2=pose_2, sft=sft_1      
    # pose_1 – pose_2 의 벡터 쉬프트량을 sft_1에 계산하여 저장
```
  