# 2.14 缝合

### 描述

```stitch``` 命令执行缝合焊接。您可以通过将光标放在命令上并单击 **属性** 按钮来设置缝合条件。
在使用 `移动 (move)` 命令移动到所需的缝合焊接位置后，使用 `arcon` 命令一起进行缝合。
当缝合功能被执行时，缝合焊接从指定位置开始，并持续到缝合操作完成。  
<br/>

### 语法

```python
stitch on, cnd=<Condition Number>
stitch off
```  


### 参数

| 项目 | 说明 | 备注 |
| --- | --- | --- |
| **条件编号** | 缝合条件编号 (1 ~ 1000) | 可变 |


### 示例
```python
   stitch on, cnd=2         #  执行缝合在条件 2
   stitch off               #  终止缝合
```


### 详细信息  
  请参阅 [[8.6 STITCH Function]](../8_Application_function/6_Stitch/README.md)