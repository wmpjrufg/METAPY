---
layout: default
title: multi_point_crossover
grand_parent: Framework
parent: Genetic Algorithm functions
has_children: false
has_toc: true
nav_order: 209
---

<!--Don't delete ths script-->
<script src = "https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id = "MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<!--Don't delete ths script-->

<h3>multi_point_crossover</h3>
<br>

```python
x_i_new, of_i_new, fit_i_new, neof, report = multi_point_crossover(of_function, parent_0, parent_1, n_dimensions, x_upper, x_lower, none_variable=None)
```

<p align = "justify">This function performs the multi point crossover operator. Two new points are generated from the two parent points (offspring).</p>

Input variables
{: .label .label-yellow }

<table style = "width:100%">
   <thead>
     <tr>
       <th>Name</th>
       <th>Description</th>
       <th>Type</th>
     </tr>
   </thead>
   <tr>
       <td><code>of_function</code></td>
       <td>Objective function</td>
       <td>Py function (def)</td>
   </tr> 
   <tr>
       <td><code>parent_0</code></td>
       <td>Current design variables of the first parent</td>
       <td>List</td>
   </tr>
   <tr>
       <td><code>parent_1</code></td>
       <td>Current design variables of the second parent</td>
       <td>List</td>
   </tr>
   <tr>
       <td><code>n_dimensions</code></td>
       <td>Problem dimension</td>
       <td>Integer</td>
   </tr>
    <tr>
       <td><code>x_upper</code></td>
       <td>Upper limit of the design variables</td>
       <td>List</td>
   </tr>   
   <tr>
       <td><code>x_lower</code></td>
       <td>Lower limit of the design variables</td>
       <td>List</td>
   </tr>
   <tr>
       <td><code>none_variable</code></td>
       <td>None variable. Default is None. Use in objective function</td>
       <td>None, List, Float, Dictionary, String or any</td>
   </tr>
</table>

Output variables
{: .label .label-yellow }

<table style = "width:100%">
   <thead>
     <tr>
       <th>Name</th>
       <th>Description</th>
       <th>Type</th>
     </tr>
   </thead>
   <tr>
       <td><code>x_i_new</code></td>
       <td>Update variables of the i agent</td>
       <td>L'ist</td>
   </tr>
   <tr>
       <td><code>of_i_new</code></td>
       <td> Update objective function value of the i agent</td>
       <td>Float</td>
   </tr>
   <tr>
       <td><code>fit_i_new</code></td>
       <td>Update fitness value of the i agent</td>
       <td>Float</td>
   </tr>
   <tr>
       <td><code>neof</code></td>
       <td>New solution indicator. It is a Boolean value (1 to indicate a new solution)</td>
       <td>Integer</td>
   </tr>
   <tr>
       <td><code>report</code></td>
       <td>Report about the crossover process</td>
       <td>String</td>
   </tr>
</table>

Example 1
{: .label .label-blue }

<p align = "justify">
 <i>
 </i>
</p>

```python
from metapy_toolbox import multi_point_crossover

# Data
father1 = [1.7, 3.6, 2.7, 1.5, 1.3]
father2 = [3.9, 1.6, 2.5, 3.2, 3.3]
nDimensions = len(father1)
xUpper = [5, 5, 5, 5, 5]
xLower = [1, 1, 1, 1, 1]
noneVariable = None

# Objective function
def objFunction(x, _):
    """Example objective function"""
    x0 = x[0]
    x1 = x[1]
    of = x0 ** 2 + x1 ** 2
    return of

# Call function
xNew, ofNew, fitNew, neof, report = multi_point_crossover(objFunction, father1, father2, nDimensions, xUpper, xLower, noneVariable)

# Output details
print('x new ', xNew)
print('of new ', ofNew)
print('fit new', fitNew)
print('number of evalutions objective function', neof)
```

```bash
x new  [1.7, 1.6, 1.7, 1.6, 1.7]
of new  5.45
fit new 0.15503875968992248
number of evalutions objective function 2
```

<p align = "justify">
  To check the movement report just apply the following instruction.
</p>

```python
# Report details
arq = "report_example.txt"

# Writing report
with open(arq, "w") as file:
    file.write(report)
```

<p align = "justify">
  Open <code>report_example.txt</code>. 
</p>

```bash
    Crossover operator - multi point crossover
    current p0 = [1.7, 3.6, 2.7, 1.5, 1.3]
    current p1 = [3.9, 1.6, 2.5, 3.2, 3.3]
    cut mask = [0, 1, 0, 1, 0]
    offspring a = [1.7, 1.6, 1.7, 1.6, 1.7], of_a = 5.45
    offspring b = [3.9, 3.6, 3.9, 3.6, 3.9], of_b = 28.17
    update pos = [1.7, 1.6, 1.7, 1.6, 1.7], of = 5.45, fit = 0.15503875968992248

```
