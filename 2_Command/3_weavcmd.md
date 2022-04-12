# 2.3. WEAVCmd


- 설명 
    
    WEAVCmd 는 위빙 조건을 세부항목별로 외부 설정하는 명령어 입니다. 이를 통해 위빙 조건 개수 제한(32개)보다 많은 수의 위빙 조건을 설정할 수 있습니다.



- 문법
  
    - WEAVON WEV#=<위빙조건번호>	← 위빙 조건을 로딩
    - WEAVCmd.Freq=5		← 위빙 조건 중 변경할 항목을 설정 
  
</br>  

- 사용 예
  
   - ```WEAVON WEV#=1```  <span style="color: red"># 위빙 조건 1번을 로딩</span>
   - ```WEAVCmd.Freq=5``` <span style="color: red"># 위빙 조건 중 주파수만 5Hz로 변경</span>
   - ```WEAVCmd.FwdAngle=10```	<span style="color: red"># 위빙 조건 중 진행각도를 10도 변경</span>
   - ```MOVE L,S=100cm/min,A=0,T=0``` <span style="color: red"># 위의 위빙 조건대로 실행하며 로봇 이동</span>


- 세부 설명  
  [[6장 위빙기능(Weaving)]](../6_Weaving_function/README.md) 참고


</br>
</br>

{% hint style="warning" %}
[**주의**]
 -	WEAVCmd 대입문 중 일부 명령들은 위빙 동작 중 변경 시 반영이 되지 않습니다. 위빙 동작 중 변경이 가능한 명령어 목록은 [[6장 위빙기능(Weaving)]](../6_Weaving_function/README.md) 을 참고하십시오.
{% endhint %}