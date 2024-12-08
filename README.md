# Manifold Basis Vectors Animation

This script visualizes the basis vectors of a manifold defined by two parameters, $\phi_1$ and $\phi_2$, and simulates their evolution with respect to each other. The animation dynamically shows the changing of the basis vectors $\mathbf{e_{\phi_1}}$ and $\mathbf{e_{\phi_2}}$ on the manifold. It uses `matplotlib` for plotting and `cupy` for GPU-accelerated computation.

## Dependencies

- **matplotlib**: For plotting the 3D visualization and animations.
- **cupy**: For performing GPU-accelerated calculations.
- **FuncAnimation**: From `matplotlib` to create animations.
- **FFMpegWriter**: For saving the animation (if needed).

## Mathematical Definitions

### Position Vector ($\mathbf{R}$) on the manifold

The position vector $\mathbf{R}$ is defined in terms of the parameters $\phi_1$ and $\phi_2$:

$$
\mathbf{R}(\phi_1, \phi_2) = \left( \chi(\phi_1, \phi_2), \psi(\phi_1, \phi_2), \zeta(\phi_1, \phi_2) \right)
$$

Where:

$$
\chi(a, b) = \cos(2\pi a)\sqrt{1-b^2}, \quad \psi(a, b) = \sin(2\pi a)\sqrt{1-b^2}, \quad \zeta(a, b) = b
$$

### Basis Vectors

The basis vectors are defined as the partial derivatives of $\mathbf{R}$ with respect to the parameters:

$$
\mathbf{e_{\phi_1}} = \frac{\partial \mathbf{R}}{\partial \phi_1}, \quad \mathbf{e_{\phi_2}} = \frac{\partial \mathbf{R}}{\partial \phi_2}
$$

### Simulating the Changing Basis Vectors

The simulation visualizes the partial derivatives and the evolution of the basis vectors with respect to each other using:

$$
\frac{\partial \mathbf{e_{\phi_1}}}{\partial \phi_1}, \quad \frac{\partial \mathbf{e_{\phi_1}}}{\partial \phi_2}, \quad \frac{\partial \mathbf{e_{\phi_2}}}{\partial \phi_1}, \quad \frac{\partial \mathbf{e_{\phi_2}}}{\partial \phi_2}
$$

## Usage

### 1. Import Libraries
The script requires `matplotlib` and `cupy` for 3D plotting and GPU computation.

```python
import matplotlib.pyplot as plt
import cupy as cp
from matplotlib.animation import FuncAnimation, FFMpegWriter
