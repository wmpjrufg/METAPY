---
layout: default
title: RMSE
parent: Loss
grand_parent: Statistical
has_children: false
has_toc: false
nav_order: 5
---

<!--Don't delete ths script-->
<script src = "https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id = "MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<!--Don't delete ths script-->

<p align="justify">
The Root Mean Square Error (RMSE) loss function is a \(d\)-dimensional loss function.
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
        <td><code>y_true</code></td>
        <td>True values.</td>
        <td>List</td>
    </tr>
    <tr>
        <td><code>y_pred</code></td>
        <td>Predicted values.</td>
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
        <td><code>rmse</code></td>
        <td>The function returns the value of the Root Mean Square Error (RMSE) calculated based on the true and predicted values.</td>
        <td>Float</td>
    </tr>
</table>
<h3>Problem</h3>
<table style = "width:100%">
    <tr>
        <td style="width: 90%;">\[f(\mathbf{y}) = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_{\text{true},i} - y_{\text{pred},i})^2}\]</td>
        <td style="width: 10%;"><p align = "right">(1)</p></td>
    </tr>
</table>

```python
# Data
y_true_example = [1, 2, 3, 4, 5]
y_pred_example = [1.2, 2.3, 2.9, 4.2, 5.3]

# Call function
rmse_value = loss_function_rmse(y_true_example, y_pred_example)

# Print the result
print("Root Mean Square Error (RMSE): {:.4f}".format(rmse_value))
```

```bash
of_best mae: of = 0.0000e+00
```
