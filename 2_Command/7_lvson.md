# 2.7 lvs

### 설명 
```lvs``` 문은 LVS(레이저비전센서)를 이용하여 레이저가 위치한 곳의 포즈를 얻어내거나 (seam_find), 시점 탐색 (search), 용접선 추종 (track) 기능을 수행하는 명령어입니다.

### 문법
```python
lvs laser_on, cnd=<조건 번호>, seam=<seam번호>, sp=<seam포즈>
lvs laser_off, cnd=<조건 번호>, seam=<seam번호>, sp=<seam포즈>
lvs search, cnd=<조건 번호>, seam=<seam번호>, sp=<seam포즈>
lvs track, cnd=<조건 번호>, seam=<seam번호>, sp=<seam포즈>
lvs seam_find, cnd=<조건 번호>, seam=<seam번호>, sp=<seam포즈>
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
      <td style="text-align:left">laser_on / laser_off / search / track / seam_find</td>
      <td style="text-align:left">
        laser_on : 레이저를 켭니다. <br>
        laser_off : 레이저를 끕니다. <br>
        search : track 기능을 수행하기 전 시점을 찾고 tracking을 위한 준비를 시작합니다. <br>
        track : arcon을 만나면 용접선 추종을 시작합니다. <br>
        seam_find : 현재 레이저가 센싱하고 있는 위치를 포즈로 변환하여 sp 인자에 저장합니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">조건 번호</td>
      <td style="text-align:left">
        LVS 기능 수행 시 사용되는 조건번호 (1 ~ 32), 각 조건번호 마다 명령어의 속성창에 있는 정보가 달라지며 트래킹시 이 정보를 사용합니다. 
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">seam번호</td>
      <td style="text-align:left">
        seam 번호를 지정합니다. 해당 번호는 LVS 컨트롤러에 전송되어 LVS센서가 해당번호의 seam으로 센싱을 하도록 합니다.
      <td style="text-align:left">변수</td>
    </tr>
    <tr>
      <td style="text-align:left">seam포즈</td>
      <td style="text-align:left">
        seam_find 로 찾은 포즈를 저장하거나 search후 찾은 시점을 저장할 포즈변수를 지정합니다.
      <td style="text-align:left">포즈변수</td>
    </tr>
  </tbody>
</table>









- 
   ① 조건 번호
     - 내용 : LVS 기능 실행 시 사용되는 LVS조건번호
     - 범위 : 1~32
   
   ② 옵션
     - seam : seam 번호를 지정합니다. 해당 번호는 LVS 컨트롤러에 전송되어 LVS센서가 해당번호의 seam으로 센싱을 하도록 합니다.
     - sp : search, seam_find 로 찾은 포즈를 저장할 포즈변수를 지정합니다.
     - seam_find : 심파인딩, LVS를 이용하여 현재 센싱하고 있는 위치를 포즈로 변환하여 저장합니다.
     - track : 트래킹, LVS를 이용하여 실시간 트래킹을 수행하는 명령어입니다. track을 수행하기전에 search가 선행되어야 합니다.
     

</br>  

### 사용 예
```python
   lvs seam_find, cnd=1, seam=10, sp=p10    
   # 조건번호 1번, seam번호 10번으로 seam 파인딩 기능 수행, 결과포즈는 p10에 저장
   lvs track, cnd=1 ,seam=10 , sp=p10           
   # 조건번호 1번, seam번호 10번으로 LVS 용접선 추종 시작
```


- 세부 설명
  
  •	옵션 기능으로 사용을 위해서는 당사에 문의하시기 바랍니다.
