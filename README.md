# simplified-dnd-monte-carlo-combat-simulator

# D&D Monte Carlo Combat Simulator

A Python-based Monte Carlo simulation of Dungeons & Dragons rules
1v1 combat.

## Project Overview

This project simulates repeated combat encounters using randomized
dice rolls and compares results across different simulation sizes.

The goal was to explore how increasing the number of Monte Carlo trials
affects the stability of estimated combat outcomes.

## Features

- D20 attack and initiative rolls
- Armor Class and attack bonuses
- Configurable damage dice
- Critical hits
- Hit point tracking
- Initiative order
- Fight-level statistics
- Monte Carlo simulation
- Pandas-based result analysis
- Simulation convergence analysis

## Technologies

- Python
- Pandas
- Matplotlib
- Jupyter Notebook

## Key Result

The estimated win rate varied substantially with only 100 simulated
fights but became increasingly stable as the simulation count increased
to 1,000, 10,000, and 100,000 trials.

## Possible Future Improvements

- Combat-stat sensitivity analysis
- Advantage/disadvantage
- Multiple attacks
- Class features
- Spellcasting
- Additional visualization and statistical analysis
