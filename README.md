# Maze Navigation Robot
![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![Status](https://img.shields.io/badge/status-complete-brightgreen)
![License](https://img.shields.io/badge/license-MIT-lightgrey)


A Python simulation of a robot navigating a 5x5 grid maze using purely random movement, with no map, no memory and no planning.

## Overview

The robot starts at a fixed position in a small maze containing a few blocked cells. At every time step it picks one of four directions at random (north, east, south or west) and tries to move. If the move would take it into an obstacle or outside the maze, it stays where it is. The simulation continues until the robot reaches the goal.

This is a simple way to see how a "naive" agent behaves, and how long pure luck takes to solve a problem that a planned route would solve in a few steps.

## Features

- Maze stored as a Python dictionary in `maze.py`, mapping `(x, y)` coordinates to `'O'` (obstacle) or `' '` (empty)
- A `move()` function in `robot.py` that handles obstacles and maze boundaries
- Step-by-step logging of every move the robot makes
- Monte Carlo experiment in `main.py`: repeats the simulation thousands of times to estimate the average number of steps to reach the goal

## How It Works

1. **Maze setup (`maze.py`):** a 5x5 grid is created with a start cell, a goal cell and [3] obstacle cells.
2. **Random action:** each step, a random integer from 1 to 4 is generated and mapped to a direction:

   | Number | Action |
   |--------|--------|
   | 1 | North (N) |
   | 2 | East (E) |
   | 3 | South (S) |
   | 4 | West (W) |

3. **Movement:** the robot moves only if the target cell is inside the maze and not an obstacle.
4. **Termination:** the episode ends when the robot reaches the goal.
5. **Averaging:** the process is repeated [10,000] times, and the average number of steps is calculated (Law of Large Numbers).

## Example Output

```
Location: (4, 3), Action 'S' -> (5, 3)
Location: (5, 3), Action 'W' -> (5, 2)
...
Goal reached in [N] steps.

Average steps over 10000 runs: [your result]
```

## Getting Started

### Requirements

- Python 3.8 or newer
- No external libraries (uses only the built-in `random` module)

### Run the simulation

```bash
git clone https://github.com/[your-username]/maze-navigation-robot.git
cd maze-navigation-robot
python main.py
```

## 📁 Project Structure

```
maze-navigation-robot/
├── main.py       # runs a single episode, then the averaged experiment
├── maze.py       # builds the maze dictionary, holds obstacle/start/goal positions
├── robot.py      # move functions and the random-walk simulation
├── README.md     # project description
└── .gitignore    # keeps generated files out of the repo
```

## Possible Improvements

- Visualise the maze and the robot's path in the terminal or with a plotting library
- Compare the random robot against a smarter strategy such as breadth-first search
- Plot a histogram of the number of steps across all runs
- Allow custom maze sizes and obstacle layouts

## 👤 Author

GitHub: [@chathuranga-K](https://github.com/chathuranga-K)

I built this project to practise Python fundamentals through a simulation, covering dictionary-based data modelling, modular code across multiple files, random decision-making, boundary and obstacle handling


<p align="center">
  <a href="https://www.linkedin.com/in/chathurang" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="https://github.com/chathuranga-K" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
  </a>
</p>
