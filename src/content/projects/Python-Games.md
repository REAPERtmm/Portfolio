---
title: 'Python-Games'
description: 'Multiple of games made with python'
pubDate: 'Dec 3 2023'
heroImage: '../../assets/Python-Games/Logo.webp'
---

# Python-Games

## Intoduction

At the time when i write this, i'm 2 years after the last push of this **project** so i dont remember every details. But the context is a project during *my first year of study*. In this project we were supposed to learn **Python** but as I was coding with Python since 2 years at this time, I started creating minigames as fast as i can. The duration of the project was **2 weeks** and I achieved to create **5 mini-project**.

---
## Project 1 : More or less

This first project is a simple **game** that follow a few rules : 

- Choose a **minimum** and a **maximum** for a *random* number to be generated.
- Set a **number of try**.
- **Try to guess** the number and the game will tell you if the objective is **more or less**.

if you guess the correct number in less than the choosed amount of try, then you win !

Before looking at what the game look like, it is **important** to notice that any **invalid input** will be **ignored** and will result in **retrying** to ask the same input. **Valid input** contains only **0123456789**.

![Invalid Argument](../../assets/Python-Games/Game1-Invalid-Argument.png)

In my **Editor**[^0], a game will look like this:

First, i take **two inputs** for the **minimum** and the **maximum** between which a random number will be generated.

![Part 1](../../assets/Python-Games/Game1-Screen1.png)

Next, you will be **asked** a **number** of try, the *higher*, the *easier*. Here i choosed to try to find a number between 0-100 in 10 try. Therefore, I guessed 50 (choose the median is a good start to eliminate half the possibilities). Here i know that the answer is **between 50 and 100**.

![Part 2](../../assets/Python-Games/Game1-Screen2.png)

Later, I encountered a number where the game said that the answer is **less** that it. So the Answer is between 75 and 87.

![Part 3](../../assets/Python-Games/Game1-Screen3.png)

Finally, I Tried different number until I guessed the **correct answer**, here it was 86 !

![Part 4](../../assets/Python-Games/Game1-Screen4.png)

Alternally, if i had **failed** to find the correct number in 10 try, this is what i would have get.

![Part 5](../../assets/Python-Games/Game1-Screen5.png)



[^0]: I'm using Pycharm as my main editor for all my python projects