# 8.5.2 LVS Settings


To use LVS functionality, sensor installation and communication settings are required.

Let's now look at the process involved.

### (1) Mounting the LVS Sensor using the connection bracket

The connection bracket can either be designed and used by yourself, or you may receive one from HD Hyundai Robotics or the LVS manufacturer. <br>

<p align="center">
  <img src="../../_assets/8_5_3_lvs_mount_setup.png" width="60%"></img>
  <em><p align="center">Figure 8.5.3. LVS Mounting Precautions</p></em>
</p>

{% hint style="warning" %}
  - To achieve repetition accruacy and precision, directly mount the LVS bracket to the robot flange<br>
  - In other words, install the mechanical assembly as follows: flange - LVS mount, LVS sensor - shock sensor(if used) - torch.
{% endhint %}

The tool coordinate system should be set as follows: the welding direction opposite to the progress direction should be set as the +Tool X direction, and the wire direction should be set as the +Tool Z direction, as shown in the diagram below.

The LVS sensor must be installed so that the laser is positioned perpendicular to the welding seam, which is straight (see figure)


<p align="center">
  <img src="../../_assets/8_5_4.png" width="90%"></img>
  <em><p align="center">Figure 8.5.4. TCP and Sensor Installation, Tool Coordinate System Setup</p></em>
</p>

{% hint style="info" %}
  For instructions on setting the tool coordinate system, refer to the Tool Calibration and Angle Correction Manual(Angle Calibration) section.
{% endhint %}

{% hint style="warning" %}
  In order to use LVS, the laser should be positioned ahead of the welding direction, and the tool coordinate system must be set as shown in the diagram above.
{% endhint %}

---

### (2) Communication Settings

Connect the LVS sensor controller and the robot controller using an Ethernet cable.<br>
Navigate to **[System > 4: Application parameter > 5: LVS tracking > 1: Envrionment setting]**.<br>

In the **[Communication]** tab, configure the following items:

- LVS brand : Scansonic, Oxford (or Meta), Full-v<br>
- IP Address : Enter the IP address of the sensor controller.
- Local Port : The port for the robot controller. (For Oxford, 8000)
- Remote Port : The port for the sensor controller. (For Oxford, 8002)

After entering the above information, click **[connect]**. If the status shows "connected," the connection is successfully established.


{% hint style="info" %}
- [IP Address] : The IP address used for sending data from the LVS controller to the robot controller is set in the LVS controller.
  - If the settings are incorrect, the connection may fial. In such cases, refer to the LVS manufacturer's manual.
- [Port] : When selecting a brand, the default values will automatically be applied, so there is no need for the user to modify them.
  - If the port is incorrect, the connection may fial. In such cases, refer to the LVS manufacturer's manual.
{% endhint %}

---

### (3) Basic Settings

In the **[Tracking]** tab, configure the following items: 
- P gain : Specifies the intensity with which the TCP tracks to the converted position and orientation.
- D gain : Specifies the speed at which the TCP responds to the converted position and orientation.
- Max tracking Distance : Specifies the maximum tracking amount per second in [mm/sec].


<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Recommended Settings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">P, D gain</td>
      <td style="text-align:left">Specifies the intensity with which the TCP tracks to the converted position and orientation.</td>
      <td style="text-align:left">
        General tracking (without weaving) : Set within the range 1 ~ 10. <br>
        Weaving tracking (with weaving) : Use the default value of 10. <br>
        The default values are P gain: 10 and D gain: 10. Adjust these values to suit the actual workpiece.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Max tracking distance/sec [mm/sec]</td>
      <td style="text-align:left">Specifies the maximum tracking amount per second in [mm/sec].</td>
      <td style="text-align:left">
        Set within the range of 1 to 5. The default value is 10.<br>
        LVS seam tracking is designed to correct small deviations from the taught trajectory, so setting a larger value is not necessary.
      </td>
    </tr>
  </tbody>
</table>


Preferences have been completed through the above process.

---

#### Full-V Sensor Configuration Example

<p align="center">
 <img src="../../_assets/8_5_5_lvs_setting_fullv_1.png" width="90%"></img>
 <em><p align="center">Figure 8.5.5. Full-V Sensor Connection Settings</p></em>
</p>

As shown in the figure above, select the LVS brand as FULL, then check the IP address of the LVS sensor in the Full-V softeware.  <br>
Enter the IP in the **[System > 4: Application parameter > 5: LVS tracking > 1: Envrionment setting]** window.  <br> Afterward, click the "connect" button at the bottom and verify that the connection status shows.  <br>
If "disconnected" appears, check the hardware connection and IP address.<br>

Refer to the manual provided by Full-V and the figure below to register the seam you wish to use in the Full-V software.  


<p align="center">
 <img src="../../_assets/8_5_6_lvs_setting_fullv_2.png" width="90%"></img>
 <em><p align="center">Figure 8.5.6. Example of Seam Setting in Full-V Software</p></em>
</p>