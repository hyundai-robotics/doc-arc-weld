# 2.2. arcoff


- 설명 
    
    arcoff Arc용접을 종료하는 명령어 입니다. 이 명령어는 4가지 형태로 사용될 수 있습니다. 단, 설정된 용접기에서 지원하지 않는 명령어는 사용할 수 없습니다.



- 문법
  
    - arcoff 
    - arcoff ASF# 
    - arcoff AEF#=<Arc용접 종료조건번호> → 아날로그 Arc용접 전용
    - arcoff C=<전류 출력 값>,V(VP)=<전압 출력 값>, AEF#=<Arc용접 종료조건번호>
  
        → 아날로그 Arc용접 전용

- 파라미터
  
   ① arcoff 조건번호
     - 내용 : Arc용접 종료 시 사용되는 용접조건의 번호
     - 범위 : 1~32
  
   ② 전류 출력 값
     - 내용 : Arc용접 종료 시 출력 전류 값
     - 범위 : 0 ~ 500 A

   ③ 전압 출력 값(V) / 전압 출력 값(VP)
     - 내용(V) : 개별설정 Arc용접 종료 시 출력전압
     - 내용(VP) : 일원설정 Arc용접 종료 시 출력전압
     - 범위(V) : 0.0 ~ 40.0 V
     - 범위(VP) : -20 ~ 200 (%)
 
</br>  

- 사용 예
  
   - ```arcoff``` <span style="color:green"> #특별한 종료처리 없이 Arc 용접을 종료 함.</span>
   - ```arcoff ASF#``` <span style="color:green">#디지털 설정인 경우 ARCON 명령에서 설정한 내용대로 용접을 종료. 조건 설정은 ARCON 명령에서만 진입 가능함. </span>
   - ```arcoff AEF#=1``` <span style="color:green">#조건파일에 설정된 조건대로 용접종료.</span>
   - ```arcoff C=200,V=22, AEF#=1``` <span style="color:green">#전류, 전압은 입력된 값으로 적용하고 그 외의 종료 조건은 지정한 조건파일의 값으로 용접종료.</span>


- 세부 설명  
  [[5장 Arc용접 조건 편집]](../5_Condition_editing/README.md) 참고


</br>
</br>

{% hint style="warning" %}
[**주의**]   
 -	디지털 용접기를 사용하기 위해서는 『시스템』 → 『5: 초기화』→ 『3: 용도설정』대화상자의 ‘아크용접’을 디지털로 설정해야 합니다.

{% endhint %}