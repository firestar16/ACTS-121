---
title       : Integration using R
description : This chapter provides examples of computing integrals using R
attachments :
  


--- type:NormalExercise lang:r xp:100 skills:1 key:e62a39e6f9
## One Dimensional Integration for Financial Derivatives
The mathematics of financial derivatives involves integrating probability density functions to compute expected values and probabilities.  In this course, you will use R to compute some these integrals numerically.  Follow the instructions below to calculate a simple integral using the `integrate()` function.



*** =instructions
Load the `stats` package.

Use R to evaluate the integral $\displaystyle{\int\limits_0^2 x \ dx}$.  Assign your answer to the variable `integral`
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

