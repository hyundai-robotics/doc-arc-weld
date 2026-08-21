# 2.16 stdc


### 설명

```stdc``` 문은 툴 자동 보정 기능을 위한 명령어입니다. 본 기능은 각 명령어보다 여러 동작을 통해 수행됩니다.
<br/>


### 문법
  
```python
    stdc cen=<포즈1>,cenup=<포즈2>,opt=<옵션>
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
      <td>cen(포즈1)</td>
      <td>
        센서를 통해 얻어진 중심 포즈가 저장될 변수를 지정합니다.<br>
        옵션 번호가 <b>10</b> 또는 3일 때, 사용됩니다.
      </td>
      <td>포즈 변수</td>
    </tr>
    <tr>
      <td>cenup(포즈2)</td>
      <td>
        센서를 통해 얻어진 중심 포즈가 저장될 변수를 지정합니다.<br>
        옵션 번호가 <b>11</b> 또는 3일 때, 사용됩니다.
      </td>
      <td>포즈 변수</td>
    </tr>
    <tr>
      <td>옵션</td>
      <td>
        툴 보정 기능 수행 간 사용되는 옵션 번호입니다.<br>
        (10, 11, 3, 5)
      <td>변수</td>
    </tr>
  </tbody>
</table>


### 사용 예

```python
    stdc cen=po1,opt=10
    stdc cenup=po2,opt=11
    stdc cen=po1,cenup=po2,opt=3
    stdc opt=5
```  

{% hint style="info" %}
옵션 기능으로 사용을 위해서는 당사에 문의하시기 바랍니다.
{% endhint %}


### 세부 설명

[8.8 STDC(Sensor-based Tool Data Correction)](../8_Application_function/8_STDC/README.md) 참고
