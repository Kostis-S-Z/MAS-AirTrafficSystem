# MAS-AirTrafficSystem
An air traffic redirecting system in a simulated environment written in NetLogo.

This was developed as a project during the Multi-Agent Systems course 2017 (Department of Informatics, Aristotle University of Thessaloniki).

<p align="center">
<img src="https://raw.githubusercontent.com/Kostis-S-Z/MAS-AirTrafficSystem/master/images/flying.gif" alt="flying image" width="360" height="360">
</p>

## Description
This project offers the creation of an airport map in the 2D space, assignment of planes to each airport and scheduling of the flights. It allows the user to "destroy" an airport in real time and cause the flying airplanes to alter their routes accordingly. The planes are trying:
- to minimize the amount of extra fuel consumed during the redirecting as well as 
- to not crash
In the project there are two techniques available for the planes to choose their new destination, after their destination airport has been destroyed.

## Agents
### Planes
They fly from airport to airport. They make decisions regarding which airport to fly to. When in the air, they carry an amount of fuel. They are refueled only before the take off. When an airplane runs out of fuel in mid-air, it crashes.
### Airports
They have a certain capacity of airplanes that they can host. They only communicate with airplanes to let them know if there are any free spots.

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


## The redirecting techniques and the "tactical" switch
Suppose the following scenario: A plane is mid-air flying when its destination is destroyed. At this point, the plane needs to find another airport to land.

### First approach (tactical switch off)
In the first approach, the planes choose as destination the nearest airport with an empty spot, and start flying towards there. However there is a good chance that they won't have enough fuel and they will eventually crash. This is the simplest and least effective approach.

### Second approach (tactical switch on)
In the second approach, the plane tries to find the nearest airport with an empty spot, that it is close enough to fly without crashing. If there is no such airport, it redirects to the nearest airport (let's call this airport A). To free space from airport A, it asks an airplane heading to airport A to redirect. The second airplane will follow the same approach to find a new destination.

Experiments with this technique have shown a considerable decrease in the number of crashes.
