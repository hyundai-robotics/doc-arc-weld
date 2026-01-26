# 8.1 Arccond - Arc Welding Condition DB & interpolation


Welding conditions can be stored in a database (DB) for use or interpolated during the welding process.
The usage of this function is as follows:

`[F6: cmd. input] - arcweld - arccond` to enter the command in the JOB file.

The command format is as follows:
```arccond <interpolation type>, cnd=<condition number>, gap=<gap>, spd=<welding speed>, rd=<wall direction>, ld=<sie direction>, freq=<weaving frequency>, cur=<crruent>, vol=<voltage>```


<br>

- **interpolation type**: D(stepped, immediate application) / L(Linear interpolation)
- **cnd**: condition number (WDB-welding database- and interpolation conditions can be edited via the properties window)