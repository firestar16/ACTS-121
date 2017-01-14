---
title       : Derivative Payoffs Using R
description : This lab is about working with derivative payoff functions in R
attachments :
  


--- type:NormalExercise lang:r xp:100 skills:1 key:2776d48885
## Defining a Call Option Payoff Function
Consider a `K`-strike European call option on a stock index $S$ that expires at time `T`.  In our book, the payoff is written as
$$\text{call payoff} = \max\left\\{0, S  -K\right\\}$$
In this exrcise you will define the payoff function using R


*** =instructions
Define `call_payoff` to be payoff of a European call option on stock index `S`.  The function should have two arguements:

* `K` the strike price
* `S` the underlying asset price at expiration

*** =hint
Make sure to include a factor `(K <= S)` in your function definition


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
call_payoff <- function(K, S){(K <= S) * (S - K)}
```

*** =sct
```{r}
test_error()
test_object("call_payoff",
            undefined_msg = "Did you correctly define call_payoff?",
            incorrect_msg = "Did you use all three arguements of integrate?  Did you include a (K <= S) factor in your definition?")
success_msg("Good job!")

```



--- type:NormalExercise lang:r xp:100 skills:1 key:618f8f7fec
## Graphing a Call Payoff 
In the previous exercise you define `call_payoff` to be the payoff function of a European call option on stock index $X$.  In this exeercise you practice plotting the graph using the `curve()` function.  There are many ways to plot functions in R.  In this exersice we are only  getting started with what is possible.  In this exercise the strike price $K$ is set to \\$40.00.


*** =instructions
The `call_payoff()` from the previous exercise is already defined for you.
- Use `ls()` to verify that `call_payoff()` is already defined
Use `curve` with the following arguements to plot `call_payoff`

- `S = x`
- `K = 40`
- `col = "red"`
- `xlim = c(0, 80)`
- `ylim = c(-40, 40)`
- `main = "A Long Call Payoff"`
- `las = 1`

*** =hint
Did you use `curve(call_payoff(S = x, K = 40),....`
*** =pre_exercise_code
```{r}
# Define call_payoff 
call_payoff <- function(K, S){(K <= S) * (S - K)}
```

*** =sample_code
```{r}
# Use ls() to verify that call_payoff is already defined


# Plot call_payoff using the arguements specified in the instructions


```

*** =solution
```{r}
# Use ls() to verify that call_payoff is already defined
ls()

# Plot call_payoff using the arguements specified in the instructions
curve(call_payoff(S = x, K = 40), 
      col  = 'red', 
      xlim = c(0, 80), 
      ylim = c(-40, 40), 
      las  = 1,
      ylab = "call_payoff",
      main = "Graphing a Long Call Option Payoff")
```

*** =sct
```{r}
test_error()

success_msg("Nice, Graphing with Base R is easy!!")
```
