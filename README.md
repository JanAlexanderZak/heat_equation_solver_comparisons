#  Heat Equation Solver Comparisons
This repository shows how three methods compare in solving the heat equation, an important partial differential equation in physics and engineering. Researchers and practitioners seek understandings into each method's strengths, weaknesses and applicability for solving the heat equation across multiple scenarios. We nondimensionalize the equations for better generality. This approach allows for greater scalability and enables more strong training. We examine several methods:
1. Analytical Solution: The exact solution derived mathematically.
2. Finite Difference Method (FDM): A numerical approach based on discretization.
3. Physics-Informed Neural Networks (PINNs): A machine learning framework that incorporates physical laws into the training process of a neural network.

## Peak
Side-by-side plots of the solutions are provided to illustrate the accuracy and characteristics of each method:

<div style="display: flex; justify-content: space-around;">
  <img src="https://github.com/JanAlexanderZak/heat_equation_solutions/blob/main/src/plots/analytical_solution.png" alt="Image 1" width="32.9%" />
  <img src="https://github.com/JanAlexanderZak/heat_equation_solutions/blob/main/src/plots/FDM_solution.png" alt="Image 2" width="32.9%" />
  <img src="https://github.com/JanAlexanderZak/heat_equation_solutions/blob/main/src/plots/pinn_solution.png" alt="Image 3" width="32.9%" />
</div>

## Variable Glossary

### Physical Parameters

| Variable | Symbol | Unit | Description |
|---|---|---|---|
| `ALPHA` | $\alpha$ | - | Non-dimensional thermal diffusivity coefficient |
| `HEAT_SOURCE_INTENSITY` | $q$ | - | Intensity of the heat source term ($\pi^2$) |
| `THERMAL_CONDUCTIVITY` | $k$ | W / (mm K) | Thermal conductivity of aluminum |
| `DENSITY` | $\rho$ | kg / mm$^3$ | Density of aluminum |
| `SPECIFIC_HEAT_CAPACITY` | $c_p$ | J / (kg K) | Specific heat capacity of aluminum |
| `THERMAL_DIFFUSIVITY` | $\kappa$ | mm$^2$ / ms | Thermal diffusivity, $k / (\rho \, c_p)$ |

### Spatial Domain

| Variable | Symbol | Unit | Description |
|---|---|---|---|
| `REFERENCE_LENGTH` | $L$ | - | Length of the computational domain |
| `NUM_OF_SPATIAL_STEPS` | $N_x$ | - | Number of spatial grid points |
| `dx` | $\Delta x$ | - | Spatial grid spacing, $L / (N_x - 1)$ |
| `X_DOMAIN` | $\mathbf{x}$ | - | Array of spatial grid coordinates |

### Temporal Domain

| Variable | Symbol | Unit | Description |
|---|---|---|---|
| `REFERENCE_TIME` | $T_{\text{ref}}$ | - | Total simulation time |
| `dt` | $\Delta t$ | - | Time step size (CFL-constrained) |
| `NUM_OF_TIME_STEPS` | $N_t$ | - | Number of time steps, $T_{\text{ref}} / \Delta t$ |
| `TIME_STEPS` | - | - | Array of time step indices |
| `TIME_DOMAIN` | $\mathbf{t}$ | - | Array of time coordinates |

### Non-Dimensionalization

| Variable | Description |
|---|---|
| `char_temp` | Characteristic temperature scale for reverting non-dimensional solution |
| `char_time` | Characteristic time scale for reverting non-dimensional solution |