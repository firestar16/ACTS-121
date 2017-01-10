---
title       : Multiple Choice Examples
description : This chapter includes examples of multiple choice examples


--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:5359b46ae9
## Multiple Choice Exercise Title
This is the assignment.
How much is `2 + 2`



*** =instructions
-2
-3
-4

*** =hint
Here's a hint:  Think about your time in primary school.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sct
```{r}
msg1 = "Try again! Think about your time in school."
msg2 = "Summing two even numbers always leads to another even number"
msg3 = "Well done.  Proceed to the next exercise"
test_mc(correct = 3, feedback_msgs = c(msg1, msg2, msg3))
```
