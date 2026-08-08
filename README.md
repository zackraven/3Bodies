# Three-Body Problem — Numerical Exploration

This project documents my process of learning the mechanics of the classical three-body problem and some of the related mathematical and computational areas of the problem space.

Once I have gained sufficient understanding of the problem and the computational methods used to find and verify stable systems, I will attempt to conduct my own systematic search for stable and periodic solutions, including investigating whether previously undocumented solutions can be identified.

I started this project on **20/07/2026**.

---

## 1. Initial Learning and Scripts

I began by going over the Newtonian equations which govern the problem and the derivation of the full vectorised equations for the three-body problem.

I then learnt about several numerical integration methods, including:

* Euler integration
* RK4 integration
* Symplectic integration
* Velocity Verlet integration

I investigated the disadvantages of different integrators, particularly numerical error and energy drift, and learnt about the importance of symplectic methods when studying long-term Hamiltonian systems.

I also learnt about limiting the dimensions of the problem space by setting the **centre of mass** and **centre of momentum** to zero, along with other coordinate transformations and calibrations. These allow redundant degrees of freedom to be removed and make the search and verification of systems more computationally efficient.

---

## 2. First Numerical Implementation

I learnt the Velocity Verlet integrator and wrote my first three-body simulation in Python using Jupyter and NumPy.

The initial script calculated the positions and velocities of three interacting bodies at each timestep.

I then added calculations for the total kinetic and potential energy of the system. The relative energy error was stored at each timestep and graphed using Matplotlib to visualise numerical error and assess the reliability of the integrator.

I also graphed the paths of the three bodies using several different methods.

---

## 3. Visualisation

Initially, I used basic Matplotlib graphs to show the paths of the bodies, including interactive plots with sliders.

I then experimented with different methods of visualising the three bodies, including animating the paths as GIFs in Jupyter and later exporting longer simulations as MP4 videos.

As I began calculating longer orbital evolutions, animation generation became increasingly computationally expensive. I eventually decided that the most effective method for visualising longer system evolutions was a static graph showing a trail of each body's path, with markers indicating the beginning and end of the trajectory.

This allowed me to visualise systems with far more timesteps without having to wait for long animation-generation times. This did, however, lose information about the instantaneous speed of the bodies.

This process highlighted the trade-off between the amount of information contained in a visualisation and the computational cost of generating it.

---

## 4. Numerical Stability and Close Encounters

One of the main problems I encountered was that, during close encounters between bodies, the energy error could develop very large spikes which often failed to return to zero.

This led me to investigate the relationship between timestep size and numerical accuracy.

I attempted using an **adaptive timestep** to counteract this problem. This significantly reduced the observed energy errors during close encounters.

However, I found that changing the timestep dynamically introduces an important trade-off, as the integrator is no longer straightforwardly symplectic.

This has led me to investigate the relationship between:

**timestep size → numerical accuracy → energy conservation → symplecticity → computational cost**

rather than simply attempting to minimise the energy error by continually reducing the timestep.

---

## 5. Validation Against Known Systems

Before attempting to search for new systems, I tested the implementation against previously known configurations.

I verified that systems such as:

* Sun–Planet–Moon configurations
* The classical figure-eight orbit

remained stable within my code over many orbits.

The figure-eight orbit was particularly useful as a non-trivial benchmark for testing the implementation, as it provides a known periodic solution to the equal-mass three-body problem.

These tests formed my initial exploration of the problem and helped me gain insight into how the underlying mechanics and numerical methods behave.

---

## 6. Current Position

At this stage I have developed an initial understanding of:

* The Newtonian mechanics governing the three-body problem
* Vectorised equations of motion
* Euler and RK4 integration
* Symplectic integration
* Velocity Verlet integration
* Energy conservation and numerical error
* Adaptive timesteps
* Centre-of-mass and centre-of-momentum transformations
* Numerical visualisation
* Validation against known solutions

I am now ready to move from reproducing and understanding known systems towards more serious attempts to computationally explore the problem space.

The next stage will be to develop scripts capable of systematically searching for stable and periodic configurations, while also developing reliable criteria for determining whether a candidate system is genuinely stable or periodic.

---

## 7. Future Work

The planned next stages of the project are:

1. Quantitatively compare Euler, RK4 and Velocity Verlet integration.
2. Investigate timestep convergence and numerical error.
3. Improve the treatment of close encounters.
4. Investigate alternative approaches to numerical regularisation.
5. Develop automated stability criteria.
6. Develop a systematic search across the relevant initial-condition parameter space.
7. Develop methods for identifying periodic orbits.
8. Benchmark computational performance and investigate optimisation.
9. Automatically visualise and analyse candidate systems.
10. Compare candidate solutions against known solutions in the literature.
11. Investigate whether the search can identify previously undocumented stable or periodic configurations.

---

## Technologies

* **Python**
* **NumPy**
* **Matplotlib**
* **Jupyter**
* **FFmpeg**

---

## Project Status

**Started:** 20/07/2026

**Current stage:** Numerical-method development and validation

**Next stage:** Automated search for stable and periodic configurations
