# 8.3.10 멀티패스 용접 예시

작업 프로그래밍은 다음과 같이 작성합니다.
이 작업은 1pass 용접 후 2pass, 3pass를 좌/우 3mm, 높이 3mm로 시프트 하여 용접하는 작업프로그램입니다.


```py
     'Cylinder AS and MP Program
S1   MOVE P,S=60%,A=3,T=1  
     'Find 4 Points by touch sensing
S2   MOVE L,S=30%,A=3,T=1  			' 1: 원 궤적 첫 번째 점 탐색 위치
     TOUCHSEN TSC#=4,TF,TD,0,P1,V1!		' 2: 원 궤적 첫 번째 위치 터치센싱
S3   MOVE L,S=30%,A=3,T=1  			' 3: 원 궤적 두 번째 점 탐색 위치
     TOUCHSEN TSC#=4,TF,TD,0,P2,V1! 		' 4: 원 궤적 두 번째 위치 터치센싱
S4   MOVE L,S=30%,A=3,T=1  			' 5: 원 궤적 세 번째 점 탐색 위치
     TOUCHSEN TSC#=4,TF,TD,0,P3,V1! 		' 6: 원 궤적 세 번째 위치 터치센싱
S5   MOVE L,S=30%,A=3,T=1  			' 7: 원 궤적 네 번째 점 탐색 위치
     TOUCHSEN TSC#=4,TF,TD,0,P4,V1! 		' 8: 원 궤적 네 번째 위치 터치센싱
     '1st pass					첫 멀티패스 궤적을 아크센싱으로 저장
S6   MOVE L,S=60%,A=3,T=1  
S7   MOVE L,P1,S=50%,A=3,T=1
     WEAVON WEV#=3
     MULTIPASS SAVE,TrjNo=1,SampDist=10
     ARCON ASF#=3
S8   MOVE C,P2,S=60cm/min,A=3,T=1
S9   MOVE C,P3,S=60cm/min,A=3,T=1
S10  MOVE C,P4,S=60cm/min,A=3,T=1
S11  MOVE C,P1,S=60cm/min,A=3,T=1
     ARCOF ASF#
     WEAVOF
     MULTIPASS OFF
S12  MOVE P,S=60%,A=3,T=1  
     '2nd pass				두 번째 멀티패스는 수평 우측 3mm, 수직 3mm 시프트
     MULTIPASS LOAD,TrjNo=1,Side=3,Updown=3,Reverse=0,TAS=0,WAS=0
S13  MOVE L,P1,S=20%,A=3,T=1
     WEAVON WEV#=4
     ARCON ASF#=3
S14  MOVE C,P2,S=60cm/min,A=3,T=1
S15  MOVE C,P3,S=60cm/min,A=3,T=1
S16  MOVE C,P4,S=60cm/min,A=3,T=1
S17  MOVE C,P1,S=60cm/min,A=3,T=1
     ARCOF ASF#
     WEAVOF
     MULTIPASS OFF
     '3rd pass				세 번째 멀티패스는 수평 우측 -3mm, 수직 3mm 시프트
S18  MOVE P,S=60%,A=3,T=1  
     MULTIPASS LOAD,TrjNo=1,Side=-3,Updown=3,Reverse=0,TAS=0,WAS=0
S19  MOVE L,P1,S=20%,A=3,T=1
     WEAVON WEV#=4
     ARCON ASF#=3
S20  MOVE C,P2,S=60cm/min,A=3,T=1
S21  MOVE C,P3,S=60cm/min,A=3,T=1
S22  MOVE C,P4,S=60cm/min,A=3,T=1
S23  MOVE C,P1,S=60cm/min,A=3,T=1
     ARCOF ASF#
     WEAVOF
     MULTIPASS OFF
S24  MOVE P,S=60%,A=3,T=1  
     END
```

