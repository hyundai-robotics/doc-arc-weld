# 8.5.1 LVS(Laser Vision Sensor) 기본설정

LVS기능을 사용하기 위해서는 통신 설정 및 센서 설치가 필요합니다.<br>
지금부터 해당 과정을 살펴보겠습니다.<br><br>

1) 통신설정<br>
LVS센서 제어기와 로봇 제어기간에 이더넷선을 이용해 접속합니다.<br>
[System]-[Application parameter]-[LVS tracking]-[Environment setting]에 진입합니다.<br>
Communication 탭에서 다음항목을 설정합니다.<br><br>

LVS 브랜드 : Oxford(Meta), Scansonic(향후 지원예정)<br>
IP 주소 : 센서 제어기의 IP를 입력합니다.<br>
로컬 포트 : 로봇 제어기의 포트입니다. (Oxford의 경우 8000)<br>
원격 포트 : 센서 제어기의 포트입니다. (Oxford의 경우 8002)<br><br>

2) 기본설정<br>
Tracking 탭에서 다음항목을 설정합니다. 디폴트값 사용을 권장합니다.<br>
P gain : 변환할 위치 및 방위로 TCP가 추종하는 세기를 지정합니다.<br>
D gain : 변환할 위치 및 방위에 TCP가 반응하는 속도를 지정합니다.<br>
Max tracking distance/sec : 초당 최대 추종량을 [mm]로 지정합니다.<br>

위 과정을 통해 기본설정이 끝났습니다. 