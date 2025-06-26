# 8.5.4 LVS(Laser Vision Sensor) seam finding 기능

### (1) Seam finding 기능의 개요

이 기능은 LVS를 이용하여 센싱한 위치를 포즈로 저장하는 기능으로 터치센싱 대용으로 사용 가능합니다. 

{% hint style="warning" %}
기능 사용전 TCP-LVS 센서 캘리브레이션(8.5.3절 참조)이 수행되어 있지 않으면 비정상적인 포즈가 저장됩니다.
{% endhint %}

명령어 형식은 다음과 같습니다.  

위 명령어를 수행하면 po_100 변수에 lvs로 센싱한 위치가 저장됩니다.


```python
var po_100=cpo() # 현재 포즈를 선언한 변수 po_100에 저장함
lvs seam_find, cnd=1, seam=1, sp=po_100 # sp에 입력한 이름의 변수가 없는 경우 local pose 변수로 자동 선언됨
```


{% hint style="warning" %}
sp인자가 선언되어 있지 않다면 지역 포즈로 선언됩니다.<br>
mp인자가 선언되어 있지 않다면 전역 포즈로 선언됩니다.<br>
ms인자가 선언되어 있지 않다면 전역 쉬프트로 생성됩니다.
{% endhint %}


<p align="center">
 <img src="../../_assets/8_5_9_lvs_seamfind_ex.png" width="80%"></img>
 <em><p align="center">그림 8.5.9. lvs 센싱 자세에 따른 포즈에서의 자세</p></em>
</p>   
</br>

{% hint style="warning" %}
- seam_find 명령을 사용하여 sp 매개변수에 저장된 포즈의 자세는 센싱 전 툴의 자세(Rx, Ry, Rz)를 유지합니다.<br>
- 반면에 seam_find_p 명령어를 사용하면 sp 매개변수에 저장된 포즈에 위치만 기록됩니다.
{% endhint %}


* 센싱 전 자세와 상관없이 포즈에 위치만 저장하고 싶다면 다음과 같은 명령어 형식을 사용하십시오.<br>
이 기능은 포즈에 용접자세를 기록해 놓은 뒤 다음 위치(X,Y,Z)를 lvs로 센싱한 점으로 만들 때 사용할 수 있습니다.

```python
var po_100=cpo()
lvs seam_find_p, cnd=1, seam=1, sp=po_100
```


* 센싱한 위치에서 센싱시 툴 방향 (Tool Y, Tool Z 방향)으로 쉬프트한 포즈는 다음과 같이 계산할 수 있습니다.
위 명령어는 센싱한 위치에서 센싱시 툴의 자세로 tool_y 방향으로 10mm, tool_z 방향으로 10mm 이동된 포즈를 계산합니다.

```python
var po_100=cpo()
lvs seam_find, cnd=1, seam=1, side=10, height=10, sp=po_100
```


---

### (2) lvs seam finding 재시도 기능

Seam finding 시 seam 인식이 불가능할 경우 재시도를 수행합니다. 

재시도 횟수는 lvs명령어의 속성창에서 seam finding parameter의 no of retry 항목에 기입합니다.

재시도 횟수만큼 센싱을 시도한 뒤에도 센싱이 불가능할 경우 에러가 발생합니다.

재시도는 다음과 같은 시퀀스로 수행됩니다.

<p align="center">
 <img src="../../_assets/8_5_10_lvs_seamfind_retry.png" width="60%"></img>
 <em><p align="center">그림 8.5.10. seam finding 재시도 기능</p></em>
</p>   
</br>

{% hint style="warning" %}
* 마스터-쉬프트 기능(8.5.5절 참조)을 사용할 경우 재시도를 하면 앞뒤로 위치가 바뀌므로 유의하십시오.
{% endhint %}

---

### (3) lvs seamfinding 모니터링 기능

TP 우측의 **[창조절]** 버튼을 눌러 "LVS 용접선 탐색" 항목을 선택하면 lvs seamfinding 모니터링을 볼 수 있습니다.

<p align="center">
 <img src="../../_assets/8_5_11_seamfind monitoring.png" width="60%"></img>
 <em><p align="center">그림 8.5.11. seam finding 모니터링 기능</p></em>
</p>   
</br>
<table>
  <thead>
    <tr>
      <th style="text-align:left">항목</th>
      <th style="text-align:left">설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">위치 (X, Y, Z)</td>
      <td style="text-align:left">
        센싱한 위치를 표시합니다. (베이스 좌표계)
        사양 : 마스터 포즈의 위치입니다. 등록이 안된경우 (-1, -1, -1)로 표시됩니다.<br>
        센싱 : 현재 센싱한 위치입니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">갭</td>
      <td style="text-align:left">
      사양 : 마스터 갭 [mm]<br>
      센싱 : 현재 센싱한 갭 [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">영역</td>
      <td style="text-align:left">
      groove 나 butt 형상의 내부 영역 넓이 [mm^2]
      사양 : 마스터 넓이 [mm]<br>
      센싱 : 현재 센싱한 넓이 [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">미일치</td>
      <td style="text-align:left">
       lvs seam의 미스매치 값을 보여줍니다. 보통 좌우 형상의 높이차를 말합니다. 
      </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
갭, 영역, 미스매치 등의 값은 제조사의 lvs 컨트롤러가 지원하는 seam에 대해서만 표시됩니다.
{% endhint %}

마스터 포즈가 등록되어 있다면, 현재 JOB에서 센싱한 이력들을 prev, next를 눌러서 확인해 볼 수 있습니다.

{% hint style="info" %}
마스터모드 기능은 8.5.5 LVS master mode 기능을 참고하십시오.
{% endhint %}

