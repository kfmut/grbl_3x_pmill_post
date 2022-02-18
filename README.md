# grbl_3x_pmill_post

GRBL 3-axis DUCT post processor for Delcam PowerMILL

## Notes

Post processor is tested with PowerMILL 2015 R2

**G28 safe postion is ON\
Tool change M6 commands is ON\
Line numbering is ON**

Always check generated G-code before sending it to your mill!

[2022-02-18] - BEWARE: first toolchange position now is explicitly specified at SafeZ height and first toolpath's starting point X/Y-wise.


## Motivation

Once upon a time I've found myself stuck with always in development Autodesk's Fusion 360 and turns out that my only option was to write post processor for something more reliable and time-proven.

## Output Code Example


```
N00001 G17
N00002 G21
N00003 G94
N00004 G28 G91 Z0
N00005 G90

N00006 G0 X-3.603 Y57.005
N00007 Z14.000
N00008 T241 M6
...
N00049 G0 X-3.603 Y57.005 S6000 M3
N00050 Z14.000
N00051 Z0.450
N00052 G1 Z0.200 F220
N00053 X-3.595 Y57.002 F640
N00054 G3 G17 X-3.500 Y57.046 I0.026 J0.070
N00055 G1 X-2.241 Y60.430 F960
N00056 G3 X-2.090 Y61.949 I-2.812 J1.046 F640
N00057 G0 Z7.109
...
N03446 M5
N03447 G28 G91 Z0
N03448 G28 G91 X0 Y0
N03449 M30
```
