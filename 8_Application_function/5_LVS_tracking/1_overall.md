# 8.5.1 LVS 개요 및 사양

{% hint style="info" %}
해당 기능은 60.30-03 이후 버전에서 지원합니다.
{% endhint %}

본 기능은 LVS (레이저비전 센서)로 용접선을 인식하여 작업물 및 지그 오차에 대한 보상을 실시간으로 반영하여 용접선 추적을 수행합니다. 

LVS는 로봇의 플렌지에 직결되어야 하며, 센서는 용접선을 인식하고, 로봇은 툴을 용접선을 실시간으로 추적합니다. 

즉, 용접선 추적을 통해 용접 대상물의 위치가 변하여 기존 교시점에서 벗어나는 경우에도 용접을 수행할 수 있습니다.


<p align="center">
 <img src="../../_assets/8_5_1.png" width="90%"></img>
 <em><p align="center">그림 8.5.1. LVS 용접선 추적 데이터 흐름도</p></em>
</p>

</br>

LVS 용접선 추적 및 검출 기능은 ```lvs``` 명령어를 통해 수행하며 TP의 **[명령입력]-[아크]-[lvs]** 를 입력하여 명령어를 입력할 수 있습니다.

명령어의 구성은 다음과 같습니다.

```python
lvs 기능인자 cnd=조건번호, seam=센싱하고자 하는 프로파일 번호, sp=센싱된 위치의 포즈변수, mp=마스터 기준 포즈변수, ms=마스터 대비 현재 센싱위치 쉬프트변수
```

<table>
  <thead>
    <tr>
      <th>대항목</th>
      <th>소항목</th>
      <th>의미</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="9">기능인자</td>
    </tr>
    <tr>
      <td style="text-align:left">laser_on</td>
      <td style="text-align:left">레이저를 켭니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">laser_off</td>
      <td style="text-align:left">레이저를 끕니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find</td>
      <td style="text-align:left">현재 센서가 센싱하고 있는 레이저의 seam 위치를 명령어의 sp인자에 지정된 포즈변수(로봇/베이스좌표계)에 저장합니다.<br>
      단, 자세(RX, RY, RZ)는 명령어 수행시 툴의 자세로 기록됩니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find_p</td>
      <td style="text-align:left">현재 센서가 센싱하고 있는 레이저의 seam 위치를 명령어의 sp인자에 지정된 포즈변수(로봇/베이스좌표계)에 저장합니다.<br>
      단, 자세(RX, RY, RZ)는 기존 포즈변수 값이 유지되며 X, Y, Z 값만 저장합니다.<br>
      intersection 등의 함수로 3점을 이용해 교점을 포즈로 찾는 경우 유용하게 사용할 수 있습니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">auto_calib</td>
      <td style="text-align:left">TCP-LVS 간 오토캘리브레이션을 수행합니다. (8.5.3절 참고)</td>
    </tr>
    <tr>
      <td style="text-align:left">search</td>
      <td style="text-align:left">+ToolX, -ToolX 방향으로 이동하면서 시작점을 찾고 트래킹 준비를 수행합니다.<br>
      찾은 시작점은 명령어의 sp인자에 지정된 포즈변수에 저장됩니다.(8.5.6절 참고)</td>
    </tr>
    <tr>
      <td style="text-align:left">step_search</td>
      <td style="text-align:left">+ToolX, -ToolX 방향으로 이동하면서 시작점 또는 다단비드의 시작점 등을 찾습니다.<br>
      찾은 시작점은 명령어의 sp인자에 지정된 포즈변수에 저장됩니다.(8.5.6절 참고)</td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">search가 완료된 후 arcon 및 weaving on 이 수행된 뒤 실행되어야 합니다.
      arcoff를 만날때 까지 트래킹을 수행합니다.</td>
    </tr>
    <tr>
      <td colspan="2">조건번호</td>
      <td>
        lvs 명령어의 속성 창에 설정된 내용을 사용하기 위한 조건번호입니다. 속성창에서 탐색속도, 탐색길이, 큐간격, 추종제한치, 센싱좌표계(로봇/베이스) 등을 설정할 수 있습니다.
      </td>
    </tr>
  <tr>
      <td colspan="2">센싱하고자 하는 프로파일 번호</td>
      <td>
        LVS 제어기에 사용자가 등록한 센싱형상 및 센싱조건에 해당하는 번호입니다. 명령어 수행시 LVS제어기는 이 번호에 대한 센싱형상 및 조건을 load 합니다.
      </td>
    </tr>
    <tr>
      <td colspan="2">센싱된 위치의 포즈변수</td>
      <td>
        현재 레이저의 위치에 해당하는 위치를 포즈변수로 저장합니다.
      </td>
    </tr>
    <tr>
      <td colspan="2">마스터 기준 포즈변수</td>
      <td>
        마스터 모드에서 등록된 기준 포즈변수입니다. (8.5.5절 참고)
      </td>
    </tr>
    <tr>
      <td colspan="2">마스터 대비 현재 센싱위치 쉬프트변수</td>
      <td>
        mp 대비 현재 센싱한 위치의 쉬프트가 저장됩니다. (8.5.5절 참고)
      </td>
    </tr>
  </tbody>
</table>  
<br/>

---

```lvs``` 명령어를 이용한 트래킹기능은 다음과 같이 사용할 수 있습니다.

<p align="center">
 <img src="../../_assets/8_5_2.png" width="60%"></img>
 <em><p align="center">그림 8.5.2. LVS 용접선 추적을 위한 티칭 방법</p></em>
</p>


---

LVS 기능 사양

* 일반 모션 트래킹 기능 지원 (직선 L보간, 원호 C보간, 직선 및 원호 복합 구간)<br>
* 위빙 트래킹 기능 지원 (0.5Hz ~ 3Hz)<br>
* 포지셔너 동기 트래킹 기능 지원 (SMOV 구간)<br>
* 포지셔너 동기 + 위빙 트래킹 기능 지원 (0.5Hz ~ 3Hz)<br>

<table>
  <thead>
    <tr>
      <th style="text-align:left">항목</th>
      <th style="text-align:left">제조사</th>
      <th style="text-align:left">반복 정확도</th>
      <th style="text-align:left">반복 정밀도</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">seam_find / seam_find_p</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">좌우 : 0.1 mm (기준 +- 30mm 높이),  0.4mm<br>높이 : 0.4mm (기준 +- 30mm 높이), 2mm<br>앞뒤 : 0.4mm (기준 +- 30mm 높이), 1.5mm</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find / seam_find_p</td>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">좌우 : 0.4 mm (기준 +- 30mm 높이),  0.7mm<br>높이 : 0.6mm (기준 +- 30mm 높이), 3mm<br>앞뒤 : 0.6mm (기준 +- 30mm 높이), 2.5mm</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find / seam_find_p</td>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">좌우 : 0.6 mm (기준 +- 30mm 높이),  2mm<br>높이 : 0.8mm (기준 +- 30mm 높이), 4.5mm<br>앞뒤 : 0.6mm (기준 +- 30mm 높이), 4mm</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">0.2mm (직선)<br>0.4mm (위빙)<br>0.25mm (포지셔너 동기)<br>0.5mm (위빙 + 포지셔너동기)</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">0.3mm (직선)<br>0.5mm (위빙)<br>0.4mm (포지셔너 동기)<br>0.6mm (위빙 + 포지셔너동기)</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">0.3mm (직선)<br>0.6mm (위빙)<br>0.4mm (포지셔너 동기)<br>0.7mm (위빙 + 포지셔너동기)</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
  </tbody>
</table>