# 2.9 heightsen on

### 설명 
```heightsen on``` 문은 높이센싱(AVC, Arc 길이제어)을 시작하는 명령문입니다.
자세한 내용은 '높이센싱' 부분을 참고하십시오.  
<br/>


### 문법
```python
heightsen on, cnd=<높이센싱 조건번호>
heightsen on, cnd=<높이센싱 조건번호>, crd=<좌표계>, dir=<방향>
```  

### 파라미터  

| 항목 | 의미 | 기타 |
| :--- | :--- | :--- |
| 높이센싱 조건번호 | 높이센싱 실행 시 사용하는 조건 번호 (1 ~ 8) | 변수 |
| 좌표계 | 높이 방향 지정좌표계("base", "tool", "user") | 미지정 시, tool +z방향 |
| 방향 | 높이 방향 ("+x", "+y", "+z") | 미지정 시, tool +z방향 |

### 사용 예

```python   
   # tool +z방향, 1번 조건으로 높이센싱 시작
   heightsen on, cnd=1        
```  
```python   
   # base +x 방향, 1번 조건으로 높이센싱 시작
   heightsen on, cnd=1, crd="base", dir="+x"  
```  
```python  
   # 1번 사용자 좌표계 -z 방향, 1번 조건으로 높이센싱 시작 
   heightsen on, cnd=1, crd="user_1", dir="-z"  
```  

### 세부 설명
  [[8.4 높이센싱(Height Sensing)]](../8_Application_function/4_Height_sensing/README.md) 참고


