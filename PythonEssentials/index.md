---
title: Python Essentials – Capstone
layout: default
---

# Python Essentials – Capstone

This page pulls together my work from **Python Essentials (8-week course)**.  
The focus was on writing clean command-line programs, using functions and loops, and building a larger “service learning” project.

By the end of the class I could:

- Read from user input and validate it
- Use lists, loops, and functions to organize logic
- Build menu-driven command-line tools
- Work with basic file I/O
- Package code in a way that another person can understand and re-use

---

## Projects Overview

### 1. CLI Calculator

**File:** `cli-calculator.py`  
**Location:** `PythonEssentials/projects/cli-calculator.py`

A command-line calculator that:

- Prompts the user for two numbers and an operation (+, −, ×, ÷)
- Handles invalid input with error messages
- Loops until the user chooses to exit

**Concepts used:**

- Input validation with `try/except`
- While loops
- Simple function to perform the calculation

You can view the code here:  
`PythonEssentials/projects/cli-calculator.py`

---

### 2. Decision Helper

**File:** `decision-helper.py`  
**Location:** `PythonEssentials/projects/decision-helper.py`

A simple decision app that:

- Asks a series of yes/no or multiple-choice questions
- Uses conditional logic to suggest an outcome  
  (for example: *“Is this port open?” → *“Check firewall rules”*)

**Concepts used:**

- `if / elif / else`
- Mapping user choices to different code paths
- Basic input sanitization

You can view the code here:  
`PythonEssentials/projects/decision-helper.py`

---

### 3. Loop & List Lab

**File:** `loop-list-lab.py`  
**Location:** `PythonEssentials/projects/loop-list-lab.py`

A practice script focused on loops and collections:

- Builds a list from user input (e.g., favorite tools, IPs, or tasks)
- Iterates over the list and prints formatted output
- Optionally performs simple analysis (counts, min/max, etc.)

**Concepts used:**

- `for` and `while` loops
- Lists and basic list methods
- Simple aggregation logic

You can view the code here:  
`PythonEssentials/projects/loop-list-lab.py`

---

### 4. Functions Lab

**File:** `functions-lab.py`  
**Location:** `PythonEssentials/projects/functions-lab.py`

This lab breaks logic into small, reusable functions.  
Examples include:

- A function that validates user input
- A function that calculates a result and returns it
- A main function that ties everything together

**Concepts used:**

- Defining and calling functions
- Parameters and return values
- Keeping `main()` separate from helper functions

You can view the code here:  
`PythonEssentials/projects/functions-lab.py`

---

## Spotlight Project – Baseball Walkup Song Player

**File:** `baseball-walkup-player.py`  
**Location:** `PythonEssentials/projects/Walkup/baseball-walkup-player.py`

This “service learning” project is a more complete program:  
a **Baseball Walkup Song Player** designed to run during games.

### What it does

- Stores a roster of players and their walkup songs
- Lets the operator select a player from a menu
- Plays the correct track for that player (or prints the selection if running without audio)
- Can be updated between games as rosters or songs change

### Why it matters

This project shows that I can:

- Move beyond one-file labs and build a usable tool
- Structure a script so someone else can run it without reading all the code
- Combine core Python skills: input, loops, functions, and simple data structures

I plan to deployed in real games for the Hocking College Hawks in 2026.

You can view the code here:  
`PythonEssentials/projects/Walkup/baseball-walkup-player.py`

---

## How to Run These Scripts

1. Install Python 3 on your machine.  
2. Clone this repository or download the `PythonEssentials/projects` folder.
3. From a terminal, run for example:

   ```bash
   cd PythonEssentials/projects
   python cli-calculator.py
