# 8.1.1 Step Change using Command Factors

The stepped change function can be used in the command arguments as follows:

| Method | Example |
| :--- | :--- |
| Changing IV(Current, Voltage) |move L, spd=60%, …<br/>move L, spd=10%, …   <span style="color: green"> # Weld point(seam) Entry Step </span> <br>    arcon cnd=1  <br>    move L, spd=40cm/min, ... <br>   <b>  arccond D, cur=175, vol=20 </b>  <span style="color: green"> # Change current to 175A, voltage to 20V </span> <br>   move L, spd=30cm/min, …  <br>    arcof <br>   end |
| Changing Welding Speed and Weaving Parameter | move L, spd=60%, …  <br>   move L, spd=10%, …    <span style="color: green"> # Weld point(seam) Entry Step  </span> <br> weaving on, cnd=1 <br>   arcon cnd=1   move L, spd=40cm/min, … <br> <b>  arccond D, spd=80, rd=20, ld=10, freq=1.5, cur=175, vol=20 </b> <br> <span style="color: green">  # Change welding speed to 80cm/min, weaving width to 20/10mm, frequency to 1.5HZ, current to 175A, and voltage ot 20V </span> <br>  move L, spd=30cm/min, …  <br>   weaving off <br>   arcof  <br> end |