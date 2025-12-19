# 8.3.2 Arc Sensing Support Specifications


The Arc Sensing Seam Tracking does not support all welding applications.
For any issues beyond the ones listed below, please contact us for technical support.  

The specifications below are based on data obtained from extensive testing conducted by our company. 
(For conditions outside of the specified parameters, please contact us for verification tests based on the workpiece and usage conditions.)  


### (1) Welding Conditions
  - Welding Methods: CO2, MAG, MIG, FCAW  
  - Wire Diameter: 1.0 ~ 1.6 mm (Solid wire, Flux-cored wire)  
  - Maximum Welding Speed: Depending on the welder chaeracteristics (10 cm/min ~ 70 cm/min)
  - Welding Current: 160[A] ~ 600[A]  


### (2) Workpiece Conditions
  - Minimum Thickness: 2t or greater  
  - Maximum Tracking Performance: Determined by sensitivity settings and maximum correction distance per second  
     - When improving tracking performance, welding path vibrations may occur, so verification tests are required.  

### (3) Weaving Conditions  
  - Weaving Type: Single oscillation, L-type, Triangular
  - Frequency Range: 0.5 ~ 4.0 Hz(Single oscillation), 0.1 ~ 3.0 Hz(L-type, Triangular)
  - Amplitude Range: 1.0 X 1.0 mm or more(Single oscillation), 1.5 X 1.5 mm or more(L-type), 3.0 X 3.0 mm or more(Triangular)
  - Dwell Time: 0.0 ~ 2.0[sec]

{% hint style="info" %}
  Please check the communication specifications of the welding power source.
  The communication cycle for welding current and seam tracking data must be 10ms or less(e.g. EWM, Fronius).
  Arc Sensing guarantees weld seam tracking under stable welding conditions(when the current waveform is stable).
{% endhint %}

### (4) Interpolation Type
  - Linear Interpolation: Available
  - Circular Interpolation: Available
  - Positioner Synchronization (Linear): Available
  - Positioner Synchronization (Circular): Available

### (5) Joint Type
   - Fillet, V-groove  
   - Maximum Allowable Gap: Depends on weaving width

### (6) Other Functions
  - Sensing Trajectory Deviation Limiting Function
  - Torch Height Setting Function during Sensing
