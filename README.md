This project documents my process learning the mechanics of the three body problem and some of the related mathematical and computational areas of the problem space.
Once I have gained sufficient understanding of the problem space and some of the computational methods used to find stable systems, I will attempt to conduct my own search for new stable solutions to the problem.

1. My initial learning and scripts.
   - I started the beginnings of this project on 20/07/2026
   - I went over the Newtonian equations which govern the problem and the derivation of the full vectorised equation for the 3 body problem.
   - I learnt about the Euler and RK4 integrators, and their respective disadvantages and energy drifts.
   - I learnt the importance of symplectic integrators for energy conservation within the problem.
   - I learnt about limiting the dimensions of the problem space by setting centre of mass, centre of momentum, and other calibrations, in order to reduce the necessary calculations to verify stable systems.
   - I learnt the velocity Verlet intergrator, and wrote my first script in python in a JUYPTER IDE, calculating a 3 body system and printing the velocities and positions at each step.
   - I added Energy error calculations, and stored Energy error at each step in an array. Then graphed it (Matplotlib) to visualise the energy drift and verify the reliability of the intergrator.
   - I graphed the path of the 3 bodies using various methods. Initially a basics matplot lib graph showing the paths with a slider.
   - I experimented with different methods of visualising the 3 bodies, animating the paths as a Gif in JUYPTER, then when I started calculating longer orbits exporting them as MP3.
   - I eventually decided the best method for visualising longer system evolutions was simply as a static graph with a trail of each bodies path, and marks for the start and end of the paths.
   - This allowed me to visualise systems with far more steps without having to wait for long animation generation times. This did of course lose the visualisation of speed however.
   - Observed that at close encounters, energy error still had massive spikes which often failed to resolve to 0.
   - Attempted using an adaptive time step to counteract this. This reduced the energy errors significantly, however causes the intergrator to stop being symplectic.
   - Verified that pre-discovered systems such as Sun-Planet-Moon and the famous figure 8 orbit remained stable within my code over many orbits.
This was my initial exploration of the problem, to gain insight into how some of the basic mechanics worked. I am now ready to move into some more serious attempts to start building scripts which can search the problem space for novel solutions.
