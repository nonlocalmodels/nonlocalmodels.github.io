---
layout: page
title: Generating a simple regular mesh
#permalink: /examples/
---


Sometimes it can be convenient to create a simple regular mesh. The file yaml file below will be used as an example to generate a regular mesh. 

```yaml 
Output:
  Path: .
  Mesh: mesh
  File_Format: vtu
Domain: [0.000000e+00, 0.000000e+00, 1.000000e+01, 1.000000e+01]
Mesh_Size: 1.000000e-01
Horizon: 4.400000e-01
Mesh_Type: uniform_square
Compress_Type: zlib
Is_FD: true
```

Using the [mesh tool](https://github.com/nonlocalmodels/NLMech/blob/master/tools/mesh/mesh.cpp) and running

```bash
mesh -i mesh.yaml -d 2
```

will generate the regular mesh in the figure where the nodes are colored with the nodal volume. 

<p id="mesh" align="center">
    <img src="{{ site.url }}/assets/img/tool-mesh.png" alt="setup"  />
</p>
