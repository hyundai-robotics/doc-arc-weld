# 8.5.1 LVS(Laser Vision Sensor) 기본설정

LVS기능을 사용하기 위해서는 통신설정 및 센서 설치가 필요합니다.<br>
지금부터 해당 과정을 살펴보겠습니다.<br><br>

(1) 통신설정

LVS센서 제어기와 로봇 제어기간에 이더넷선을 이용해 접속합니다.<br>
[System]-[Application parameter]-[LVS tracking]-[Environment setting]에 진입합니다.<br>
Communication 탭에서 다음항목을 설정합니다.

LVS 브랜드 : Scansonic, Oxford (or Meta)<br>
IP 주소 : 센서 제어기의 IP를 입력합니다.<br>
로컬 포트 : 로봇 제어기의 포트입니다. (Oxford의 경우 8000)<br>
원격 포트 : 센서 제어기의 포트입니다. (Oxford의 경우 8002)

위 내용을 입력 후 [연결] 을 눌러 '연결됨' 이라고 표시될 경우 정상 개통된 것입니다.

{% hint style="info" %}
[IP 주소] LVS제어기에서 로봇 제어기로 데이터를 보내기위한 IP설정은 LVS제어기에서 설정합니다. 이 부분은 LVS 브랜드의 메뉴얼을 참고하십시오. 포트의 경우 브랜드를 선택할 경우 디폴트 값으로 변경되므로 사용자가 수정할 필요가 없습니다.
{% endhint %}


(2) 기본설정

Tracking 탭에서 다음항목을 설정합니다. 디폴트값 사용을 권장합니다. <br>
P gain : 변환할 위치 및 방위로 TCP가 추종하는 세기를 지정합니다. <br>
D gain : 변환할 위치 및 방위에 TCP가 반응하는 속도를 지정합니다. <br>
Max tracking distance [mm/sec] : 초당 최대 추종량을 [mm]로 지정합니다. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">항목</th>
      <th style="text-align:left">권장 설정값</th>
      <th style="text-align:left">기타</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">P, D gain</td>
      <td style="text-align:left">
        일반 트래킹 (위빙 미사용) : 0.5 ~ 3 범위 내에서 설정하십시오. <br>
        위빙 트래킹 (위빙 사용) : 0.5 ~ 1.5 범위 내에서 설정하십시오.
      </td>
      <td style="text-align:left">디폴트값은 P gain 1, D gain 1 입니다. <br> 
      실제 작업물에 적합한 값을 찾아 적용하십시오.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Max tracking distance [mm/sec]</td>
      <td style="text-align:left">
        1 ~ 5 범위로 설정하십시오.
      </td>
      <td style="text-align:left">LVS 추종 기능은 기본 티칭궤적에서 벗어나는 미세한 차이를 보정해주기 위한 것이므로 이 값을 크게 놓을 필요가 없습니다.
      </td>
    </tr>
  </tbody>
</table>

위 과정을 통해 기본설정이 끝났습니다. 