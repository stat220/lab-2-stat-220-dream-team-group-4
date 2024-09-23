[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/h9nlBIrW)

[![Open Lab in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://drive.google.com/file/d/17D_d4QISGvXanwkYtGnzJ8pG62dstEu0/view?usp=sharing)

#  Stat 220 Lab 2: Probability Calculation for Red Dragon Inn

The Red Dragon Inn is an online Dungeons and Dragons community, connecting players worldwide.
In this lab, you will develop a tool that helps users calculate the probabilities of specific events occurring during gameplay,
enhancing their strategic planning.
For instance, users may wish to calculate the probability of the sum of two six-sided dice being 10 or more.

In Dungeons and Dragons, the notation _mdn_ denotes the process of rolling _m_ dice,each with _n_ sides.
Here, rolling two six-sided dice is expressed as 2*d*6,
and rolling three eight-sided dice is denoted by 3*d*8.
You are tasked with creating a utility to assist players in the following two scenarios:
* **Scenario A:** Calculating the probability of rolling _m_ dice, each with _n_ sides,
  and having the sum of the dice be greater than _x_.
  This calculation should only be implemented for _m_ = 1 through 4 and _n_ is at most 20.
* **Scenario B:** Determining the probability of rolling _m_ dice, each with n sides,
  and having at least one die show a value greater than or equal to _x_.

Your task is to develop two functions, one for each scenario,
where users can input values for _m_, _n_, and _x_ to compute the required probability.
Ensure to document your code well, with comments that effectively guide users through each step of the computation process.

Here’s a hint to help you get started with computing probabilities in Python.
The following code snippet shows how to calculate
the probability of rolling a sum greater than or equal to a specific target
using three six-sided dice (3d6):

```python
import itertools
import pandas as pd
import numpy as np

# List out all possible rolls, in this case for 3d6
rolls = list(itertools.product(range(1, 7), repeat=3))
# Find the sum of all possible rolls
sums = np.array([sum(roll) for roll in rolls])
# Find the proportion of those sums that are greater than or equal to the target,
# in this case 14
np.mean(sums >= 14)
```

This code uses the `itertools.product` function to generate all possible combinations of outcomes for the dice rolls
and then calculates the proportion of those combinations that meet or exceed the target sum.
You can use this code to get started in the function you need for Scenario A.

Evaluate the performance of your tool using the following scenario:

A player is in a challenging situation where they have a choice.
They can choose between the following challenges:
* Roll 1d20 and get a result of 17 or more
* Roll 3d4 and get a result of 10 or more
* Roll 4d6 and have at least one dice show a 6

Use your tool to compute the probabilities and report the best choice for the player.

## Deliverables:
Submit a comprehensive report to Red Dragon Inn containing:
1. A well-documented code capable of computing the probabilities specified in scenarios A and B.
2. A walkthrough example showcasing the application of your code in resolving the situation delineated above. 
   Be sure to highlight or emphasize the probabilities you find.

You can again complete this in a Python notebook with everything clearly labeled and formatted.
