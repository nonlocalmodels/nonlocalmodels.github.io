---
layout: page
title: Deformation of 2-d Logo - 2
#permalink: /examples/
---
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      tex2jax: {
        skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
        inlineMath: [['$','$']]
      }
    });
  </script>
  <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
  
  <center> Note that this example here shows no real scientific application and its purpose was to generate the code's logo. </center> 


- The setup is same as in the [first Logo example](fd-logo-soft-material.html) except the boundary condition. 

- Boundary condition

	- We apply body force along horizontal axis on whole material domain.

	- Force is given by $f_x(x,y,t) = f t sin(n\pi x/L_x)$ where `n = 3` and `f = 1.5E+09`.

	- We apply body force along vertical axis on whole material domain.

	- Force is given by $f_y(x,y,t) = f t sin(n\pi y/L_y)$ where `n = 2` and `f = 1.5E+09`.

- We specify `Displacement`, `Velocity`, `Force` and `Damage_Z` as output candidates. 

The complete YAML configuration file is available [here](https://github.com/nonlocalmodels/NLMech/blob/main/examples/fdModel/logo2/input.yaml).

### Mesh
We obtain mesh using `Gmsh` library with mesh size `h = 0.025`. 

<p id="result" align="center">
	<img src="{{ site.url }}/assets/img/logo_mesh.png" alt="setup" width="600" height="400" />
</p>

### Results
We show damage plot at time `t = 0.008, 0.009, 0.01 seconds`. 

<p id="result" align="center">
	<img src="{{ site.url }}/assets/img/Z_fd_logo_2_8.png" alt="setup" width="600" height="400" />
</p>

<p id="result" align="center">
	<img src="{{ site.url }}/assets/img/Z_fd_logo_2_9.png" alt="setup" width="600" height="400" />
</p>

<p id="result" align="center">
	<img src="{{ site.url }}/assets/img/Z_fd_logo_2_10.png" alt="setup" width="600" height="400" />
</p>


Video of simulation:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ecddv7XvBgI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
