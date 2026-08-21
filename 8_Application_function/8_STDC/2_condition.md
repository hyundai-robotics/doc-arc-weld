# 8.8.2 명령어 및 속성  


본 기능을 위한 프로그램은 별도의 라이선스를 통해 제공됩니다. 제공되는 프로그램에서 관련 명령어를 자동으로 수행하므로 사용자가 직접 명령어를 작성할 필요는 없습니다.

본 장에서는 툴 자동 보정에 사용되는 명령어와 시스템 변수의 주요 기능을 설명하고, 기능 사용을 위해 설정해야 하는 명령어 속성에 대해 설명합니다.  

### (1) 명령어

```py
    stdc cen=<포즈1>,cenup=<포즈2>,opt=<옵션>
```

#### cen, cenup

센서 측정을 통해 추정된 툴의 중심 포즈를 저장합니다.  
- `cen`: 기준 높이에서 측정한 중심 포즈를 저장합니다.
- `cenup`: 기준 높이에서 z 방향으로 이동한 위치에서 측정한 중심 포즈를 저장합니다.  


#### opt

`stdc` 명령어가 수행할 동작을 옵션 번호로 지정합니다.  

<table>
  <thead>
    <tr>
      <th>예시</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <code class="language-python">stdc cen=po1,opt=10</code>
      </td>
      <td style="text-align:left">수집된 데이터를 기반으로 추정한 중심 포즈를 cen에 저장합니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <code class="language-python">stdc cenup=po2,opt=11</code>
      </td>
      <td style="text-align:left">
        수집된 데이터를 기반으로 추정한 중심 포즈를 cenup에 저장합니다. opt=10과 서로 다른 높이에서 측정해야 합니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <code class="language-python">stdc cen=po1,cenup=po2,opt=3</code>
      </td>
      <td style="text-align:left">
        cen과 cenup에 저장된 중심 포즈를 이용하여 툴의 각도 변형량을 계산합니다. 설정된 측정 모드에 따라 관련 속성이 갱신되며 툴 데이터가 변경될 수 있습니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <code class="language-python">stdc opt=5</code>
      </td>
      <td style="text-align:left">
        센서에 정렬된 툴을 센서 좌표계의 z 방향으로 이동하여 툴 끝단을 센서 중심에 위치시킵니다. 기준 등록 모드에서는 추가 동작을 수행하여 기준 자세를 저장합니다.
      </td>
    </tr>
  </tbody>
</table>  


### (2) 시스템 변수

명령어를 수행하는 것 외에 추가로 설정해주어야 하는 값들이 있습니다.

<table>
  <thead>
    <tr>
      <th>항목</th>
      <th>설명</th>
      <th>예시</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">_stdc.gather</td>
      <td style="text-align:left">
        측정 데이터를 수집할지 여부를 설정합니다. 활성화된 동안 현재 툴 정보와 센서 입력값을 수집합니다.
      </td>
      <td style="text-align:left"><pre>
        <code class="language-python">_stdc.gather=1</code>
      </pre></td>
    </tr>
    <tr>
      <td style="text-align:left">_stdc_cnd.crd_no</td>
      <td style="text-align:left">
        현재 툴에 설정된 센서 좌표계 번호를 나타냅니다.
      </td>
      <td style="text-align:left">
        <code class="language-python">var ucrd_no=_stdc_cnd.crd_no</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">_stdc_cnd.ref_tool</td>
      <td style="text-align:left">
        기준 등록 시 저장된 레퍼런스 툴 데이터를 나타냅니다. 자동 캘리브레이션이 완료된 변형 전 툴 데이터가 저장됩니다.
      </td>
      <td style="text-align:left">
        <code class="language-python">var ref_tool=_stdc_cnd.ref_tool</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">_stdc_cnd.measurement_mode</td>
      <td style="text-align:left">
        현재 설정된 측정 모드를 나타냅니다.
      </td>
      <td style="text-align:left">
        <code class="language-python">_stdc_cnd.measurement_mode==1</code>
      </td>
    </tr>
  </tbody>
</table>  

특히 `_stdc.gather`는 다음과 같이 로봇 동작 전/후에 설정하여 측정 구간을 지정합니다.  
```py
    _stdc.gather=1 #게더링 시작
S1  move C,tg=po1,spd=10mm/sec,acc=0,tool=0
S2  move C,tg=po2,spd=10mm/sec,acc=0,tool=0
    _stdc.gather=0 #게더링 종료
```


### (3) 속성

![](../../_assets/8_8_2_1.png)<br>
*그림 8.8.2.1. 명령어 속성*

명령어 속성에서는 툴 자동 보정에 필요한 설정값과 기능 수행을 통해 생성된 데이터를 확인하고 관리할 수 있습니다.  


#### Default

툴 자동 보정 기능 수행에 필요한 항목을 설정합니다.  

<table>
  <thead>
    <tr>
      <th>항목</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">측정 모드</td>
      <td style="text-align:left">
        수행할 동작 모드를 설정합니다. 최초 기준 데이터를 등록할 때는 "기준 등록"으로 설정하고, 이후 툴 보정을 수행할 때는 "보정"으로 설정합니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">기준 등록 완료</td>
      <td style="text-align:left">
        기준 등록 상태를 나타냅니다. 초기값은 -1이며, 기준 등록이 완료되면 1로 표시됩니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">신호 포트 (X/Y)</td>
      <td style="text-align:left">
        센서가 연결된 제어기의 신호 포트를 설정합니다.센서의 X축과 Y축에 해당하는 포트를 순서대로 입력합니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">센서 좌표계</td>
      <td style="text-align:left">
        센서 좌표계로 사용할 사용자 좌표계 번호를 설정합니다. 툴 자동 보정과 관련된 위치 및 각도 계산은 설정된 좌표계를 기준으로 수행됩니다.
      </td>
    </tr>
  </tbody>
</table>  


#### 레퍼런스

기준 등록 시 저장되는 기준 툴 데이터를 나타냅니다.

<table>
  <thead>
    <tr>
      <th>항목</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">길이</td>
      <td style="text-align:left">
        기준 등록 시 자동 캘리브레이션이 완료된 툴 데이터의 길이를 저장합니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">각도</td>
      <td style="text-align:left">
        기준 등록 시 자동 캘리브레이션이 완료된 툴 데이터의 각도를 저장합니다.
      </td>
    </tr>
  </tbody>
</table>  


#### 센서 좌표계

기준 등록이 완료되면 센서에 대한 다음 항목이 자동으로 저장됩니다.

<table>
  <thead>
    <tr>
      <th>항목</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">중심</td>
      <td style="text-align:left">
        센서의 X/Y 축이 교차하는 센서 중심 위치를 베이스 좌표계 기준으로 저장합니다.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">각도</td>
      <td style="text-align:left">
        센서 좌표계의 자세를 베이스 좌표계 기준으로 저장합니다.
      </td>
    </tr>
  </tbody>
</table>  

