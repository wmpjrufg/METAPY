---
layout: default
title: id_selection
grand_parent: Framework
parent: Common Library functions
has_toc: false
nav_order: 6
---

<!--Don't delete ths script-->
<script src = "https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id = "MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<!--Don't delete ths script-->

<h3>id_selection</h3>

<br>

<p align = "justify">
This function selects a \(k\) dimension from the all dimensions (uniform selection).
</p>

```python
selected, report = id_selection(n_dimensions, n, k_dimension=False)
```

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
       <td><code>n_dimensions</code></td>
       <td>Problem dimension</td>
       <td>Integer</td>
   </tr>
    <tr>
       <td><code>n</code></td>
       <td>Number of dimensions to select</td>
       <td>Integer</td>
   </tr>
    <tr>
       <td><code>k_dimension</code></td>
       <td>Default is False (Selects n dimensions among all dimensions). k_dimension=Integer selects n dimensions among all dimensions, excluding k dimension</td>
       <td>Integer or Boolean</td>
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
       <td><code>selected</code></td>
       <td>Selected dimensions</td>
       <td>List</td>
   </tr>
    <tr>
       <td><code>report</code></td>
       <td>Report about the selection process</td>
       <td>String</td>
   </tr>
</table>

Example 1
{: .label .label-blue }

<p align = "justify">
  <i>
  Select three dimension from five dimensions, except dimension 2.
  </i>
</p>

```python
# Import 
from metapy_toolbox import id_selection # or import *

# Data
nDimensions = 5 
n = 3

# Call function
selected, report = id_selection(nDimensions, n, 2)
print(selected)
```

```bash
[4 3 0]
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
Selection dimension operator
    probs = [0.25, 0.25, 0.0, 0.25, 0.25]
    the selected dimensions = [4 3 0]
```

Example 2
{: .label .label-blue }

<p align = "justify">
  <i>
    Select three dimension from five dimensions.
  </i>
</p>

```python
# Import 
from metapy_toolbox import id_selection # or import *

# Data
nDimensions = 5 
n = 3

# Call function
selected, report = id_selection(nDimensions, n)
print(selected)
```

```bash
[1 2 4]
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
Selection dimension operator
    probs = [0.2, 0.2, 0.2, 0.2, 0.2]
    the selected dimensions = [1 2 4]
```