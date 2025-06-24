# 8.4.1 Height Sensing Condition


Press the **[Property]** key in the `heightsen` command to access the "Heigth Sensing Condition" settings screen. The condition settings screen is shown below.
 
<p align="center">
 <img src="../../_assets/8_4_2.png" width="70%"></img>
 <em><p align="center">Figure 8.4.2. Height Sensing Condition Dialog Box</p></em>
</p>

---

Each item's settings and operations are as follows:

### (1) Condition Number: [1 ~ 8]

Set the height sensing condition number.


### (2) Type of Input Data

Displays the type of input data. For GMAW, welding current is used, while for TIG welding, welding voltage is used.


### (3) Reference Data Setting: <Average Input Data, User Input Data>

Choose the method for setting the reference data.
- Average Input Data : Set the reference data based on the average value of the sensing initial reference data.
- User Input Data : Allow the user to directly enter the reference data.


### (4) Input Data Ignore Time: [0.0 ~ 5.0]

The time to ignore signals during the unstable initial welding state.
If setting reference data with "Average Input Data", this time is used to calculate the reference value using the average over the specified time.
If using "User Input data", height sensing begins immediately.


### (5) Input Data Average Time: [0.5 ~ 10.0]

Set the time to average the input data to calculate the sensing reference data.
This item appears when "Average Input Data" is selected for the reference data setting method.
(if the accurate reference height is not yet determined)


### (6) Reference Data Setting: [-500.0 ~ 500.0]

This is the item where the user directly enters the height sensing reference value. This item appears when "User Input Data" is selected for setting the reference data.


### (7) Sensing Coefficient: [-100.0 ~ 100.0]

This is the distance coefficient corresponding to the difference in the input data. A smaller value results in smoother tracking with less responsiveness to input data, while a larger value increases tracking speed but may cause oscillations along the trajectory.


### (8) Tracking Speed Limit: [0.1 ~ 10.0]

This sets the maximum tracking value per second based on sensing. A smaller value results in smoother tracking, while a larger value speeds up tracking.


<!-- ### (10) 노이즈 민감도  
    입력 데이터의 노이즈에 대한 민감도를 설정합니다. 비활성화 되어 있는 경우 지원하지 않는 버전입니다. -->

### (9) Tracking Limit Distance: [-300.0 ~ 0.0] ~ [0.0 ~ 200.0]

This sets the total tracking distance limit for height sensing.


### (10) Integral Coefficient for Error: [0.00 ~ 10.00]

This sets the correction amount for continuous error values in height sensing performance.
Setting a value greater than 0 improves tracking performance, but if the value is too large, oscillations in the trajectory may occur.
Start with a very small value and gradually adjust it to an appropriate setting for the field.


<!-- 
### (12) 초기 기준 데이터: [-500.0 ~ 500.0]
    용접 초반에 별도의 기준 데이터를 적용하려고 할 때 설정합니다. 입력 데이터 무시 시간이 지난 후 ‘초기설정된 시기준 데이터 적용 시간’에서 설정된 시간동안 이 기준 데이터를 이용하여 높이 센싱이 수행됩니다.

### (13) 초기 기준 데이터 적용 시간: [0.0 ~ 10.0]  
    초기 기준 데이터로 높이 센싱을 수행할 시간을 설정합니다. 이 시간이 지난 후에는 ‘기준 데이터 설정’ 항목에서 입력한 데이터로 높이센싱이 수행됩니다.

### (14) 입력 데이터 평균 시간: [0.5 ~ 10.0]  
    기준데이터 설정방법이 Average input data(입력데이터 평균)인 경우 표시되는 항목입니다. 입력 무시시간이 지난 후 기준데이터 계산을 위해 입력데이터를 평균하는 시간입니다.

### (15) 기준 데이터 설정: [-500 ~ 500]  
    기준데이터 설정방법이 User input data(사용자 입력데이터)인 경우 표시되는 항목입니다. 입력 무시시간이 지난 후 기준데이터 계산을 위해 입력데이터를 평균하는 시간입니다.

### (16) 높이 센싱 계수: [-100.0 ~ 100.0]  
    데이터 추종량을 계산하는데 사용하는 센싱 계수를 설정합니다. 이 값이 크면 보정할 거리가 증가하므로 추종 속도가 증가하고 진동이 발생할 수 있습니다. 이 값이 작으면 추종 속도가 감소하지만 진동이 작아집니다. 
    이 값이 0으로 설정되면 높이센싱기능이 동작하지만 위치추종은 수행하지 않고 데이터만 입력 받습니다. 센싱을 위한 기준데이터를 얻기 위한 경우 사용하십시오.

### (17) 센싱에 의한 추종속도 제한치: [0.001 ~ 5.0]  
    초당 추종 거리 제한치를 설정합니다. 이 값은 로봇의 급격한 추종을 제한하기 위하여 설정합니다. 이 값이 크면 추종 속도가 증가하고 진동이 발생할 수 있습니다. 이 값이 작으면 로봇의 추종가능 거리가 감소하지만 진동이 작아집니다. 

### (18) 높이 센싱 범위: [-300.0 ~ 0.0], [0.0 ~ 200.0]  
    높이센싱의 총 추종거리 제한치를 설정합니다. -->
