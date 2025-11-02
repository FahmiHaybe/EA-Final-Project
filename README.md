# EA-Final-Project

## Bin Packing Optimization using Ant Colony Optimization (ACO)

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

## Example output:

Iteration 200/200 -> Best bins: 13
Best overall solution used 13 bins
 Bin 0: load=99, items=[45, 54]
 ...

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
