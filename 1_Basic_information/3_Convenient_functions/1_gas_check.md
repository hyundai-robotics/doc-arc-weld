# 1.3.1 Gas Check, Wire Inching, and Wire Retract

This describes the functionality for controlling the shield gas valve and the wire feeder motor in an arc welding system. You can check the current shield gas flow rate using the gas check function. The inching and reverse inching(retreat) functions let you adjust the length of the wire protruding from the welding torch.

Here are the functions and how to use them: 

<style>
  table {
    width: auto;
    border-collapse: collapse;
    margin-bottom: 20px;
  }
</style>

### Gas Check

| Item      | Description                     |
| ------- | ---------------------- |
| **HotKey** | `[Shift]+[1]`          |
| **Dedicated Key** | User Key `GAS CHK`         |
| **Function**  | Open the shield gas valve to verify the gas flow rate |

### Wire Inching

| Item      | Description                          |
| ------- | --------------------------- |
| **HotKey** | `[Shift]+[2]`               |
| **Dedicated Key** | User Key `inching`              |
| **Function**  | Feed the wire forward out of the torch to adjust its length <li>Slow Inching: Press the key for less than 3 seconds</li> <li>Fast Inching: Press the key for 3 seconds or more</li> |

### Wire Retract

| Item      | Description                 |
| ------- | ------------------ |
| **HotKey** | `[Shift]+[3]`      |
| **Dedicated Key** | User Key `retract`     |
| **Function**  | Rewind the wire to adjust its length <li>Slow Inching: Press the key for less than 3 seconds</li> <li>Fast Inching: Press the key for 3 seconds or more</li> |
<br/>

### Inching Speed Setting
 >- Navigate to `[F2: System] - 4: Application parameter - 2: Arc welding`
 >- Within the Arc welding settings menu, Set your values for both low and high speeds: **Inching speed(%): Low=[---]%, High=[---]%**
 >- The speed is displayed as a percentage of the maximum inching speed.
 >- Depending on your specific welder model, changes to the inching speed may not be reflected.
