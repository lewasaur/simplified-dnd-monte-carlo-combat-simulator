# D&D Monte Carlo Combat Simulator

A Python-based Monte Carlo simulation of Dungeons & Dragons-style 1v1 combat, built to explore combat outcomes and the effect of simulation size on estimate stability.

## Project Overview

A single D&D combat encounter can be heavily influenced by random dice rolls. This project simulates the same encounter thousands of times to estimate combat outcomes across many possible rolls.

The test scenario pits **Regnar Torsten**, a friend's D&D cleric, against a **Polar Bear**. Regnar normally has access to spells, but this scenario assumes he has exhausted his spell slots and must rely entirely on his medium armor and greatsword.

The simulator models:

* Initiative
* Armor Class (AC)
* Attack rolls
* Critical hits
* Damage rolls
* Hit points
* Combat rounds

## Monte Carlo Stability

Before using the simulator for further analysis, I tested how the number of simulated fights affects the stability of the estimated win rate.

Simulation sizes of **100, 1,000, 10,000, and 100,000 fights** were first compared individually.

Because a single run can itself be affected by random variation, each simulation size was then repeated **10 independent times**.

The repeated tests showed that smaller simulations produced substantially more variation in estimated win rate, while larger simulations produced increasingly consistent estimates. At **100,000 fights per run**, estimates clustered tightly around approximately **27–28%** for Regnar.

Based on this stability, 100,000 simulations per scenario was selected as a baseline for future analysis.

## Technologies

* Python
* Pandas
* Matplotlib
* Jupyter Notebook

## Project Structure

The notebook progresses through:

1. Character configuration
2. Combat mechanics
3. Single-fight simulation
4. Monte Carlo simulation
5. Simulation-size comparison
6. Repeated-run stability testing
7. Visualization and interpretation

## Future Work

The simulator can be extended into a sensitivity analysis to investigate questions such as:

* How do AC and HP affect survivability, combat duration, and win probability?
* How much does attack bonus affect hit rate and win probability?
* How strongly does initiative influence combat outcomes?
* With the same attack and damage bonuses, does damage distribution (such as 2d6 vs. 1d12) meaningfully affect average damage or win probability?
* How strongly are critical hits associated with winning an encounter?

Additional D&D mechanics such as advantage/disadvantage, multiple attacks, spells, class abilities, and conditi
