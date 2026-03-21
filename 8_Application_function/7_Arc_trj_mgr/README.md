# 8.7 弧轨迹管理器

此功能在弧焊过程中实时显示轨迹、电流、电压和火炬位置（焊接角度、推拉角度）。

通过此功能，您可以在弧焊过程中实时监控焊接角度、电流和电压，更容易在后期修改焊接教学。

要启用此功能，请按照以下步骤操作：

在 `[System] - 2: 应用参数 - 2: 弧焊 ([System] - 2: Application parameter - 2: Arc welding)` 下将 "Arc trajectory monitoring" 设置为 'activation on'。

{% hint style="info" %}
此功能在版本 60.30-00 及以后的版本中可用。
{% endhint %}

![](../../_assets/8_7_1_arc_trj_mgr.png)<br>
*图 8.7.1. 实时弧轨迹监测*

您可以从 `arcon` 到 `arcoff` 部分实时监控轨迹和焊接信息。

使用箭头键移动平面，或按 **[Shift] + [+/-]** 键进行缩放。

焊接角度和推拉角度是根据相对于焊接平面的焊接方向计算的。

{% hint style="info" %}
焊接平面会根据焊接轨迹自动旋转。
{% endhint %}