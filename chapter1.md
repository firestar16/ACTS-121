---
title       : Normal Exercise Examples
description : This Chapter Provides Normal Exercise Examples
attachments :
  


--- type:NormalExercise lang:r xp:100 skills:1 key:e62a39e6f9
## One Dimensional Integration for Financial Derivatives
The mathematics of financial derivatives involves integrating probability density functions to compute expected values and probabilities.  In this course, you will use R to compute these integrals.  Follow the instructions below to calculate a simple integral using the `integrate()` function.



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
            incorrect_msg = "Did you correctly enter all three arguements of integrate?")
success_msg("Good job! You have already integrated a simple one dimensional function using R!")
```
