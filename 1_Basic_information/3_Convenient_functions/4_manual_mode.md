# 1.3.4 Manual Mode Arc Welding

Generally, Arc Welding is only possible when the robot operates in automatic or remote mode.

Manual Mode Arc Welding is a function that allows welding even when the robot is in manual mode. This is convenient for repeatedly testing various welding conditions during setup.

To use Manual Mode Arc Welding, it should be set as below.

 (1) Go to **[System > 4: Application parameter > 2: Arc welding > Arc welding enable during manual mode]** and check enable.

 (2) Set the **[run to(execution unit)] to "End"** (the second menu on the left side of the TP).

 (3) Execute ```arcon``` using step forward.  <br/>
 * NOTE: If the robot stops during welding(before ```arcoff```) due to a paused step forward movement, ```arcon``` won't execute when you step forward again. In this case, the robot will move to the next teaching point without welding.
