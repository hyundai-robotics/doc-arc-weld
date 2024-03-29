﻿# 1.2.3 충돌센서 신호 설정
아크용접로봇 시스템은 토치의 변형을 방지하기 위해 충돌센서를 사용합니다. 충돌센서는 기본적으로 부논리를 사용하여 센서 케이블의 단선 등이 발생 시 바로 확인할 수 있도록 합니다.

설정 대화상자는 다음과 같습니다. 『시스템』 → 『1: 사용자 환경』 → 『6: 충돌센서』

충돌센서의 설정 항목은 다음과 같습니다.
-	센서처리: 비상정지, 정지
비상정지: 충돌센서 신호 입력 시 로봇이 모터를 off하고 비상 정지 수행
정지: 충돌센서 신호 입력 시 로봇이 모터를 On상태로 유지하고 정지 수행

-	신호논리: 충돌센서 신호의 입력 논리를 설정합니다.
정논리: 센서 미 연결 시 입력 신호가 Off 상태입니다. 충돌센서가 정논리만 지원하는 경우나 충돌 센서를 연결하지 않고 사용하는 아크용접로봇 시스템에서 설정합니다.
부논리: 센시 미 연결 시 입력 신호가 On 상태입니다. 센서 연결선이 끊어지는 경우 충돌센서 신호 입력으로 처리됩니다.

{% hint style="info" %}
[기타 항목] 
시스템의 입력신호 설정 항목에서 충돌 센서를 설정하는 경우 이 신호의 입력을 우선 확인하며 용접기 통신으로 입력되는 충돌 센서 신호 입력은 무시됩니다.
{% endhint %}