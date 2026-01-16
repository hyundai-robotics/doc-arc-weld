# 8.1.2 Step Change using WDB(Welding DataBase)

```python
    arccond D, cnd=1
```

In the command above, by entering the properties window, you can view the following configuration window.

 
<p align="center">
 <img src="../../_assets/8_1_1.png" width="70%"></img>
 <em><p align="center">Figure 8.1.1. Arc Welding Condition Dialog</p></em>
</p> 

<br>

You can add or delete **cnd**(welding conditions), allowing you to store and use welding conditions in the database as follows:
    Conditions that can be stored in the DB: welding speed, current, voltage, weaving frequency, weaving width

Using this, the following JOB configuration can be created:

```python
    move L, spd=60%, ...
    move L, spd=10%, ...	    # Weld point(seam) Entry Step
    arcon cnd=1
    move L, spd=40cm/min, ...
    arccond D, cnd=1  	    # Immediately change to Welding DB Condition 1
    move L, spd=30cm/min, ...
    arcof
    end
```