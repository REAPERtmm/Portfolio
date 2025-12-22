---
title: 'TMM_Library'
description: 'My own C++ library that i can use on other projects (windows-only)'
pubDate: 'Nov 01 2025'
heroImage: '../../assets/TMM_Library/logo.png'
---

# TMM_Library

## Introduction

In this project that i will **continue to update**, the objective was to create a **Library** that i can use as a base to **refer** to when i need something on a new **C++ project** [^1]. Like a central point, it will help me gain time while allow me to discover ways of doing various things.

## Sommaire

1. TMM_Debugger
2. TMM_Container
3. TMM_Functional
4. TMM_Threading

### TMM_Debugger

The first thing i though about when starting this project is that i needed a **strong** and **reliable** system for **debugging** information from any project and any destination. So i made this simple to use **TMM_Debugger** which work like **std::cout** but can also output in a *log file* or in the *windows debugger*. 

### TMM_Container

The second most used thing in any project are the **container** also known as **data structure**. Here i made various container with each **their own pros and cons**. It will help me **optimize** the use of those in bigger projects.

### TMM_Functional 

This third one is inspired from the Standard Library and is a duo of class that represente respectively a **function** and a **method**, they are really **user friendly** and can be extremely useful when needed.

### TMM_Threading 

This collection is following a lecture on **multithreading** and is a wrapper to the **thread** function of the WINAPI, with some more class to use **parallelism** on any resource.

### TMM_Maths
This collection contain the building blocks for maths algebra such as Vector 2, 3 and 4 dimentional. I intend to add the Matrix. Also, I implemented a simple architecture to use the SIMD with the vector which greatly improve performence while in release. Notably on Matrices multiplication.

[^1]: For every C++ project i used CMake and Visual Studio