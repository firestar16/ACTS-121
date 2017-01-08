---
title       : Forwards
description : This Chapter Introduces Forward Contracts
attachments :
  slides_link : https://www.dropbox.com/s/pb5nb5vbsa2yey8/ACTS121%20-%20Chapter%201.pdf?dl=0

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:a67632fe8e
## The long and short of forwards

Which of the following statemets is correct?

*** =instructions
- A long forward is a short position in the underlyng asset
- A long forward is a long position in the underlying asset
- A short forward is a long position in the underlying asset
- A long forward and a short forward are both long positions in the underlying asset

*** =hint
Long positions benefit from an increase in the underlying asset price?


*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "That is not correct!"
msg_success <- "Exactly! A Long forward is a long position in the underlying asset."
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))
```



--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:1834a6c405
## The premium of forward contracts
Which statement about the premium of a forward contract is correct?


*** =instructions
- A long forward has a positive premium $\Delta$
- A long forward has a negative premium
- A short forward has a positive premium
- A short forward has a negative premium
- Both short and long forwards have zero premium

*** =hint
How was is the forward price determined anyway?



*** =sct
```{r}
msg_bad <- "That is not correct!"
msg_success <- "Exactly! A forward options have zero premium"
test_mc(correct = 5, feedback_msgs = c(msg_bad, msg_bad, msg_bad, msg_bad,  msg_success))
```
--- type:NormalExercise lang:r xp:100 skills:1 key:f69f2da977
## Creating a Forward Payoff Function

In this exercise, you will define a forward payoff function using R

*** =instructions
- Define a function forward_payoff that computes a long forward payoff
- The function should have two arguements 
- Test your function by computing the payoff of a long forward contract when the forward price is 80 and the asset has price 70 at settlement

*** =hint
- Did you use  `function`?
- Did you name your function `forward_payoff`?
- Did you use two arguements for the function?



*** =sample_code
```{r}
# define the function forward_payoff


# test your function using F = 80  and S = 70

```

*** =solution
```{r}
# define the forward payoff

forward_payoff <- function(S, F)
  {(0 <= S) * (S - F)}

# test your function using F =80  and S = 70
forward_payoff(S = 70, F = 80)
```

*** =sct
```{r}
# define the forward payoff

forward_payoff <- function(S, F)
  {(0 <= S) * (S - F)}

# test your function using F =80  and S = 70
forward_payoff(S = 70, F = 80)
```


