# FDTD 3D CPU&GPU

* This repository provides a MATLAB implementation of 3D Finite Difference Time Domain (FDTD) methods optimized for both CPU and GPU execution. The approach aims to leverage the computational power of GPUs while addressing the limitations of Video Random Access Memory (VRAM) through an efficient use of both VRAM and system RAM.

## Key Features
* Hybrid CPU & GPU Execution: Implements a coordinated approach where constant matrices, such as field coefficients and boundary conditions, are stored in system RAM, while variable matrices, such as fields and Psi, are stored in VRAM. This allows for larger simulations by circumventing VRAM limitations.
Performance Optimization: Although coordinating CPU and GPU decreases the execution speed compared to pure GPU execution, it remains significantly faster than basic GPU code, providing a good balance between speed and memory usage.
* 3D FDTD Simulation: Enables robust simulation of electromagnetic wave propagation using the Finite Difference Time Domain method in three dimensions.
User-Friendly MATLAB Code: Contains well-documented and modular MATLAB scripts that facilitate easy modification and understanding.
Visualization Tools: Offers functions for visualizing the simulation results, allowing for comprehensive analysis of the electromagnetic fields over time.

* Although the execution speed on the GPU is awesome, Video Random Access Memory (VRAM) in this space is limited, so to address this problem VRAM and RAM are used simultaneously. Therefore, constant matrices such as field coefficients and some boundary conditions coefficients are defined on RAM and variable matrices such as fields and Psi are defined on VRAM. This solution removes VRAM limitation, but the execution speed is decreased.

* According to Fig 1(b) coordinating the GPU and CPU decreases the execution speed but it is still faster than that of the basic GPU code.

![GPU_2a](https://user-images.githubusercontent.com/94797491/152184206-d36591af-2d96-4177-9b7c-99a1a0fa5d0e.jpg)
Fig. 1.  Comparison between the execution speed of the basic GPU code, the modified GPU code, and coordinating the GPU and CPU code.
