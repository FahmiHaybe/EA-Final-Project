# EA-Final-Project

## Bin Packing using Ant Colony Optimization (ACO)

In order to minimize the number of bins required to pack all products inside a certain capacity, this project uses Ant Colony Optimization (ACO) to solve the Bin Packing Problem.

### Features:

- **Customizable Parameters**: Modify temperature, pheromone decay, ants, and iterations.
- **Heuristic + Pheromone Search**: Integrates residual-space heuristics with pheromone learning.
- **Rank-Based Updates**: Reinforces pheromones for top-performing solutions.
- **Visualization**: Plots of convergence and load distribution for every instance of the dataset.
- **Performance metrics**: include runtime, bins used, unused space, and comparison with the most well-known outcomes.

### How to Run:
Eight u120 instances were combined into one JSON file named binpack_u120.json. Each problem includes the instance name, bin capacity, best-known solution, and a list of item sizes. 

You just have to run the notebook cells one by one to execute the algorithm.
Each part of the notebook will:

**1.** Load the dataset (binpack_u120.json)

**2.** Run ACO on each problem instance

**3.** Display convergence plots, load distributions, and summary tables

### Example output:
```python
Iteration 200/200 -> Best bins: 13
Best overall solution used 13 bins
 Bin 0: load=99, items=[45, 54]
 ...
```
**To run**: open the notebook → run cells in order → view results and plots.

  

## Optimize Classic Benchmark Functions using Particle Swarm Optimization (PSO)

This project implements Particle Swarm Optimization (PSO) to optimize several classic benchmark functions commonly used in optimization problems. The benchmark functions include:

- **Sphere Function**: A simple quadratic function used to test convergence.
- **Rosenbrock Function**: A non-convex function used to evaluate optimization algorithms' ability to handle narrow, curved valleys.
- **Rastrigin Function**: A multimodal function with many local minima, testing the algorithm's ability to escape local optima.
- **Ackley Function**: A complex multimodal function used to test convergence in highly irregular search spaces.

### Features:
- **Customizable Parameters**: Adjust the number of particles, dimensions, and iterations.
- **Early Stopping**: Stops the optimization process when a predefined fitness threshold is reached.
- **Visualization**: Includes convergence plots, mean fitness curves, and boxplots for performance comparison.
- **Performance Metrics**: Reports mean, median, standard deviation, best, and worst fitness values, along with success rates and runtime.

### How to Run:
1. Set the desired number of runs and dimensions in the `run_experimental` function.
2. Execute the script to optimize the benchmark functions.
3. View the results, including convergence plots and statistical summaries.

### Example Usage:
```python
np.random.seed(42)
for num_dimensions in [2, 10, 30]:
    results = run_experimental(num_dimensions=num_dimensions)
    plot_boxplots(results, num_dimensions)
```
## 0-1 Knapsack Optimization using Bees Algorithm (BA)
The 0-1 Knapsack issue is a traditional combinatorial optimization issue where the objective is to maximize the total value of items in a knapsack without going over its weight capacity. This project uses the Bees Algorithm (BA) to solve the problem. The technique, which combines local search, probabilistic selection, and adaptive exploration to effectively explore the solution space, is modeled after the natural foraging behavior of honeybees.

### Features:
- **Customizable Parameters**: Adjust the number of bees, onlooker bees, limit for scout phase, number of iterations, and neighborhood exploration settings.
- **Greedy Initialization**: Includes a heuristic-based starting solution using the best value-to-weight ratio.
- **Neighborhood Search**: Employs bit-flipping to explore solutions locally.
- **Scout Phase**: Introduces new random solutions to prevent premature convergence.
- **Repair Mechanism**: Ensures feasibility by removing items if the total weight exceeds capacity.
- **Convergence Visualization**: Tracks best and average fitness values over iterations.
- **Performance Metrics**: Reports best-found solutions, percentage of known optimum, runtime, and stability across multiple runs.

### How to run:
**1.** Create instances of your knapsack problems (such as WEING1, WEING2, WEISH01, WEISH02, WEISH19, and WEISH20) with values, weights, and capacity in a JSON or Python-friendly format.

**2.** Run the given Python script or notebook cells one after the other. Every action will: 1. Open the dataset. 2. Set up the population of bees. 3. Execute the Bees Algorithm repeatedly use local machinery for scouting, repair, and search. 4. Record best and average fitness for convergence analysis

**3.** View convergence plots and solution statistics for each instance.

### Example output:
```python
Dataset WEING1 -> Best value: 1650
Selected items: [2, 5, 7, 10]
Total weight: 50
Achieved: 100% of known optimum
Runtime: 0.12 seconds

Convergence plot generated for first run.
```

## Solving FrozenLake with Reinforcement Learning (Q-Learning)
In this project, the FrozenLake-v1 environment from Gymnasium is solved using Tabular Q-Learning. The objective is to teach an agent how to safely go from a start tile (S) to a goal tile (G) in a slippery grid world while avoiding holes (H). The performance of the trained agent is compared to both a basic heuristic policy and a random policy baseline.

### Features: 
- **Customizable RL Hyperparameters**: Modify learning rate, discount factor, epsilon decay schedule, and training duration.
- **Greedy Exploration:** Supports both linear and exponential epsilon decay strategies.
- **Tabular Q-Learning Agent:** Uses a Q-table of size (n_states × n_actions), updated using temporal-difference learning.
- **Baseline Comparisons Includes:**
  - Random Policy (uniform random action selection)
  - Heuristic “go toward the goal” police
  - Trained Q-learning policy
- **Environment Understanding Tools:**
  - Grid visualization with labeled components
  - Reward structure explanation
  - Stochastic transition dynamic (slippery floor with 2/3 slip probability)
- **Training & Evaluation Plots:**
  - Episode rewards with moving averages (500-episode window)
  - Cumulative reward over training
  - Success rate curves
  - Episode length distributions
  - Algorithm comparison bar charts
- **Multiple Map Sizes:**
Runs experiments on 6×6 and 8×8 FrozenLake grids.

## How to run:
The code automatically executes experiments combining two map sizes (6×6, 8×8) with two epsilon decay strategies (linear, exponential)

### Main Experiments (4 configurations)
1. **Environment Setup:** Creates FrozenLake-v1 environment with deterministic map generation (seed-based)
2. **Visualization:** Displays grid layout showing start (S), frozen tiles (F), holes (H) and goal (G)
3. **Training:** Runs 20,000 episodes of Q-learning with:
  - ε-greedy action selection
  - Temporal-difference Q-table updates
  - Tracking of rewards, success rate and episode length
4. **Evaluation:** Tests three policies over 10,000 episodes each:
  - Trained Q-learning agent (greedy evaluation)
  - Random baseline (uniform random actions)
  - Heuiristic baseline (moves toward goal)
5. **Visualization:** Generates training curves, success rate plots and performance comparison charts


## Example output:
### Grid Visualization
```python
SFFFHF
FFFFFH
FHHFFF
HFFFFF
FFFHFF
FFFHFG
```

### Performance Metrics

```python
--- Evaluating trained Q-learning policy ---
Q-Learning - Success Rate: 57.80%, Avg Steps: 78.64, Avg Reward: 0.578

--- Evaluating random policy baseline ---
Random Policy - Success Rate: 0.21%, Avg Steps: 8.27

--- Evaluating heuristic policy baseline ---
Heuristic Policy - Success Rate: 5.20%, Avg Steps: 7.92
```

## Hyperparameters
**Default Configuration:**
  - Learning rate (α): 0.8
  - Discount Factor (γ): 0.995
  - Initial Epsilon (ε₀): 1.0
  - Final Epsilon (ε_min): 0.001
  - Exponential Decay Rate: 0.999
  - Training Episodes: 20,000
  - Evaluation Episodes: 10,000
  - Episode Step Limit: 200 (safety cutoff)
