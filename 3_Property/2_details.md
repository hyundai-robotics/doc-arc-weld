# 3.2 상세 내용

각 명령문에서 [**속성**] 버튼을 누를 때 나타나는 내용은 다음과 같습니다.

<style>
  table th,
  table td {
    text-align: left;
  }
</style>

<table>
  <thead>
    <tr>
      <th>항목</th>
      <th>내용</th>
      <th>상세</th>
      <th>비고</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>move</th>
      <td>기록된 위치</td>
      <td>
        - 현 위치 (로봇좌표계, 베이스좌표계, 축좌표계, 엔코더 등)<br>
        - X Y Z(mm) Rx Ry Rz(deg)<br>
        - 로봇 Configuration
      </td>
      <td>지령치 수정 가능</td>
    </tr>
    <tr>
      <th>대입문</th>
      <td>변수 확인 및 변경</td>
      <td>
        변수 유형에 따라 해당 변수를 모니터링하고 값을 변경
      </td>
      <td></td>
    </tr>
    <tr>
      <th>arcon</th>
      <td>
        용접 조건 확인 및 변경<br>
        - 용접 시작조건<br>
        - 용접 본조건<br>
        - 용접 보조조건<br>
        - 용접 종료조건<br>
      </td>
      <td>
        - 용접시작 및 본조건 <br>
        조건번호, 설명, 시너직 코드, 가스예출, 전류/송급속도, 용접전압(보정)/ Arc길이, WCR 대기시간, 로봇지연시간, ...<br><br>
        - 용접보조조건  <br>
        - 재시도: 횟수, 재시도조건, 동작모드, 속도, Retract시간, Retract속도, 후퇴/용접선 이동량, 시프트 이동량<br>
        - 재기동: 횟수, 재기동조건, 중첩량, 이동속도, 용접속도<br><br>
        - 용접종료조건<br>
        - 전류비율, Downslope시간, 조건 유지시간, 가스후출, ...<br>
        - 용접보조조건(종료조건 진입)<br>
        - 자동 용착 해제: 횟수, 용착해제 조건, 조건유지시간 <br>
      </td>
      <td></td>
    </tr>
    <tr>
      <th>weaving on</th>
      <td>
        위빙 조건 확인 및 변경
      </td>
      <td>
        조건번호, 위빙형태, 주파수, 기본패턴, 진행각도, 경계제한, 이동시간, 타이머
      </td>
      <td></td>
    </tr>
    <tr>
      <th>refp</th>
      <td>
        참조점 확인 및 변경
      </td>
      <td>
        현 위치, 지령치<br>
        - X Y Z(mm) Rx Ry Rz(deg) 로봇 Configuration
      </td>
      <td>
        지령치 수정 가능<br>
        “위치”화면과 동일
      </td>
    </tr>
    <tr>
      <th>lvs</th>
      <td>
        LVS 조건 확인 및 변경
      </td>
      <td>
        기능 설정
    - 조건번호, Joint형상, 동작모드, 시작점 검출, 용접점 파인딩 설정
  - 탐색 조건 
    - 탐색량 [mm], 탐색방향 (+tx, -tx), 탐색속도 (mm/s)
      </td>
      <td></td>
    </tr>
    <tr>
      <th>heightsen</th>
      <td>
        높이센싱 조건 확인 및 변경
      </td>
      <td>
        조건번호, Input data type for height sensing, Reference data setting method, ...
      </td>
      <td></td>
    </tr>
    <tr>
      <th>arccond</th>
      <td>
        용접조건 데이터베이스
      </td>
      <td>
        용접속도, 전류, 전압, 위빙 폭, 위빙 주파수로 이루어진 데이터 베이스 확인 및 편집
      </td>
      <td></td>
    </tr>
    <tr>
      <th>touchsen</th>
      <td>
        터치센싱 기능 설정
      </td>
      <td>
        용접속도, 전류, 전압, 위빙 폭, 위빙 주파수로 이루어진 데이터 베이스 확인 및 편집
      </td>
      <td></td>
    </tr>
  </tbody>
</table>

