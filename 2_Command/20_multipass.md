# 2.20 MULTIPASS

- 설명
    
    아크센싱의 경로를 재현하기 위한 멀티패스 용 명령어 입니다. 이 명령어를 이용하면 원래 아크용접 경로에서 원하는 만큼 시프트 시킨 경로를 재현할 수 있습니다. 


- 문법
  
    - MULTIPASS SAVE, TrjNo=<멀티패스 궤적 번호>, SampDist=<궤적 저장 주기 거리>
    - MULTIPASS LOAD, TrjNo=<멀티패스 궤적 번호>, Side=<좌우 시프트 거리>, Updown=<상하 시프트 거리>, Reverse=<멀티패스 재생방향>, TAS=<토치 전후방향 각도 시프트>, WAS=<토치 좌우방향 각도 시프트>
    - MULTIPASS OFF


- 파라미터
  
   ① 멀티패스 궤적 번호
     - 내용 : 저장/로딩 할 멀티패스 궤적 번호
     - 범위 : 1 ~ 50
   
   ② 궤적 저장 주기 거리
     - 내용 : 멀티패스 궤적을 저장할 샘플링 거리
     - 범위 : 5 ~ 100 mm

   ③ 좌우 시프트 거리
     - 내용 : 멀티패스 재현 시 원래 아크센싱 궤적에서 좌우 방향으로 시프트 할 거리
     - 범위 : -20 ~ 20 mm

   ④ 상하 시프트 거리
     - 내용 : 멀티패스 재현 시 원래 아크센싱 궤적에서 상하 방향으로 시프트 할 거리
     - 범위 : -20 ~ 20 mm
     
   ⑤ 멀티패스 재생방향
     - 내용 : 멀티패스 재현 시 원래 아크센싱 궤적과 반대 방향부터 재생할 것인지 설정
     - 범위 : 0(정방향), 1(역방향)

   
   ⑥ 토치 전후방향 각도 시프트
     - 내용 : 멀티패스 재현 시 토치를 전후 방향으로 기울이는 시프트 각도
     - 범위 : -20 ~ 20 deg

   ⑦ 토치 좌우방향 각도 시프트
     - 내용 : 멀티패스 재현 시 토치를 좌우 방향으로 기울이는 시프트 각도
     - 범위 : -20 ~ 20 deg
  
</br>  

- 사용 예
  
     ```WEAVON WEV#=1```  
     ```MULTPASS SAVE,TrjNo=1,SampDist=10```  
     <span style="color: green"># 1번 궤적에 10mm 간격으로 저장  </span>  
     ```ARCON ASF#=1```   
**S10**  ```MOVE L,R2,S=LV1!cm/min,A=3,T=1```  
**S11**  ```MOVE L,R2,S=LV1!cm/min,A=3,T=1```  
     ```ARCOF```  
     ```WEAVOF```  
     ```MULTPASS OFF```  
**S12**  ```MOVE L,S=50%,A=3,T=1```  
**S13**  ```MOVE L,S=50%,A=3,T=1```  
**S14**  ```MOVE L,S=50%,A=3,T=1```  
     ```MULTPASS LOAD,TrjNo=1,Side=3,Updown=3,Reverse=0,TAS=0,WAS=0```  
     <span style="color: green">#  1번 궤적을 읽어 우측 3mm, 위로 3mm 시프트, 정방향, 각도 시프트 없음.  </span>  
**S15**  ```MOVE L,R2,S=50%,A=0,T=1```  
     <span style="color: green">#  멀티패스 시작 위치로 시프트하며 이동할 스텝  </span>  
     ```WEAVON WEV#=11```  
     ```ARCON ASF#=1 ```  
**S16**  ```MOVE L,R2,S=LV1!cm/min,A=3,T=1```  
**S17**  ```MOVE L,R2,S=LV1!cm/min,A=3,T=1```  
     ```ARCOF```  
     ```WEAVOF```  
     ```MULTPASS OFF```
