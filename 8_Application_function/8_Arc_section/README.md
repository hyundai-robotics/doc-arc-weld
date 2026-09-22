# 8.7 LPS(Laser Point Sensing)  

{% hint style="info" %}
해당 기능은 70.04-00 이후 버전에서 지원합니다.
{% endhint %}

arcon과 arcoff 사이 구간에서 특정 길이[mm]를 지정하고 명령어가 실행된 이후부터 그 길이만큼 전류, 전압, 용접속도, 위빙폭, 위빙주파수를 선형보간 (시작값 ~ 끝값)할 때 사용하는 기능입니다.

동작은 다음그림과 같습니다.

![](../../_assets/8_8_1.png)<br>
*그림 8.8.1 Arcsection 기능 사양*<br/>

arcsection 이 끝나면 해당 요소는 arcoff가 실행되기 전까지 e값을 유지합니다.

arcsection이 끝나기 전 다시 같은 요소의 arcsection을 실행하면 새 요소의 s값으로 값이 변경되며 선형보간됩니다.
