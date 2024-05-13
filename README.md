# MineSweeper
Part of Harvard CS50 AI course. MineSweeper game with AI elements.

## About project
This project is a task described under following <a href="https://cs50.harvard.edu/ai/2024/projects/1/minesweeper/"> link</a>. In shortcut: this a minesweeper game, where you can use AI in order to make a safe move for you. If no safe move is possible, a random move is made. AI is implemented using prepositional logic described in the next section.

![image](https://github.com/kubawini/MineSweeper/assets/93740269/23139def-dfcb-4f12-908b-3679d6e66812)

All UI elements have already been given. All classes and methods regarding prepositional logic have been implemented by myself.

## About solution
Knowledge is represented by sentences constructed like this:

```python
{A, B, C, D, E} = n
```

where {A, B, C, D, E} are cell indexes and n is a number of cells that are known to contain bombs between all {A, B, C, D, E} cells.

It turns out that all inferences one can take are described by 5 simple rules

* if {A, B, C} = 0 then A, B, C are safe,
* if {A, B, C} = 3 then A, B, C are bombs,
* if {A, B, C} = 2 and C is safe then {A, B} = 2,
* if {A, B, C} = 2 and C is mine then {A, B} = 1,
* if {A, B, C, D, E} = 2 and {A, B, C} = 1 then {D, E} = 1.

First four inferences seem to be quite logical and they need no further explanation. Regarding last inference: more generally, any time we have two sentences set1 = count1 and set2 = count2 where set1 is a subset of set2, then we can construct the new sentence set2 - set1 = count2 - count1. Consider the example above to ensure you understand why that’s true.

## Prerequisities
In order to run the projects, there is need to install pygame package. For windows:

```bash
pip install pygame
```
