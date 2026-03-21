# 8.5.6 LVS 搜索功能

### (1) 如何使用搜索功能

LVS 提供了一种搜索功能，可用于以下目的：

- `搜索 (search)`：搜索起始点时，TCP（工具中心点）移动到起始位置，并将要跟踪的点以设定的间隔存储在缓冲区中，为跟踪做准备。
- `step_search`：用于多次通过的焊道检测和步骤检测

当执行搜索时，系统会搜索目标，如果检测到无效点，则将最近的有效点存储为 `sp` 参数中的姿态。

随后，为了准备跟踪，系统会在 TCP 移动到找到的点时将要跟踪的点存储在缓冲区中。

通过执行搜索功能，系统准备执行“接缝跟踪”。

{% hint style="info" %}
  搜索过程检测无效的接缝（当 LVS 控制器无法检测到接缝时）并搜索起始点。
  **search** 功能找到起始（或结束），然后移动到该位置，存储要跟踪的点在缓冲区中。
{% endhint %}

```search``` 功能的使用如下：

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.1 # 如果起始位置的准确度不为 0，必须插入此行。
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs search, cnd=1, seam=1, sp=po_100
```

要配置搜索功能，请在 `lvs` 命令中输入 **[property]**，可以对搜索设置进行如下调整：

![](../../_assets/8_5_14_lvs_search_setting.png)<br>
*图 8.5.14. lvs 搜索设置*   
</br>

| 项目 | 描述 |
|------|------|
| function | 设置搜索功能的使用。 <br> 'Disable'：系统移动到 LVS 的激光位置并将目标位置存储在缓冲区中。 <br> 'Enable'：系统在搜索方向上检测起始点和结束点，然后移动到检测到的位置，同时在缓冲区中存储目标位置。 |
| distance | 如果搜索功能设置为 **enable**，则应输入搜索起始点的最大距离 [mm]。 |
| direction | 0：在 +ToolX 方向上搜索。 <br> 1：在 -ToolX 方向上搜索。 |
| speed | 搜索速度可以设置为 mm/秒。 |
| offset | 在焊接线方向上找到的点可以从检测到的位置偏移指定的毫米数。 |

<br>

![](../../_assets/8_5_15_lvs_search_example.png)<br>
*图 8.5.15. lvs 搜索示例*   
</br>

**search** 和 **seam tracking** 功能可以如以下所示进行教学。

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

---

### (2) 如何使用多次通过焊道检测功能 (step_search)

该功能用于检测多次通过焊道的起始点，其用法与 `搜索 (search)` 功能相同。

在 `lvs` 命令的 **[property]** 窗口中，将功能设置为“Enable”，并在“distance”字段中配置扫描距离。

可以如下使用：

```python
    move L, spd=60%, accu=0, tool=1 # 设置多次通过焊道检测扫描的起始点。
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs step_search, cnd=1, seam=1, sp=po_100
    move L, tg=po_100, spd=40cm/min, accu=3, tool=1 # 移动到找到的位置。
    end
```