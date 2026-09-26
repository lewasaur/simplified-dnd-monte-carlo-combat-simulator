# D&D Monte Carlo Combat Simulator

A Python-based Monte Carlo simulation of Dungeons & Dragons-style 1v1 combat, built to explore combat outcomes and evaluate how simulation size affects the stability of estimated win rates.

## Project Overview

A single D&D combat encounter can be heavily influenced by random dice rolls. This project simulates the same encounter thousands of times to estimate combat outcomes across many possible rolls.

The test scenario pits **Regnar Torsten**, a friend's D&D cleric, against a **Dire Wolf**. Regnar normally has access to spells, but this scenario assumes he has exhausted his spell slots and must rely entirely on his medium armor and greatsword.

The two combatants have relatively similar offensive stats. Regnar has higher AC, attack bonus, and average damage per hit, while the Dire Wolf has substantially more HP. The simulation tests how these differences translate into overall win probability.

The simulator models:

* Initiative
* Armor Class (AC)
* Attack rolls
* Critical hits
* Damage rolls
* Hit points
* Combat rounds

Fight-level results are also recorded, including the winner, remaining HP, hits, misses, critical hits, total damage, and number of rounds.

## Monte Carlo Stability

Before using the simulator for further analysis, I tested how the number of simulated fights affects the stability of the estimated win rate.

Simulation sizes of **100, 1,000, 10,000, and 100,000 fights** were first compared individually.

The results varied noticeably at smaller sample sizes, demonstrating that a single simulation run can be affected by random variation. Estimates from the larger simulation sizes were much closer to one another.

However, comparing each simulation size only once does not demonstrate that the estimates are consistently stable.

To test this more reliably, each simulation size was therefore repeated **10 independent times**.

The repeated-run experiment demonstrates how estimated win rates become less variable as the number of simulated fights increases. At larger simulation sizes, estimates cluster increasingly tightly compared with the substantial variation observed in smaller samples.

Based on this stability analysis, **100,000 simulations per scenario** was selected as the baseline for future analysis.

## Technologies

* Python
* Pandas
* Matplotlib
* Jupyter Notebook

## Project Structure

The notebook progresses through:

1. Character configuration and stat comparison
2. Combat mechanics
3. Single-fight simulation
4. Fight-level result logging
5. Monte Carlo simulation
6. Simulation-size comparison
7. Repeated-run stability testing
8. Visualization and interpretation

## Future Work

The simulator can be extended into a sensitivity analysis to investigate questions such as:

* How do AC and HP affect survivability, combat duration, and win probability?
* How much does attack bonus affect hit rate and win probability?
* How strongly does initiative influence combat outcomes?
* With the same attack and damage bonuses, does damage distribution (such as 2d6 vs. 1d12) meaningfully affect average damage or win probability?
* How strongly are critical hits associated with winning an encounter?

Additional D&D mechanics such as advantage/disadvantage, multiple attacks, spells, class abilities, conditions, and other combat mechanics could also be incorporated into future versions.

## Limitations

This project intentionally models a simplified version of D&D combat. It focuses primarily on basic weapon attacks and does not currently account for spellcasting, class abilities, conditions, movement, tactical decision-making, or other advanced combat mechanics.

As a result, the estimated win probabilities represent outcomes under the assumptions of the simulator rather than every possible outcome of a full tabletop encounter.
