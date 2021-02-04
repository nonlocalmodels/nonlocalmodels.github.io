---
layout: page
title: Restart a simulation
#permalink: /examples/
---


Sometimes it can be convenient to restart a simulation after a crash or to restricted queue limits on a cluster. 
Imagine your code ran and the output file `output_3.vtu` was succesfully writen.
By adding a new tag `Restart` to the intital configuration file and specifying the path to the last output file using 
the tag `File`. Note that you have to be careful with the `Step`, since this the step is 3*500=1500 and not 3. Note that 3 is the 
third output file which corespond to the 1500 step, since the output interval is 500. Your simulation is started from the step 1500 and all the restart values are loaded from the file `File: out/output_3.vtu`.

```yaml
Output:
 Path: out/
 Output_Interval: 500
Restart:
  File: out/output_3.vtu
  Step: 1500
```

