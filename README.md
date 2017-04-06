# MAS-AirTrafficSystem
An air traffic redirecting system in a simulated environment written in NetLogo.

This was developed as a project during the Multi-Agent Systems course 2017 (Department of Informatics, Aristotle University of Thessaloniki).

<p align="center">
<img src="https://raw.githubusercontent.com/Kostis-S-Z/MAS-AirTrafficSystem/master/images/flying.gif" alt="flying image" width="360" height="360">
</p>

## Description
This project offers the creation of an airport map in the 2D space, assignment of planes to each airport and scheduling of the flights. It allows the user to "destroy" an airport in real time and cause the flying airplanes to alter their routes accordingly. The planes are trying:
- to minimise the amount of extra fuel consumed during the redirecting as well as 
- to not crash
In the project there are two techniques available for the planes to choose their new destination, after their destination airport has been destroyed.

## Controls and Interface
### Buttons
- __setup__: Creates a new map and initializes the environment
- __reset__: Resets the environment but retains the previous map
- __go__: Runs the simulation continuously
- __go once__: Runs one step of the simulation

### Sliders
- __airport_num__: The number of airports on the map (requires setup to apply)
- __airplane_num__: The number of airplanes on the map (requires setup to apply)
- __fuel_redundancy__: The extra fuel planes will carry on take off. Fuel is measured by how far the plane can travel. e.g fuel_redundancy=5 means that the plane can travel extra five units in the 2D space.
- __airplane_speed__: The travel speed of the airplanes. Does not affect the results, used only for speeding up the simulation.

### Graphs
- __Planes__: The number of planes on the map
- __Extra fuel consumed__: The extra fuel that has been consumed by all planes during the simulation
- __Redirects__: The number of redirects that happened during the simulation

### Map
Click on any airport to destroy it (turns red). Click again to bring it back.
<p align="center">
<img src="https://raw.githubusercontent.com/Kostis-S-Z/MAS-AirTrafficSystem/master/images/redirecting.gif" alt="flying image" width="360" height="360">
</p>


### The redirecting techniques and the "tactical" switch
