# 8.3.9 터치센싱을 이용한 위빙 폭 자동설정 아크센싱 예시


하기와 같은 두 작업물에 모두 적용할 수 있는 하나의 작업 프로그램을 생성합니다.

<p align="center">
 <img src="../_assets/4_2.png" width="60%"></img>
 <em><p align="center">그림 4.2 Butt 터치센싱, 아크센싱 작업물</p></em>
</p>

작업 환경은 다음과 같이 가정합니다.

두 작업물 사이를 용접하는 공정.
180도 평면 위빙
용접 진행방향은 X+ 방향. 작업물 터치센싱은 Y방향으로 좌우 수행
아크센싱 파라미터 설정은 기존에 완료된 것으로 가정
4.0mm gap인 경우 용접 속도는 7.0mm/sec
8.0mm gap인 경우 용접 속도는 3.5mm/sec

작업 순서는 다음과 같습니다.

1)	터치 센싱 명령어를 이용하여 종료점 Butt 부분의 용접 중심 위치, gap 거리를 측정
2)	터치 센싱 명령어를 이용하여 시작점 Butt 부분의 용접 중심 위치, gap 거리를 측정
3)	gap_var 값이 허용 값 이내인지 판단. 2.0mm ~ 10.0mm 범위를 벗어나는 경우 정지
4)	측정 된 거리의 절반을 각각 벽방향(좌측면), 타방향(우측면) 거리로 지정
5)	용접 속도는 4.0mm/sec, 8.0mm/sec 시 속도를 이용하여 보간 계산. Gap이 4.0mm보다 작으면 7.0mm/sec, 8mm를 초과하면 4.0mm/sec 고정 속도 적용
6)	계산된 값을 이용하여 위빙 폭, 용접진행속도를 자동 입력하여 작업 진행
7)	작업 진행이 완료된 후 원래 시작 위치로 복귀

<p align="center">
 <img src="../_assets/4_3.png" width="60%"></img>
 <em><p align="center">그림 4.3 Butt 터치센싱과 아크센싱</p></em>
</p>

예시프로그램은 다음과 같습니다.

~~~~~~~아크센싱 프로그램: 0002.JOB~~~~~~~~~~~~~~~ 
     'Butt 아크센싱 프로그램
     '1자리: 시작조건, 10자리: 종료조건
S1   move P,spd=60%,accu=3,tool=1  			' 1: 동작 시작점
S2   move L,spd=30%,accu=3,tool=1  			' 2: 종료점 터치센싱 위치
     var p10=cpo()
     var p1=cpo()
     var gap_var1=0
     var gap_var11=0
     touchsen cnd=2,crd="tool",dir="+ty",lift_up=5,pose=p10,gap=gap_var11		' 3: 종료점 터치센싱. P10에 위치 저장
S3   move L,spd=30%,accu=3,tool=1  			' 4: 시작점 터치센싱 위치
     touchsen cnd=3,crd="+ty",lift_up=5,pose=p1,gap=gap_var1		' 5: 시작점 터치센싱. P1에 위치 저장
     'Calc. weld speed, width according to Gap 1!	갭에 따른 속도 설정
     var V3=0
     IF gap_var1<2.0 OR gap_var1>10.0 THEN		' 허용 범위 초과
     GOTO *Error
     ELSEIF gap_var1<4.0 THEN			' 4mm 이하이면 7mm/sec로 고정
     V3=7.0 'Weld speed at start
     ELSEIF gap_var1>8.0 THEN			' 8mm 이상이면 4mm/sec로 고정
     V3=4.0 'Weld speed at start
     ELSE				'4~8mm 범위내인 경우 선형 보간으로 속도 계산
     V3=(7-3.5)/(4-8)*gap_var1+10.5 	'Linear interpolated weld speed at start
     ENDIF
     var V4=gap_var1/2.0 'left side width	'Gap 의 절반을 좌측 위빙 폭으로 지정
     var V5=gap_var1/2.0 'right side width	'Gap 의 절반을 우측 위빙 폭으로 지정
     '--------------------------------------------------------
     'Calc. weld speed, width according to Gap gap_var11
     var V13=0
     IF gap_var11<2.0 OR gap_var11>10.0 THEN		' 허용 범위 초과
     GOTO *Error
     ELSEIF gap_var11<4.0 THEN			' 4mm 이하이면 7mm/sec로 고정
     V13=7.0 'Weld speed at start
     ELSEIF gap_var11>8.0 THEN			' 8mm 이상이면 4mm/sec로 고정
     V13=4.0 'Weld speed at start
     ELSE				'4~8mm 범위내인 경우 선형 보간으로 속도 계산
     V13=(7-3.5)/(4-8)*gap_var11+10.5 	' Linear interpolated weld speed at end
     ENDIF
     var V14=gap_var11/2.0 'left side width
     var V15=gap_var11/2.0 'right side width
     '---------------------------------------------------------
S4   move L,1,S=20%,A=3,T=1		' 6: 용접 시작 점으로 이동
     weaving on, cnd=2			' 7: 위빙, 아크센싱 시작
     arcon cnd=2			' 8: 용접 시작
     arc_cond L,spd=V3,ld=V4,rd=V5,freq=2 	' 9: Start of weld parameter continuous change
S5   move L,p10,spd=60cm/min,accu=3,tool=1	'10: 용접 종료 점으로 이동
     arc_cond L,spd=V13,ld=V14,rd=V15,freq=2 '11: End of weld parameter continuous change
     arcoff				'12: 용접 종료
     weaving off				'13: 위빙, 아크센싱 종료
S6   move P,spd=60%,accu=3,tool=1  		'14: 동작 종료점
     END
     *Error				'15: 갭의 범위 이탈 시 퇴피 위치
     DO200=1			'16: 에러 표시를 위해 신호 출력
     STOP				'17: 로봇 정지
     END
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
