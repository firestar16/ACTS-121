---
title       : Integration using R
description : This lab is about working integrating one dimensional functions using R
attachments :
  


--- type:NormalExercise lang:r xp:100 skills:1 key:e62a39e6f9
## One Dimensional Integration for Financial Derivatives
The mathematics of financial derivatives involves integrating probability density functions to compute expected values and probabilities.  In this course, you will use R to compute some these integrals numerically.  Follow the instructions below to calculate a simple integral using the `integrate()` function.



*** =instructions
Load the `stats` package.

Use R to evaluate the integral $\displaystyle{\int\limits_0^2 x^2 \ dx}$.  

Assign your answer to the variable `integral`

Your call to `integrate` should use three arguements

* `f = function(x){x ^ 2}`
* `upper = 2`
* `lower = 0`. 

Make sure to select the `value` part of `integrate`'s output

*** =hint
Did you you use `integrate(f = function(x){x ^ 2}, lower = 0, upper = 2)$value`?


*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Load the stats package


# Use the integrate function. Assign the resulting value to integral


# Display the value of integral
```

*** =solution
```{r}
# Load the stats package
library(stats)

# Use the integrate function. Assign the resulting value to integral
integral <- integrate(f = function(x){x ^ 2}, lower = 0, upper = 2)$value

# Display the value of integral
integral
```

*** =sct
```{r}
test_error()
test_object("integral",
            undefined_msg = "Did you assign your answer to the variable integral?",
            incorrect_msg = "Did you correctly enter all three arguements of `integrate`?")
success_msg("Good job! You have already integrated a simple one dimensional function using R!")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:ace2599d9b
##SOA Exam P #45
Let $X$ be a continuous random variable with density function
$$
f(x) = \begin{cases}
\dfrac{\vert x\vert}{10} &, \ \ -2 < x < 4 \\\
& \\\
0 &, \ \ \text{otherwise} \\\
\end{cases}
$$
Calculate the expected value of $X$.


*** =instructions

- Assign the density function of $X$ to `f`
- Use `integrate` with appropriate arguements to calculate the expected value of $X$
- Assign your answer to `expected_value`

*** =hint
Did you use `integrate()` with arguements `f = function(x){x*f(x)}`,`lower = -2`, and `upper = 4`? Did you define the density using
`f <- function(x){(-2 < x & x < 4) * abs(x) / 10}`?  Did you only select the numerical result of `integrate`?  Did you assign the expected value to `expected_value` and print the result to the console? 

*** =pre_exercise_code
```{r}


```

*** =sample_code
```{r}
# Load the stats package


# Assign the density function of X to f


# Use integrate to calculate the expected value of X.  Assign to expected_value


# Display expected_value



```

*** =solution
```{r}
# Load the stats package
library(stats)

# Assign the density function of X to f
f <- function(x){(-2 < x & x < 4) * abs(x) / 10}

# Use integrate to calculate the expected value of X.  Assign to expected_value
expected_value <- integrate(f = function(x){x * f(x)}, lower = -2, upper = 4)$value

# Display expected_value
expected_value
```

*** =sct
```{r}
test_error()
test_object("f",
            undefined_msg = "Did you define the density function as f?",
            incorrect_msg = "Did you correctly define the density function of X?")
test_object("expected_value",
            undefined_msg = "Did you assign the expected value to expected_value?",
            incorrect_msg = "Did you correctly compute E[X]?")
test_output_contains(expected_value,
                     times = 1,
                     incorrect_msg = "Did you print out expected_value?")
success_msg("Good job! You can solve exam P problems using R")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:5bcf4a8e2e
## SOA Exam P #55
An insurance company's monthly claims are modeled by a continuous, positive random variable $X$ whose probability density function is proportional to $(1+x)^{-4}$, for $\ 0    <  \  x   <  \infty$.  Calculate the company's expected monthly claims.


*** =instructions

* Solve for the constant of proportionality, `c`.  
* Assign the probability density function of $X$ to `f`
* Calculate $E[X]$ using `integrate()`

*** =hint
- Did you integrate $(1+x)^{-4}$ over the interval $(0, \infty)$ and assign the value to `c`?


- Did you compute $\displaystyle{E[X] = \int\limits_0^{\infty} x f(x) \ dx}$?

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# load the stats package


# Calculate the contant of proportionality and assign this value to c


# Assign the density function of X to f


# Calculate the expected value of X and save as expected_value


# Display expected_value

```

*** =solution
```{r}
# load the stats package
library(stats)

# Calculate the contant of proportinality and assign this value to c
(c <- 1 / integrate(function(x) (1 + x) ^{-4}, lower = 0, upper = Inf)$value)


# Assign the density function of X to f
f <- function(x){c / (1 + x)^4}


# Calculate the expected value of X and save as expected_value
expected_value <- integrate(function(x){x * f(x)}, lower = 0,  upper = Inf)$value

# Display expected_value
expected_value
```

*** =sct
```{r}
test_error()
test_object("c",
            undefined_msg = "Did you define the constant c?",
            incorrect_msg = "Did you correctly calculate the value of c?")

test_object("f",
            undefined_msg = "Did you define the density function as f?",
            incorrect_msg = "Did you correctly define the density function of X using the value of c?")
test_object("expected_value",
            undefined_msg = "Did you assign the expected value to expected_value?",
            incorrect_msg = "Your answer for E[X] is wrong")
test_output_contains(expected_value,
                     times = 1,
                     incorrect_msg = "Did you print out expected_value?")
success_msg("Good job! You are getting really good at this!")
```




--- type:NormalExercise lang:r xp:100 skills:1 key:b2434ee5d2
## SOA Exam P #157

Let $X$ be a continuous random variable with density function

$$
f(x) = 
\begin{cases}
\dfrac{p-1}{x^p} &, \ 1 < x \\\
& \\\
0 &, \ \text{otherwise} \\\
\end{cases}
$$

Calculate the value of $p$ such that $E[X] = 2$



*** =instructions
* load the stats package

* Define a density function $f(x,p)$ as `f`

* Note that for $E[X]$ to be defined, $2 < p$

* Define an expected value function $ex(p) = \displaystyle{\int\limits_1^{\infty} x \cdot f(x,p) \ dx}$

* Estimate a solution to the equation $ex(p) = 2$ using `which.min()`

* Remember that $2 < p$ 

*** =hint
- Load both the stats package
- Define `f` a a function of  $x$ and $p$
- Use `integrate()` to define `ex(p)` 
- Vectorize `ex`
- Estimate a solution to the equation ex(p) = 2 using `which.min()`
- Save your answer as p_answer
- Print p_answer

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# load the stats package


# Define the density function f


# Use f to define an expected value function ex


# Vectorize ex


# Estimate a solution to the equation ex(p) = 2 and save ave as p_answer


# Print p_answer to the console


```

*** =solution
```{r}
# load the stats package
library(stats)


# Define the density function f
f <- function(x, p){(1 < x) * (p - 1) / x ^ p}

# Use f to define an expected value function e
ex <- function(p){integrate(function(x){x * f(x, p)}, lower = 1, upper = Inf)$value}

# Vectorize ex
ex <- Vectorize(ex)

# Estimate a solution to the equation e(p) = 2 and save as p_answer
values   <- ex(seq(2.01, 5, by = 0.001)) 
index    <- which.min(abs(values - 2))
p_answer <- values[index]

# Print p_answer to the console
p_answer
```

*** =sct
```{r}
test_error()
test_object("f",
            undefined_msg = "Make sure to define the density f(x,p)",
            incorrect_msg = "Did you correctly define f(x,p)?")
test_object("ex",
            undefined_msg = "Did you assign the expected value function ex",
            incorrect_msg = "Your definition of for ex is wrong")
test_output_contains(p_answer,
                     times = 1,
                     incorrect_msg = "Did you print out p_answer")
success_msg("Good job! You are getting really good at this!")
```
