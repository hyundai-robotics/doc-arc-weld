# 2.2 arcoff

### 설명
```arcoff```는 Arc용접을 종료하는 명령어 입니다. 이 명령어는 2가지 형태로 사용될 수 있습니다. 단, 설정된 용접기에서 지원하지 않는 명령어는 사용할 수 없습니다.  
<br/>

### 문법

```python
arcoff
arcoff welder=<조건번호>, delay=<지연시간>
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
      <td>조건번호</td>
      <td>
        용접기를 2대 사용하는 경우 off시킬 용접기 번호를 설정합니다.
        (1 ~ 2)
      </td>
      <td>변수</td>
    </tr>
    <tr>
      <td>지연시간</td>
      <td>
        용접기를 2대 사용하는 경우 off시킬 지연시간을 설정합니다.
        (0 ~ 2)
      <td>변수</td>
    </tr>
  </tbody>
</table>  


### 사용 예

```python
    arcoff                    #특별한 종료처리 없이 Arc 용접을 종료 함
    arcoff welder=2, delay=1  #2번째 용접기 아크를 1초 후 off 
```  

### 세부 설명  

  [[5장 Arc용접 조건 편집]](../5_Condition_editing/README.md) 참고
