# 8.5.5 LVS(Laser Vision Sensor) master mode 기능

(1) master mode 개요

master mode 기능은 기준 위치을 저장해 놓고 실제 양산 시 기준 위치 대비 쉬프트량을 구하는 기능입니다.

이를 위해서는 사용자키 - master mode를 활성화 하여 기준위치를 미리 등록해 두어야 합니다.

<p align="center">
 <img src="../../_assets/lvs_seamfind_mastermode.png" width="70%"></img>
 <em><p align="center">그림. lvs 센싱 자세에 따른 포즈에서의 자세</p></em>
</p>   
</br>


기준 위치에서의 센싱 프로파일 이미지 (LVS 센서가 보는 이미지)를 비교하여 에러를 검출할 수 있습니다. (Scansonic 센서만 지원)

또한 쉬프트량이 사용자가 설정한 범위 내에 존재하는지 검사할 수 있습니다.



