# 2.10 LVSON

- 설명 
    
    LVSON문은 LVS 용접선 추종 기능을 시작하는 명령어입니다.

- 문법
  
    - LVSON COND#=<조건 번호>,OPT=<옵션>,SN=<seam번호>



- 파라미터
  
   ① LVS조건 번호
     - 내용 : LVS 기능 실행 시 사용되는 LVS조건 번호
     - 범위 : 1~32
   
   ② 옵션
     - SEAMF : 심파인딩
     - TRK : 트래킹
     - EPS : 종료점 우선탐색

   ③ SN
     - 내용 : 심번호, LVS컨트롤러에 전달할 번호, LVS는 해당 seam번호의 seam point정보를 제어기로 전송함.
 
</br>  

- 사용 예
  
   - ```LVSON COND#=1,OPT=SEAMF,SN=10``` 조건번호 1번, seam번호 10번으로 seam 파인딩 기능 수행
   - ```LVSON COND#=1,OPT=TRK,SN=10``` 조건번호 1번, seam번호 10번으로 LVS 용접선 추종 시작




- 세부 설명
  
  •	옵션 기능으로 사용을 위해서는 당사에 문의하시기 바랍니다.
