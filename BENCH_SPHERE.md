---
layout: default
title: sphere
grand_parent: Benchmark
parent: Mathematical Functions
has_children: false
has_toc: false
nav_order: 1
---

<!--Don't delete ths script-->
<script src = "https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id = "MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<!--Don't delete ths script-->

<h3>sphere</h3>

<br>

<p align="justify">
  The sphere function has \(d\) local minima except for the global one. It is continuous, convex and unimodal <a href="#ref1">[1]</a>.
</p>

```python
of = sphere(x)
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
        <td><code>x</code></td>
        <td>Current design variables of the i agent.</td>
        <td>List</td>
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
        <td><code>of</code></td>
        <td>Objective function value of the i agent.</td>
        <td>Float</td>
    </tr>
</table>

<h3>Problem</h3>

<table style = "width:100%">
    <tr>
        <td style="width: 90%;">\[f(\mathbf{x}) = \sum_{i=1}^{n} x_{i}^{2}\]</td>
        <td style="width: 10%;"><p align = "right">(1)</p></td>
    </tr>
    <tr>
        <td style="width: 90%;">\[  x_{i} \in [-5.12, 5.12], i = 1,..., d;  \;...\;    f(\mathbf{x}^*) = (0,..,0), \; \mathbf{x}^* = [0,...,0] \]</td>
        <td style="width: 10%;"><p align = "right">(2)</p></td>
    </tr>
</table>

Example 1
{: .label .label-blue }

<p align = "justify">
  <i>
      Considering the design variable \(\mathbf{x} = [0,0]\), what value does the objective function expect?
  </i>
</p>

```python
# Data
x = [0, 0]

# Call function
of = sphere(x)

# Output details
print("of_best sphere: of = {:.4e}".format(of))
```

```bash
of_best sphere: of = 0.0000e+00
```

<h3>Reference list</h3>

<table>
    <thead>
        <tr>
            <th>ID</th>
            <th>Reference</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><p align = "center" id = "ref1">[1]</p></td>
            <td><p align = "left"><a href="https://www.sfu.ca/~ssurjano/spheref.html" target="_blank" rel="noopener noreferrer">Sonja Surjanovic, Derek Bingham. Virtual Library os Simulation Experiments, Simon Fraser University, accessed 20 February 2024, <www.sfu.ca/~ssurjano/optimization>.</a></p></td>
        </tr>
    </tbody>
</table>
