# 2.9 heightsen on

### Description 

```heightsen on``` command starts the height sensing function(AVC, Arc length control).  


### Syntax
```python
    heightsen on, cnd=<Condition Number>
    heightsen on, cnd=<Condition Number>, crd=<Coordinate System>, dir=<Direction>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Condition Number** | The number of the welding condition used to starting Arc Welding and the specific condition (1 ~ 8) | Variable |
| **Coordinate System** | Coordinate system used to define height direction ("base", "tool", "user") | Default: Tool +Z direction |
| **Direction** | Height direction("+x", "+y", "+z") | Default: Tool +Z direction |

### Example
```python
   # Start height sensing using condition No. 1 in tool +z direction
   heightsen on, cnd=1        
```  
```python   
   # Start height sensing using condition No. 1 in base +x direction
   heightsen on, cnd=1, crd="base", dir="+x"  
```  
```python  
   # Start height sensing using condition No. 1 in user coordinate system 1 -z direction 
   heightsen on, cnd=1, crd="user_1", dir="-z"  
```  

### Details
  Refer to [[8.4 Height Sensing]](../8_Application_function/4_Height_sensing/README.md)


