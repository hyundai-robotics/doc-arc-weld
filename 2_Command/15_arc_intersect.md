# 2.15 arc_intersect


{% hint style="info" %}
해당 기능은 70.04-00 이후 버전에서 지원합니다.
{% endhint %}


### 설명  

```arc_intersect``` 문은 아크 응용에서 마스터모드/양산모드를 적용하기 위한 명령어입니다. 기존 intersection 함수와 사용 방법은 같고 마스터모드 on/off에 따라 파라미터에 값이 처리됩니다.
<br/>


### 문법  

```py
  arc_intersect sp=<저장할 포즈>,crd=<좌표계>,mp=<마스터포즈>,ms=<마스터포즈 대비 시프트>,p1=<직선 참조 포즈1>,p2=<직선 참조 포즈2>,p3=<직선 참조 포즈3>
  arc_intersect sp=<저장할 포즈>,crd=<좌표계>,mp=<마스터포즈>,ms=<마스터포즈 대비 시프트>,p1=<직선 참조 포즈1>,p2=<직선 참조 포즈2>,p3=<직선 참조 포즈3>,p4=<직선 참조 포즈4>
```  

### 파라미터

<table>
  <thead>
    <tr>
      <th>항목</th>
      <th>의미</th>
      <th>기타</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>sp</td>
      <td>
        명령어 수행 시 저장할 포즈 변수
      </td>
      <td>포즈변수</td>
    </tr>
    <tr>
      <td>crd</td>
      <td>
        시프트 변수가 계산될 때 좌표계("base", "robo", "tool")
      </td>
      <td>문자열</td>
    </tr>
    <tr>
      <td>mp</td>
      <td>
        마스터모드에서는 sp와 같은 값이 저장되며, 양산모드에서 ms를 계산할 때 사용
      </td>
      <td>포즈 변수</td>
    </tr>
    <tr>
      <td>ms</td>
      <td>
        양산모드에서 사용되는 시프트 변수로, mp와 sp의 차이가 설정된 좌표계로 계산
      </td>
      <td>시프트 변수</td>
    </tr>
    <tr>
      <td>p1 ~ p4</td>
      <td>
        직선을 만드는 3개 혹은 4개의 점으로 다음 링크를 참고합니다.
        [로봇언어 intersection 함수](https://hrbook-hrc.web.app/#/view/doc-hrscript/ko/10-etc/2-func/3-intersection?cont_model=${cont_model})  
      </td>
      <td>포즈 변수</td>
    </tr>
  </tbody>
</table>   

### 사용 예
```python
  lvs seam_find, cnd=1, seam=10, sp=p1  # 찾은 점을 p1에 저장
  lvs seam_find, cnd=1, seam=10, sp=p2  # 찾은 점을 p2에 저장
  lvs seam_find, cnd=1, seam=10, sp=p3  # 찾은 점을 p3에 저장

  arc_intersect sp=p10,crd="robot",mp=mp10,ms=ms10,p1=p1,p2=p2,p3=p3
  # p1~p3로 계산된 점을 p10에 저장, 마스터모드 여부에 따라 mp10 과 ms10 저장
```  
  