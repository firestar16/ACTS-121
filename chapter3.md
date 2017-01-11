
--- type:NormalExercise lang:r xp:100 skills:1 key:b1c6ba65b9
## $\Delta_{call}$



*** =instructions
Define a function `call_delta` that equals the delta of a European call option.  Use the following  

* $K$ - strike price
* $S$ - current underlying asset price
* $t$ - current calendar time
* $T$ - the option's time of expiration
* $r$ - the continuously compounded risk-free interest rate
* $v$ - the underlying stock's annualized volatility
* $d$ - the underlying stock's annualized dividend yield

*** =hint

*** =pre_exercise_code
```{r}
# first define d_11
```

*** =sample_code
```{r}

```

*** =solution
```{r}
# First define d_1
```
d_1 <- function(S, K, t, T, r, v, d){(log(S / K) + (r - d + 0.5 * v ^ 2) * (T - t)) / (v * sqrt(T -t))}

# Define call_delta using d_1
call_delta <- function(S, K, t, T, r, v, d){exp(d * (T - t))*d_1(S, K, t, T, r, v, d)}

# Test call_delta using S = 40, K = 40, t = 0, T =1, r = 0.05, v = 0.30, and d = 0
call_delta(S = 40, K = 40, t = 0, T =1, r = 0.05, v = 0.30, d = 0)
*** =sct
```{r}

```
