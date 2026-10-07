# EPIDEMICS
Epidemic spreads over n weeks 
Epidemic Spread Over N Weeks (C1)

📌 Project Title

Epidemic Spread Over N Weeks Using Cayley-Hamilton Theorem

---

1. Project Overview

This project models the spread of a disease through a population over multiple weeks using matrices, matrix powers, and the Cayley-Hamilton theorem.

The population is divided into three disease states:

- S — Susceptible: People who can become infected
- I — Infected: People who are currently infected
- R — Recovered: People who have recovered

The population at week n is represented by the state vector:

[
X_n =
\begin{bmatrix}
S_n\
I_n\
R_n
\end{bmatrix}
]

The weekly disease transition is represented by a matrix A.

The main mathematical model is:

[
\boxed{X_{n+1}=AX_n}
]

Therefore:

[
\boxed{X_n=A^nX_0}
]

For one year, approximately 52 weeks:

[
\boxed{X_{52}=A^{52}X_0}
]

---

2. Real-World Problem

During an epidemic, people can move between different disease states.

For example:

Susceptible
     |
     | Infection
     ↓
  Infected
     |
     | Recovery
     ↓
  Recovered

The number of people in each state changes every week.

Instead of calculating every week separately, we use a transition matrix to describe the changes.

This allows us to predict the epidemic after N weeks.

---

3. Mathematical Model

Let

[
X_n=
\begin{bmatrix}
S_n\
I_n\
R_n
\end{bmatrix}
]

represent the population during week n.

Let A be the weekly transition matrix.

Then:

[
X_{n+1}=AX_n
]

For the first week:

[
X_1=AX_0
]

For the second week:

[
X_2=AX_1
]

Substituting:

[
X_2=A(AX_0)
]

[
X_2=A^2X_0
]

Similarly:

[
X_3=A^3X_0
]

Therefore, after N weeks:

[
\boxed{X_N=A^NX_0}
]

For one year:

[
\boxed{X_{52}=A^{52}X_0}
]

---

4. Transition Matrix

The transition matrix is:

[
A=
\begin{bmatrix}
a_{11}&a_{12}&a_{13}\
a_{21}&a_{22}&a_{23}\
a_{31}&a_{32}&a_{33}
\end{bmatrix}
]

Using the column-vector convention:

- Rows represent the next disease state
- Columns represent the current disease state

For example:

- a_{11}: Susceptible → Susceptible
- a_{21}: Susceptible → Infected
- a_{32}: Infected → Recovered

For a probability transition matrix, the entries are non-negative and each column should sum to 1.

---

5. Initial Population

The initial population is represented by:

[
X_0=
\begin{bmatrix}
S_0\
I_0\
R_0
\end{bmatrix}
]

For example:

[
X_0=
\begin{bmatrix}
700\
200\
100
\end{bmatrix}
]

This means:

- 700 susceptible people
- 200 infected people
- 100 recovered people

Total population:

[
700+200+100=1000
]

---

6. Cayley-Hamilton Theorem

The main mathematical concept used in this project is the Cayley-Hamilton theorem.

The theorem states:

«Every square matrix satisfies its own characteristic equation.»

For a matrix A, the characteristic equation is obtained from:

[
\det(\lambda I-A)=0
]

For a 3\times3 matrix, the characteristic equation has the form:

[
\lambda^3-c_1\lambda^2+c_2\lambda-c_3=0
]

By the Cayley-Hamilton theorem:

[
A^3-c_1A^2+c_2A-c_3I=0
]

Therefore:

[
\boxed{A^3=c_1A^2-c_2A+c_3I}
]

This equation allows higher powers of A to be reduced using only:

[
I,\ A,\ A^2
]

Thus:

[
\boxed{A^n=\alpha A^2+\beta A+\gamma I}
]

This makes Cayley-Hamilton useful for calculating large matrix powers such as:

[
A^{52}
]

---

7. Why A^{52}?

One year contains approximately:

[
52\text{ weeks}
]

The state of the epidemic after 52 weeks is:

[
X_{52}=A^{52}X_0
]

Therefore, the project uses Cayley-Hamilton to efficiently calculate the required matrix power.

---

8. Steady State

A steady state is a state where the population distribution does not change after another transition.

Let the steady-state vector be:

[
X^*
]

Then:

[
X^=AX^
]

Rearranging:

[
AX^-X^=0
]

[
(A-I)X^*=0
]

Therefore, the steady state can be found by solving:

[
\boxed{(A-I)X^*=0}
]

If the vector represents population proportions, we can also use:

[
S^+I^+R^*=1
]

as a normalization condition.

---

9. Input Variables

The application will take the following inputs.

1. Transition Matrix

[
A
]

This represents the weekly transition probabilities between disease states.

2. Initial State Vector

[
X_0
]

This represents the initial number of susceptible, infected, and recovered people.

3. Number of Weeks

[
N
]

The user can enter any number of weeks.

For the one-year demonstration:

[
N=52
]

---

10. Algorithm

The planned algorithm is:

START
   ↓
Input transition matrix A
   ↓
Input initial state X₀
   ↓
Input number of weeks N
   ↓
Calculate characteristic equation
   ↓
Apply Cayley-Hamilton theorem
   ↓
Calculate Aᴺ
   ↓
Calculate Xᴺ = AᴺX₀
   ↓
Calculate population for each week
   ↓
Find steady state
   ↓
Display results
   ↓
Generate graph
   ↓
END

---

11. Weekly Epidemic Evolution

The program will calculate:

[
X_0,X_1,X_2,\ldots,X_{52}
]

The output can be displayed as:

Week| Susceptible| Infected| Recovered
0| S_0| I_0| R_0
1| S_1| I_1| R_1
2| S_2| I_2| R_2
...| ...| ...| ...
52| S_{52}| I_{52}| R_{52}

A graph will show how the three populations change with time.

---

12. Final Demo Application

The final application should allow the user to:

Input

- Enter transition matrix A
- Enter initial population X_0
- Enter number of weeks N

Processing

- Calculate characteristic equation
- Apply Cayley-Hamilton theorem
- Calculate A^N
- Calculate X_N
- Generate weekly epidemic data
- Calculate steady state

Output

The application should display:

1. Characteristic equation
2. Cayley-Hamilton relation
3. Matrix power A^N
4. Final population X_N
5. Weekly epidemic table
6. Epidemic evolution graph
7. Steady-state vector

---

13. Real-World Application

This project demonstrates how linear algebra can be applied to epidemic modeling.

The model can be used to understand how a population moves between disease states over time.

The project is inspired by epidemic modeling used for diseases such as COVID-19.

However, this is a simplified educational model.

Real epidemiological models may include:

- Infection rates
- Recovery rates
- Vaccination
- Immunity
- Population behavior
- Demographic changes
- Time-dependent parameters
- Birth and death rates

A standard continuous-time SIR model is generally described using differential equations, while this project uses a discrete-time transition-matrix model.

---

14. Mathematical Concepts Used

The project uses the following B.Tech Mathematics concepts:

1. Matrices
2. Matrix multiplication
3. Matrix powers
4. Characteristic equation
5. Cayley-Hamilton theorem
6. Identity matrix
7. Linear equations
8. Eigenvalue concepts
9. Steady-state analysis
10. Data visualization

---

15. Main Mathematical Equations

The complete project can be summarized using these equations.

Weekly transition

[
\boxed{X_{n+1}=AX_n}
]

After N weeks

[
\boxed{X_N=A^NX_0}
]

One-year prediction

[
\boxed{X_{52}=A^{52}X_0}
]

Characteristic equation

[
\boxed{\det(\lambda I-A)=0}
]

Cayley-Hamilton equation

[
\boxed{A^3-c_1A^2+c_2A-c_3I=0}
]

Steady state

[
\boxed{AX^=X^}
]

or

[
\boxed{(A-I)X^*=0}
]

---

16. Project Objective

The main objective of this project is to demonstrate how the Cayley-Hamilton theorem and matrix powers can be applied to a practical epidemic-spread problem.

The project connects:

[
\boxed{\text{B.Tech Mathematics}}
]

with

[
\boxed{\text{Matrix Algebra}}
]

and

[
\boxed{\text{Epidemic Modeling}}
]

to predict how an epidemic evolves over multiple weeks.

---

17. Expected Final Result

At the end of the project, the application should answer:

«Given an initial population and a weekly disease transition matrix, what will the population distribution look like after N weeks, particularly after 52 weeks, and what is the long-term steady state?»

The key result is:

[
\boxed{X_N=A^NX_0}
]

with A^N calculated using the Cayley-Hamilton theorem.
