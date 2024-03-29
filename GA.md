<!--Don't delete ths script-->
<script src = "https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id = "MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<!--Don't delete ths script-->

LINEAR_CROSSOVER
{: .label .label-green }

<p align = "justify">This function is a linear crossover between two individuals (represented by father_1 and father_2) in an optimization algorithm. </p>

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
       <td><code>father_1</code></td>
       <td>Represents the first parent for the crossover.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>father_2</code></td>
       <td>Represents the second parent for the crossover.</td>
       <td>Py list</td>
   </tr> 
   <tr>
       <td><code>of_function</code></td>
       <td>This is the objective function that will be applied to the offspring to assess their fitness.</td>
       <td>Py function</td>
   </tr> 
   <tr>
       <td><code>null_dic</code></td>
       <td> This is an empty dictionary or object that can be used in the objective function, but is not used directly in the crossover function.</td>
       <td>Py dict</td>
   </tr>   
   <tr>
       <td><code>x_l</code></td>
       <td>Represents the lower limit of the interval for checking.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>x_u</code></td>
       <td>Represents the upper limit of the interval for checking.</td>
       <td>Py list</td>
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
       <td><code>x_t1i</code></td>
       <td>List of values resulting from the linear crossover between parents father_1 and father_2.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>of_t1i</code></td>
       <td>Value of the objective function (or fitness function) evaluated on the set of x_t1i values.</td>
       <td>Float</td>
   </tr>
   <tr>
       <td><code>fit_t1i</code></td>
       <td>Fitness value corresponding to the result of the of_t1i objective function.</td>
       <td>Float</td>
   </tr>
   <tr>
       <td><code>neof</code></td>
       <td>Value indicating the number of evaluations of new solutions generated by the function.</td>
       <td>Int</td>
   </tr>
</table>

Example 1
{: .label .label-blue }

<p align = "justify">
 <i>
    Use the <code>LINEAR_CROSSOVER</code> function to perform a linear crossover process between two populations of individuals, represented by <code>father_1</code> and <code>father_2</code>. These individuals have numerical characteristics represented by vectors of values. The linear crossover process combines the values of these vectors to create three new individuals, represented by <code>OFFSPRING_A</code>, <code>OFFSPRING_B</code> and <code>OFFSPRING_C</code>.
 </i>
</p>

```python
def objective_function(x, null_dic):
    return sum([(i + 1) * x[i]**2 for i in range(len(x))])

father1 = [1, 2, 3]
father2 = [4, 5, 6]
xL = [0, 0, 0]
xU = [10, 10, 10]
nullDic = None

result = LINEAR_CROSSOVER(father1, father2, objective_function, nullDic, xL, xU)

print("The best son:", result[0])
print("Objective function value:", result[1])
print("Fitness value:", result[2])
print("Number of job evaluations:", result[3])
```

```bash
The best son: [0.0, 0.5, 1.5]
Objective function value: 7.25
Fitness value: 0.12121212121212122
Number of job evaluations: 3
```

BINOMIAL_CROSSOVER
{: .label .label-green }

<p align = "justify"></p>

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
       <td><code>father_1</code></td>
       <td>Represents the first parent for the crossover.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>father_2</code></td>
       <td>Represents the second parent for the crossover.</td>
       <td>Py list</td>
   </tr> 
   <tr>
       <td><code>binomial_rate</code></td>
       <td> This is the binomial crossover rate.</td>
       <td>Float</td>
   </tr> 
   <tr>
       <td><code>of_function</code></td>
       <td>Is the objective function that will be used to evaluate the result of the crossover.</td>
       <td>Py function</td>
   </tr> 
   <tr>
       <td><code>null_dic</code></td>
       <td>This dictionary is used as a parameter for the objective function.</td>
       <td>Py dict</td>
   </tr>   
   <tr>
       <td><code>x_l</code></td>
       <td>Represents the lower limits of the range for the problem variables.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>x_u</code></td>
       <td>Represents the upper limits of the range for the problem variables.</td>
       <td>Py list</td>
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
       <td><code>x_t1i</code></td>
       <td>List of values resulting from the binomial crossover between parents father_1 and father_2.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>of_t1i</code></td>
       <td></td>
       <td>Float</td>
   </tr>
   <tr>
       <td><code>fit_t1i</code></td>
       <td></td>
       <td>Float</td>
   </tr>
   <tr>
       <td><code>neof</code></td>
       <td>New solution indicator. It is a Boolean value (1 to indicate a new solution)</td>
       <td>Int</td>
   </tr>
</table>

Example 1
{: .label .label-blue }

<p align = "justify">
 <i>
   Use the <code>BINOMIAL_CROSSOVER</code> function

 </i>
</p>

```python


```

```bash


```

BLXALPHA_CROSSOVER
{: .label .label-green }

<p align = "justify"></p>

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
       <td><code>father_1</code></td>
       <td>Represents the first parent for the crossover.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>father_2</code></td>
       <td>Represents the second parent for the crossover.</td>
       <td>Py list</td>
   </tr> 
   <tr>
       <td><code>of_function</code></td>
       <td>This is the objective function that will be applied to the offspring to assess their fitness.</td>
       <td>Py function</td>
   </tr> 
   <tr>
       <td><code>null_dic</code></td>
       <td> This is an empty dictionary or object that can be used in the objective function, but is not used directly in the crossover function.</td>
       <td>Py dict</td>
   </tr>   
   <tr>
       <td><code>x_l</code></td>
       <td>Represents the lower limit of the interval for checking.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>x_u</code></td>
       <td>Represents the upper limit of the interval for checking.</td>
       <td>Py list</td>
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
       <td><code>x_t1i</code></td>
       <td>List of values resulting from the blx alpha crossover between parents father_1 and father_2.</td>
       <td>Py list</td>
   </tr>
   <tr>
       <td><code>of_t1i</code></td>
       <td></td>
       <td>Float</td>
   </tr>
   <tr>
       <td><code>fit_t1i</code></td>
       <td></td>
       <td>Float</td>
   </tr>
   <tr>
       <td><code>neof</code></td>
       <td>New solution indicator. It is a Boolean value (1 to indicate a new solution)</td>
       <td>Int</td>
   </tr>
</table>

Example 1
{: .label .label-blue }

<p align = "justify">
 <i>
   Use the <code>BLXALPHA_CROSSOVER</code> function

 </i>
</p>

```python


```

```bash


```
