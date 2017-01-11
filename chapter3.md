---
title       : The Option Greeks 
description : This chapter explores the options greeks
attachments :
slides      : 
  

--- type:NormalExercise lang:r xp:100 skills:1 key:b1c6ba65b9
## Delta for a European Call option

In this exercise you will define `call_delta` = $\Delta_{call}$ using R.

$\Delta_{call} = e^{-\delta(T-t)} N(d{1})$


$d{_1} = \dfrac{\ln(S/K)+(r-\delta +0.5\sigma^2)(T-t)}{\sigma\sqrt{T-t}}$




*** =instructions
Define a function `call_delta` that equals the delta of a European call option.  Since greek symbols like $\sigma$ and $\delta$ are not able to be entered into R, use the following variables names instead. 

* $K$ - strike price
* $S$ - current underlying asset price
* $t$ - current calendar time
* $T$ - the option's time of expiration
* $r$ - the continuously compounded risk-free interest rate
* $v$ - the underlying stock's annualized volatility
* $d$ - the underlying stock's annualized dividend yield

*** =hint
Did you define `d_1 <- function(S, K, t, T, r, v, d){(log(S / K) + (r - d + 0.5 * v ^ 2) * (T - t)) / (v * sqrt(T -t))}` first?

*** =pre_exercise_code
```{r}



```

*** =sample_code
```{r}
# first define d_1


# Define call_delta using d_1


# Test call_delta using S = 40, K = 40, t = 0, T = 1, r = 0.05, v = 0.30, and d = 0
```

*** =solution
```{r}
# First define d_1
d_1 <- function(S, K, t, T, r, v, d){(log(S / K) + (r - d + 0.5 * v ^ 2) * (T - t)) / (v * sqrt(T -t))}

# Define call_delta using d_1
call_delta <- function(S, K, t, T, r, v, d){exp(d * (T - t))*pnorm(d_1(S, K, t, T, r, v, d))}

# Test call_delta using S = 40, K = 40, t = 0, T =1, r = 0.05, v = 0.30, and d = 0
call_delta(S = 40, K = 40, t = 0, T = 1, r = 0.05, v = 0.30, d = 0)
```

*** =sct
```{r}
test_error()
test_object("call_delta",
            undefined_msg = "Did you define `call_delta` using `d_1`?",
            incorrect_msg = "Did you use all six arguements?  Did you remember to test `call_delta`?")
success_msg("Incredible!")
```
