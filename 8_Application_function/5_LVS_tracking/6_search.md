# 8.5.6 LVS 搜索功能

### (1) 如何使用搜索功能

LVS 提供搜索功能，主要用于以下目的：

- `搜索 (search)`：搜索起始点结束，当 TCP (Tool Center Point) 移动到起始位置时，将要跟踪的点以设定的间隔存储在缓冲区中，为跟踪做准备。
- `step_search`：用于多通道焊缝检测和步骤检测。

当进行搜索时，系统会搜索目标，如果检测到无效点，最近的有效点会作为姿态存储在 `sp` 参数中。

随后，为了准备跟踪，系统将要跟踪的点存储在缓冲区中，当 TCP 移动到找到的点时。

通过执行搜索功能，系统准备好执行“缝跟踪”。

{% hint style="info" %}
  搜索过程检测无效的焊缝（当 LVS 控制器无法检测到焊缝时）并搜索起始点。
  **搜索** 功能找到起点（或终点），然后移动到该位置，存储要跟踪的点在缓冲区中。
{% endhint %}


```search``` 功能的使用方法如下：

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.1 # 如果起始位置的精确度不是 0，则必须插入。
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs search, cnd=1, seam=1, sp=po_100
```

要配置搜索功能，请在 `lvs` 命令中输入 **[property]**，搜索设置可以按如下方式进行调整：

![](../../_assets/8_5_14_lvs_search_setting.png)<br>
*图 8.5.14. lvs 搜索设置*   
</br>

| 项目 | 描述 |
|------|------|
| function | 设置搜索功能的使用。<br> 'Disable': 系统移动到 LVS 的激光位置并将目标位置存储在缓冲区。<br> 'Enable': 系统在搜索方向上检测起始和结束点，然后移动到检测到的位置，同时将目标位置存储在缓冲区。 |
| distance | 如果搜索功能设置为 **enable**，则应输入搜索起始点的最大距离 [mm]。 |
| direction | 0: 在 +ToolX 方向搜索。<br> 1: 在 -ToolX 方向搜索。 |
| speed | 搜索速度可以设置为 mm/sec。 |
| offset | 在焊接线方向上找到的点可以从检测到的位置向指定的毫米数偏移。 |

<br>

![](../../_assets/8_5_15_lvs_search_example.png)<br>
*图 8.5.15. lvs 搜索示例*   
</br>

**搜索** 和 **缝跟踪** 功能可以如下教导。

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

### (2) 如何使用多通道焊缝检测功能 (step_search) 

此功能用于检测多通道焊缝的起始点，其使用方法与 `搜索 (search)` 功能相同。

在 `lvs` 命令的 **[property]** 窗口中，将功能设置为 "Enable" 并在 "distance" 字段中配置扫描距离。

可以如下使用：

```python
    move L, spd=60%, accu=0, tool=1 # 设置多通道焊缝检测扫描的起始点。
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs step_search, cnd=1, seam=1, sp=po_100
    move L, tg=po_100, spd=40cm/min, accu=3, tool=1 # 移动到找到的位置。
    end
```