# Mathematical Programming

## Mathematical Modeling

A model is a representation of a system, a problem, or part of it. The model is simpler than, and should be equivalent to, the real system in all relevant aspects. In this sense, a model is an abstract representation of a problem. Modeling is the activity of building a model.

### Model


A model is a representation of a system, a problem, or part of it. The model is simpler than, and should be equivalent to, the real system in all relevant aspects. In this sense, a model is an abstract representation of a problem. Modeling is the activity of building a model. In general it's:
  
  * Simplified representation of certain aspects of a real system
  * capturing the essence of that system

* The Five Step Method
  * Step 1: Ask the question.
  * Step 2: Select the modeling approach.
  * Step 3: Formulate the model.
  * Step 4: Solve the model.
  * Step 5: Answer the question.


### Mathematical  Model

* Using mathematical concepts: 

  * variables
	* operators
  * functions
	* equations
	* inequalities


#### First-Principle Models
 
 * based on physical laws (e.g. Newton’s second law)

    descriptive, explaining
    material parameter values often not known (measurements)

### Stochastic Models

based on distributions, averages (e.g. risk models)
capable to deal with random phenomena, hard to distinguish relations

### Empirical/data Models

based on (historical) patterns, data (e.g. Moore’s law)
not explaining, relations based on reality

#### Fist-Order Differential Equations
 
 Consider a collection of one million pennies. Every minute we flip the pennies and remove all of them that come up heads. How many pennies are remaining after a time t? On average, half of the pennies are removed each time, so

$$
\begin{matrix}
N(0) & = N_0 \quad\\
N(1) & = N_0 \times\frac{1}{2}  \\
N(2) & = N_0 \times ({\frac{1}{2}})^2 \\
N(3) & = N_0 \times ({\frac{1}{2}})^3 \\
     &  \cdots\\
N(t) & = N_0\times ({\frac{1}{2}})^t
\end{matrix}
$$

To make this equation truly general, we should include a time constant $$\tau$$
where, in our case $$\tau= 1$$ minute, and rewrite as


$$ N(t) = N_0 \times ({\frac{1}{2}})^{t/\tau} $$


Now, instead, consider a million six-sided dice. These dice are rolled once per minute and all of the dice that come up 6 are removed. The equation for the number of dice remaining is then


$$ N(t) = N_0 \times ({\frac{5}{6}})^{t/\tau} $$


### FIrst order Diffential Application
#### Solid Waste Disposal(SWDS)

The IPCC methodology for estimating $$CH_4$$  emissions from SWDS is based on the First Order Decay (FOD) method.


This method assumes that the degradable organic component (degradable organic carbon, DOC) in waste decays slowly throughout a few decades, during which $$CH_4$$ and $$CO_2$$ are formed. If conditions are constant, the rate of $$CH_4$$ production depends solely on the amount of carbon remaining in the waste. As a result emissions of $$CH_4$$  from waste deposited in a disposal site are highest in the first few years after deposition, then gradually decline as the degradable carbon in the waste is consumed by the bacteria responsible for the decay.


Simple Logistic Growth Equation


Letting N represent population size and t represent time, this model is formalized by the differential equation:

 $$\frac{dN}{dt} = rN$$

where 
 * N is the population
 * r is the growth rate
 * t is the time


The function is a sigmoid curve.
The initial stage of growth is approximately exponential; as saturation begins, the growth slows,
and at maturity, growth stops.

Solve the Problem

1. Mathematical description
2. Initial conditions
3. Parameter set
3. Necessary tools for integration and plotting

```python
import numpy as np
import matplotlib.pyplot as plt 
import math
import random
import seaborn as sns
sns.set()

r = .25 # growth rate / year ,|(birth/death rate)
N0 = 100 # Initial Population

t = np.linspace(0, 10, 11)
y = [N0*np.exp(r*i) for i in t]
plt.plot(t, y, 'r-')
plt.legend(['exact solution'], loc='upper left')
plt.xlabel('t'); 
plt.ylabel('N(t)')
plt.show()
```

## Integrated Assessment Modeling

* Integrated assessment models generally include both physical and social science models that consider demographic, political, and economic variables that affect greenhouse gas emission scenarios in addition to the physical climate system.

* General Circulation Models (GCMs), however, focus on the physical climate system alone.



* Many IAMs do include some form of climate modeling scheme in their routines, such as zero-dimensional or 2-dimensional energy balance models, but due to computing time limitations it is currently infeasible to integrate a full 3-dimensional GCM with a human dimensions model to create an IAM. 

* Specific purposes for constructing IAMs may include:

  * To provide a coherent framework for organizing and assessing knowledge about climate change.
  * To help differentiate among policy options.
  * To understand which of the many uncertainties about the modeled systems are most important.
  * To provide an organizing framework for conducting research.
  * To help inform the research planning process.
  * To garner qualitative judgments and insights into the interaction of components of the modeled systems.


 * It is very important for potential users of IAMs to understand the limitations of these models before using the model results:

   * The systems modeled are large, complex, and chaotic.
   * The full consequences of policies considered will not be known for decades or centuries.
   * Over this span of time, many surprises will occur.
   * Scientific knowledge is incomplete or absent in many areas.
   * Values of human, animal, and plant life, health, and diversity are difficult to quantify.


# Mathematical optimization

A model is a representation of the reality that captures "the essence" of reality. A photograph is a model of the reality portrayed in the picture. 

Mathematical optimization is the branch of computational science that seeks to answer the question `What is best?' for problems in which the quality of any answer can be expressed as a numerical value. Such problems arise in all areas of business, physical, chemical and biological sciences, engineering, architecture, economics, and management. The range of techniques available to solve them is nearly as wide. 

A mathematical optimization model consists of an objective function and a set of constraints expressed in the form of a system of equations or inequalities. Optimization models are used extensively in almost all areas of decision-making such as engineering design, and financial portfolio selection. This site presents a focused and structured process for optimization analysis, design of optimal strategy, and controlled process that includes validation, verification, and post-solution activities.


## Optimization-Modeling Process

* Optimization problems are ubiquitous in the mathematical modeling of real world systems and cover a very broad range of applications. 


* The general procedure that can be used in the process cycle of modeling is to: 

  (1) describe the problem, 
  (2) prescribe a solution, and 
  (3) control the problem by assessing/updating the optimal solution continuously

## Linear Program

Linear programming deals with a class of optimization problems, where both the objective function to be optimized and all the constraints, are linear in terms of the decision variables.


### What is a function:

 A function is a thing that does something. For example, a coffee grinding machine is a function that transform the coffee beans into powder. The (objective) function maps and translates the input domain (called the feasible region) into output range, with the two end-values called the maximum and the minimum values.

When you formulate a decision-making problem as a linear program, you must check the following conditions:
 
  * The objective function must be linear. That is, check if all variables have power of 1 and they are added or subtracted (not divided or multiplied)
  * The objective must be either maximization or minimization of a linear function. 
  * The objective must represent the goal of the decision-maker
  * The constraints must also be linear. 


* Any linear program consists of four parts: a set of **decision variables**, **the parameters**, **the objective function**, and a **set of constraints**.


* While trying to understand the problem, ask yourself the following general questions:

  * What are the decision variables? That is, what are controllable inputs? Define the decision variables precisely, using descriptive names. Remember that the controllable inputs are also known as controllable activities, decision variables, and decision activities.
  * What are the parameters? That is, what are the uncontrollable inputs? These are usually the given constant numerical values. Define the parameters precisely, using descriptive names.
  * What is the objective? What is the objective function? Also, what does the owner of the problem want? How the objective is related to his decision variables? Is it a maximization or minimization problem? The objective represents the goal of the decision-maker.
  * What are the constraints? That is, what requirements must be met? Should I use inequality or equality type of constraint? What are the connections among variables? Write them out in words before putting them in mathematical form.


** Consider the following problem:**

```
Minimize :  Z = 3x + 5y
Subject to the constraints: 
2x + 3y >= 12
-x + y <= 3
x >= 4
y <= 3
x, y >= 0
```

Solving the above linear programming problem in Python: PuLP is one of many libraries in Python ecosystem for solving optimization problems. You can install PuLp in Jupyter notebook as follows:

```python

# import the library pulp as p
import pulp as p
  
# Create a LP Minimization problem
Lp_prob = p.LpProblem('Problem', p.LpMinimize) 
  
# Create problem Variables 
x = p.LpVariable("x", lowBound = 0)   # Create a variable x >= 0
y = p.LpVariable("y", lowBound = 0)   # Create a variable y >= 0
  
# Objective Function
Lp_prob += 3 * x + 5 * y   
  
# Constraints:
Lp_prob += 2 * x + 3 * y >= 12
Lp_prob += -x + y <= 3
Lp_prob += x >= 4
Lp_prob += y <= 3
  
# Display the problem
print(Lp_prob)
  
status = Lp_prob.solve()   # Solver
print(p.LpStatus[status])   # The solution status
  
# Printing the final solution
print(p.value(x), p.value(y), p.value(Lp_prob.objective))
```

Output

```
6.0 0.0 18.0
```
The optimal value for x and y are 6.0 and 0.0 respectively. The optimised objective function value is 18.0.




## Quadratic Program

Quadratic Program (QP) comprises an area of optimization whose broad range of applicability is second only to linear programs. A wide variety of applications fall naturally into the form of QP. The kinetic energy of a projectile is a quadratic function of its velocity. The least-square regression with side constraints has been modeled as a QP. Certain problems in production planning, location analysis, econometrics, activation analysis in chemical mixtures problem, and in financial portfolio management and selection are often treated as QP. There are numerous solution algorithms available for the case under the restricted additional condition, where the objective function is convex.


## Constraint Satisfaction

Many industrial decision problems involving continuous constraints can be modeled as continuous constraint satisfaction and optimization problems. Constraint Satisfaction problems are large in size and in most cases involve transcendental functions. They are widely used in chemical processes and cost restrictions modeling and optimization.


## Convex Program

Convex Program (CP) covers a broad class of optimization problems. When the objective function is convex and the feasible region is a convex set, both of these assumptions are enough to ensure that local minimum is a global minimum.


## Dynamic Programming

Dynamic programming (DP) is essentially bottom-up recursion where you store the answers in a table starting from the base case(s) and building up to larger and larger parameters using the recursive rule(s). You would use this technique instead of recursion when you need to calculate the solutions to all the sub-problems and the recursive solution would solve some of the sub-problems repeatedly. While generally DP is capable of solving many diverse problems, it may require huge computer storage in most cases.

## Separable Program

Separable Program (SP) includes a special case of convex programs, where the objective function and the constraints are separable functions, i.e., each term involves just a single variable.

## Geometric Program

Geometric Program (GP) belongs to Nonconvex programming, and has many applications in particular in engineering design problems.
