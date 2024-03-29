<!--Don't delete ths script-->
<script src = "https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id = "MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<!--Don't delete ths script-->

Parallel processing explanation
{: .label .label-green }

<p align = "justify">Multiprocessing can be useful for applications that have independent data processing. In Metapy, some parts of the code do not need to be executed in serial mode. Each population has its own result and can be calculated independently and then the results concatenated. </p>

<p align = "justify">The code example below shows how multiprocessing is being used in this application.</p>

Python example
{: .label .label-blue }

<p align = "justify">The code example below shows how multiprocessing is being used in this application.  In this example, the population is initialized by the <code>INITIAL_POPS</code> function with parameters such as the number of repetitions (<code>SETUP['N_REP']</code>), the population number (<code>SETUP['N_POP']</code>), the number of dimensions (<code>SETUP['D']</code>), the lower limit (<code>SETUP['X_L']</code>) and the upper limit (<code>SETUP['X_U']</code>).</p>

```python
# Initial population
    POP = META_CO.INITIAL_POPS(SETUP['N_REP'], SETUP['N_POP'], SETUP['D'], SETUP['X_L'], SETUP['X_U'], SETUP['TYPE CODE'])

    # Algorithm selection and general results
    if SETUP['ALGORITHM'] == 'HILL CLIMBING 01':
        # Define the name of the model
        MODEL_NAME = 'META_HC001_'
        # Multiprocess
        with Pool() as p:
            INFO = [[SETUP, I] for I in POP]
            RESULT = p.map_async(func = HILL_CLIMBING_001, iterable = INFO)
            FINAL_RESULT = RESULT.get()

```

<p align = "justify">
The image first represents the creation of the population with the <code>INITIAL_POP</code> function in serial form, with parameters such as <code>SETUP['N_REP']</code> equals 3 and <code>SETUP['N_POP']</code> equal to 4, that's it, 3 populations with 4 individuals. The white box represents both the population boundary and the processing zone. Translating this into the context of the code, the boxes represent the 'with' stamentement. And finally, the concatenation of the result is done in the with <code>RESULT.get</code>.
</p>

<img src="assets/images/Multiprocessing explanation.png">
