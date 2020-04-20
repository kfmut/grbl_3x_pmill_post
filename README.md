# grbl_3x_pmill_post

GRBL 3-axis DUCT post processor for Delcam PowerMILL

## Notes

Post processor is tested with PowerMILL 2015 R2

**G28 safe postion is ON\
Tool change M6 commands is ON\
Line numbering is ON**

Always check generated G-code before sending it to your mill!

## Motivation

Once upon a time I've found myself stuck with always in development Autodesk's Fusion 360 and turns out that my only option was to write post processor for something more reliable and time-proven.

## Output Code Example


```
N00001 G17
N00002 G21
N00003 G94
N00004 G28 G91 Z0
N00005 G90

N00006 T211 M6
...
N00047 G0 X-7.784 Y-6.022 S12000 M3
N00048 Z11.900 M8
N00049 Z1.400
N00050 G1 X-7.713 Y-6.113 Z1.399 F384
N00051 X-7.584 Y-6.272 Z1.396
...
N00151 X9.927 Y.044 Z1.100
N00152 G2 G17 X8.563 Y.218 I-.429 J2.067
N00153 G3 X7.382 Y-.484 I-.363 J-.735
N00154 G1 X7.373 Y-.622
N00155 X7.301 Y-1.198
...
N00535 G0 Z11.900
N00536 M9

N00537 M5
N00538 G28 G91 Z0
N00539 G28 G91 X0 Y0
N00540 M30
```
