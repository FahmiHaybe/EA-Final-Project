# EA-Final-Project


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
