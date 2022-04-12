# 2.7. ARCVOL  


- 설명 
    
    ARCVOL문은 용접전압 출력 값을 지정한 값으로 설정합니다. 용접기의 종류에 따라 지정하는 값이 달라집니다.



- 문법
    - ARCVOL V(VP)=<전압값>
  
- 파라미터
  
   ① 전압값(V)
     - 내용 : Arc 용접 본 용접에 사용할 전압 출력 값
     - 범위 : 0.0 ~ 40.0 V
  
   ② 전압값(VP)
     - 내용 : Arc 용접 시 시너직 전압 %  (단, GB2, GZ4, GE2의 경우 시너직 전압의 옵셋 전압 값)
     - 범위 : -200 ~ 200 V(%)
     
</br>  

- 사용 예
  
   - ```ARCVOL V=20```
   - ```ARCVOL VP=100```  <span style="color: green"># 시너직 전압값 100%</span>
   - ```ARCVOL VP=2```    <span style="color: green"># 기준 시너직전압에 옵셋 전압 +2V (GB2, GZ4, GE2인 경우)</span>



