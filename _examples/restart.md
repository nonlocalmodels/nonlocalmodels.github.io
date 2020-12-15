---
layout: page
title: Restart a simulation
#permalink: /examples/
---


Sometimes it can be convenient to restart a simulation after a crash or to restricted queue limits on a cluster. 
Imagine your code ran until the step `53` and the output file `output_53.vtu` was succesfully writen.
By adding a new tag `Restart` to the intital configuration file and specifying the path to the last output file using 
the tag `File` and provide the `Step` to restart with, your simulation is started from the step 53 on and all the values
are loaded from this file.

```yaml 
Restart:
  File: out/output_53.vtu
  Step: 53
```

