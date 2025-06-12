# 1.3.2 High-speed mobility function

When an Arc welding program runs, the robot's movement speed in welding sections is very slow. This leads to a significant amount of time being consumed during test runs to verify the robot's working position.

To address this, we offer a high-speed movement function that allows the robot to run through welding sections faster than their recorded speed.

{% hint style="info" %}
This function is limited to operating only during step forward/backward movements in manual mode.
{% endhint %}  

The robot's movement speed when the high-speed movement function is active is not limited by the **"Maximum speed during step forward/backward"** in the condition settings. Furthermore, you can enable or disable the high-speed movement function within a welding section, regardless of its current application status(e.g., you can disable it even while it's currently running within a welding section).

The operation method is as follows:


### Manual Max-speed Step FWD/BWD

| Item              | Description              |
| --------------- | --------------- |
| **Dedicated Key**         | `[Shift]+[FWD]` <br> `[Shift]+[BWD]` |
| **Function**          | Move the robot FWD/BWD at manual maximum speed. |

### Handling `[SHIFT]` Key Changes During High-speed Movement
|        | `[SHIFT]` Key Released During High-speed Movement | `[SHIFT]` Key Pressed During Teaching Speed Step FWD/BWD |
| ------ | --------------------- |--------------------- |
| **Operation** | Move the robot forward/backward at manual maximum speed. | Robot stops, then moves at manual maximum speed |
