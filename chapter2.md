---
title       : Defining Derivative Payoffs
description : This chapter provides examples of defining option payoffs using R
attachments :
  


--- type:NormalExercise lang:r xp:100 skills:1 key:2776d48885
## Defining a Call Option Payoff Function
Consider a $K$-strike European call option on a stock index $S$ that expires at time $T$.  In our book, the payoff is written as
$$\text{call payoff} = \max\left\\{0, S  -K\right\\}$$
In this exrcise you will define the payoff function using R


*** =instructions
Define `call_payoff` to be payoff of a European call option on stock index $S$.  The function should have two arguements:

* `K` the strike price
* `S` the underlying asset price at expiration

*** =hint


*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Define call_payoff 
```

*** =solution
```{r}
# Define call_payoff 
call_payoff <- function(K, S){(K < = S) * (S - K)}
```

*** =sct
```{r}
# Define call_payoff 
call_payoff <- function(K, S){(K < = S) * (S - K)}
```
