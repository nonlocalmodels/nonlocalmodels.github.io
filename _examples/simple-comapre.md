---
layout: page
title: Comparing two simulation results
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

Sometimes it can be convenient to compare two simulation results, e.g. for a test case to compare different simulations. Therefore, we provide
the dc compare tool. In this example we showcase the simple version to compute the $L_2$ norm of different field properties. 

The file [input_compare.yaml](https://github.com/nonlocalmodels/NLMech/tree/master/examples/qsModel/1D/input_compare.yaml) in the [example folder](https://github.com/nonlocalmodels/NLMech/tree/master/examples/qsModel/1D) will be used as an example to compare the two simulation results for testing the implementation of the material model and the quasi-static time integration. 

```yaml 
Dimension: 2
Filename_1: output_1.vtu
Filename_2: output_res.vtu
# output filename with path
Out_Filename: compare.txt
# set false if do not want to print result to std::cout
Print_Screen: false
# Tolerance for the l2 norm
Tolerance: 1e-12
# provide list of tags for which comparison has to be made
Compare_Tags:
    - Displacement
    - Force
```

Note the option `Tolerance` specifies the absolute error between the two $L_2$ norms and if the error is larger the program 
returns `EXIT_FAILURE` and this return value is captured in the [ctest](https://github.com/nonlocalmodels/NLMech/tree/master/test/CMakeLists.txt) 
to determine the result. 


## Printing the results to the screen

If the option `Print_Screen` is set to `true` following output will be printed to `std::cout`:

```yaml
Displacement_L2_Error, Displacement_Sup_Error, Force_L2_Error, Force_Sup_Error
0,0,0,0
```

## Printing the results to a file

Following output will be written to the file specified in the option `Out_Filename`:

```yaml
Displacement_L2_Error, Displacement_Sup_Error, Force_L2_Error, Force_Sup_Error
0,0,0,0
```

