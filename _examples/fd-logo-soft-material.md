---
layout: page
title: Deformation of 2-d Logo 
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

- We consider a Peridynamic simulation of Soft material using RNP Peridynamic model (Regularized Nonlinear Peridynamic) developed and studied in [Lipton 2016](https://link.springer.com/article/10.1007/s10659-015-9564-z) and [Jha and Lipton 2018](https://doi.org/10.1137/17M1112236). RNP model is implemented in class [RNPBond](../../../src/material/pd/rnpBond.h).

- Units are SI units, e.g. length is in `meter`, mass is in `kg`, force is in `N`, and time is in `second`.

- Elastic properties of material are as follows:

	- Shear modulus `G = 35.2E+03 Pa`
	- Poisson ratio `$\nu$ = 0.25`
	- Density `$\rho$ = 1011.204 kg/$m^3$`

- Fracture properties of material are as follows:

	- Critical energy release rate `$G_c$ = 9.998E+02 J/$m^2$`

- For above elastic properties and fracture properties, we can compute the parameters in Peridynamic material model. This has been described in detail in [RNPBond::computeParameters](../../../src/material/pd/rnpBond.h).

- We consider a triangular mesh for "NLM" logo. It is contained in the box `[0, 2.75 m] x [0, 1.5 m]`. 

- Horizon is `$\epsilon$ = 0.1 m` and mesh size is `h = 0.025 m`.

- Time domain

	- Final time `T = 0.01`
	- Time steps `N = 50000`
	- Output frequency of simulation data: `N/100`

- Boundary condition

	- We apply body force along horizontal axis on whole material domain.

	- Force is given by $f_x(x,y,t) = f t sin(n\pi x/L_x)$ where `n = 3` and `f = 1.5E+09`.

- We specify `Displacement`, `Velocity`, `Force` and `Damage_Z` as output candidates. 

The complete YAML configuration file is available [here](https://github.com/nonlocalmodels/NLMech/blob/main/examples/fdModel/logo/input.yaml).

### Mesh
We obtain mesh using `Gmsh` library with mesh size `h = 0.025`. 

<p id="result" align="center">
	<img src="{{ site.url }}/assets/img/logo_mesh.png" alt="setup" width="600" height="400" />
</p>

### Results
We show damage plot at time `t = 0.008, 0.009, 0.01 seconds`. 

<p id="result" align="center">
	<img src="{{ site.url }}/assets/img/Z_fd_logo_8.png" alt="setup" width="600" height="400" />
</p>

<p id="result" align="center">
	<img src="{{ site.url }}/assets/img/Z_fd_logo_9.png" alt="setup" width="600" height="400" />
</p>

<p id="result" align="center">
	<img src="{{ site.url }}/assets/img/Z_fd_logo_10.png" alt="setup" width="600" height="400" />
</p>


Video of simulation:

<iframe width="560" height="315" src="https://www.youtube.com/embed/IrAk0uT6wvI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
