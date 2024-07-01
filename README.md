# bopt-slf

A Bayesian optimization library. It features a set level filtration and kernel learning. 

For tutorial notebooks, check out the examples folder.

## Getting started

**Installing with pip**

````
pip install bopt-slf
````

**

Read the [basic notebook](https://github.com/JavierMorlet/bopt_slf/blob/main/examples/Basic_tour.ipynb)
for an  introduction to the library.

For more details please refer to the [advaned tour notebook](https://github.com/JavierMorlet/bopt_slf/blob/main/examples/Advanced_tour.ipynb)

## Dependencies:

* numpy
* scipy
* sympy
* itertools
* pandas
* sklearn
* GPy
* prince
* properscoring
* multiprocess
* matplotlib.pyplot

## Library parameters

The library parameters are:

<ul>
  <li>surrogate :</li>
  <ul>
    <li>{'GP', 'SGP'}, default 'GP'</li>
    <li>Specifies the surrogate model of the bayesian optimization algorithm</li>
  </ul>
  <li>acquisition_function :</li>
  <ul>
    <li>{'UCB', 'PI', 'EI'}, default 'UCB'</li>
    <li>Specifies the acquisition function of the bayesian optimization algorithm</li>
  </ul>
  <li>xi_0 :</li>
  <ul>
    <li>float, default 2</li>
    <li>Initial value of the acquisition function hyperparameter</li>
  </ul>
  <li>xi_f :</li>
  <ul>
    <li>float, default 0.1</li>
    <li>Final value of the acquisition function hyperparameter</li>
  </ul>
  <li>xi_decay :</li>
  <ul>
    <li>{'yes', 'no'}, default 'yes'</li>
    <li>Specifies whether the hyperparameter of the acquisition function decays.</li>
  </ul>
  <li>kernel :</li>
  <ul>
    <li>GPy.kern, default None</li>
    <li>The kernel is a function. If specified must be from GPy package</li>
  </ul>
  <li>kern_discovery :</li>
  <ul>
    <li>{'yes', 'no'}, default 'yes'</li>
    <li>Specifies whether the kernel function is selected automatically. If 'no', then specify a kernel from GPy</li>
  </ul>
  <li>kern_discovery_evals :</li>
  <ul>
    <li>int, default 2</li>
    <li>Specifies the number of evaluations to find the covariance function, only of kern_discovery is 'yes'</li>
  </ul>
  <li>x_0 :</li>
  <ul>
    <li>numpy array, default None</li>
    <li>Specifies the initial points to evaluate the surrogate model.</li>
  </ul>
  <li>f_0 :</li>
  <ul>
    <li>numpy array, default None</li>
    <li>Specifies the values ​​of the objective function evaluated at x_0, only of x_0 is specified.</li>
  </ul>
  <li>design :</li>
  <ul>
    <li>{'LHS', 'Sobol', 'Halton', 'random'}, default 'LHS'</li>
    <li>Specifies the initial design strategy to initialize x_0 if it is not specified.</li>
  </ul>
  <li>n_p_design :</li>
  <ul>
    <li>int, default None</li>
    <li>Specifies the number of points of the initial design, i.e. the size of the initial points matrix. If none, the value of n_p_design is calculated depending on the computing time of a random evaluation of the objective function</li>
  </ul>
  <li>n_jobs :</li>
  <ul>
    <li>int, default None</li>
    <li>The number of jobs to run in parallel for evaluations of the objective function. None means not using any processors (1 evaluation), and -1 means using all processors.</li>
  </ul>
  <li>n_restarts :</li>
  <ul>
    <li>int, default 5</li>
    <li>The number of times the surrogate model optimizer is restarted.</li>
  </ul>
  <li>max_iter :</li>
  <ul>
    <li>int, default 100</li>
    <li>Strict limit on the maximum number of iterations within the algorithm.</li>
  </ul>
  <li>constraints :</li>
  <ul>
    <li>tuple, default None</li>
    <li>Specifies the constraints functions that define the feasible region.</li>
  </ul>
  <li>constraints_method :</li>
  <ul>
    <li>{'PoF', 'GPC'}, default 'PoF'</li>
    <li>Specifies the method to model the constraints functions.</li>
  </ul>
  <li>reducer :</li>
  <ul>
    <li>A dimension reduction module, default None</li>
    <li>Specifies a dimension reduction technique specified by the user. If none, certain rules are used to define the dimension reduction technique depending in the characteristics of the design variables.</li>
  </ul>
  <li>inverter_transform :</li>
  <ul>
    <li>{'yes', 'no'}, default 'no'</li>
    <li>Specifies wheter to use an analytic inverse of the dimension reduction technique. Only valid for PCA</li>
  </ul>
  <li>alpha :</li>
  <ul>
    <li>float, default 0.95</li>
    <li>Confidence level for the Chi-squares and T-scores. Must be between 0 and 1.</li>
  </ul>
  <li>c1_param :</li>
  <ul>
    <li>int, default 50</li>
    <li>Value used to calculate the number of points for the matrix of initial estimates.</li>
  </ul>
  <li>c2_param :</li>
  <ul>
    <li>int, default 10</li>
    <li>Value used to control the number of grid sampling points.</li>
  </ul>
  <li>verbose :</li>
  <ul>
    <li>{0, 1}, default 0</li>
    <li>Enable verbose output.</li>
  </ul>
</ul>
