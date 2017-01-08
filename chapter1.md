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
 --- type:NormalExercise lang:r xp:100 skills:1
    ## Calculate the mean

    In this exercise, you'll be calculating a mean.

    *** =instructions
    - Create a variable `m`, equal to the mean of the numbers 0 up to 9.
    - Print out `m`.

    *** =hint
    - You can use `mean(0:9)` to calculate `m`.
    - To print out a variable, simply write the variable name on a new line.

    *** =pre_exercise_code
    ```{r}
    # no pre exercise code required
    ```

    *** =sample_code
    ```{r}
    # Calculate the mean of all single digit numbers and assign the result to 'm'


    # print the result to the console

    ```

    *** =solution
    ```{r}
    # Calculate the mean of all single digit numbers and assign the result to 'm'
    m <- mean(0:9)

    # print the result to the console
    m
    ```

    *** =sct
    ```{r}
    test_function("mean", args = "x")
    test_object("m")
    test_output_contains("m")
    test_error()
    success_msg("Great job!")
    ```