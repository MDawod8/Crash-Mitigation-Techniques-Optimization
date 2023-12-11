Objective Function 1 :
The first objective function we will use will be calculating a variable called the Potential Crash Severity Index (PCSI), which is considered an indication of how severe and dangerous the crash will be.
The range of this Index is from 1 (least impact) to 6 (Strongest impact). Our optimization techniques will aim to get the index to reach a value of 2 or less.
There are 3 core factors that affect the crash severity index which are the relative speed, the relative heading angle, and the mass ratio.
The relative speed is the difference between the speed of the car and the speed of the obstacle divided by the distance between them.
PCSI(V1)=((V1-V0)/D) Where V1 is the speed of the vehicle, V0 is the speed of the obstacle and D is the distance between the obstacle and the vehicle.
The relative heading angle is the difference (in degrees) in the orientation of the vehicle and the obstacle.
The mass ratio is the ratio between the mass of the obstacle (W0) and the mass of the car (W).
All these 3 factors affect the PCSI by a certain weight. However, in our problem, we will assume that they affect the index equally and therefore the constants beside each factor will be
considered 1/3.
Our decision variables for this function will be the velocity of the car and the relative heading
angle between the car and the obstacle.
The constraint to change the relative heading angle will be the maximum steering angle of
the car which we will assume to be 40 degrees which means that the heading angle cannot
change by more than 40 degrees.

Also, there will be a constraint regarding the velocity where there will be a limit to how much
the velocity can change and this will depend on the maximum breaking acceleration that can
be produced by the car’s braking system. We will assume this acceleration to be 8 meters per
second squared. We also need the expected time before collision which will be calculated as
follows:
T=D/delta(V), where D is the distance between the car and the obstacle and delta (v) is the velocity of my car relative to the obstacle. Using T and a=-8 we can get the minimum allowed
velocity before collision using this equation:
-8=((Vf-V)/T) where Vf is the minimum final velocity of the car.


Objective Function 2 :
Given the ego vehicle states along a specific trajectory, along with the predicted obstacle
vehicle states, the unavoidable collision will be evaluated with the crash severity index (CSI)
model, which is a more generalized model for various collision patterns, e.g. oblique collision. Here, the main idea is to obtain CSI according to the proportion of energy absorption
in a collision, which is determined by the physical properties, motion states, and the geometric
relationship of both vehicles in the predicted collision.
Our second objective function will be calculating the Crash severity index CSI using the following equation :
where EES1 is the energy equivalent speed of vehicle 1 (ego vehicle), VcPDOF is the velocity in the principal direction of force (PDOF) of both vehicles, i is the coefficient of restitution,
Rk = K1/K2 is the stiffness ratio of the two vehicles, and Rm = m1/m2 is the mass ratio of the two
vehicles. For each vehicle, the factor of mass reduction is defined as =Psquared/(Psquared +
Hsquared), where P is the radius of the gyration of the vehicle and H is the force arm.
Dimensions of the car which are the length and width of the car are considered decision variables as based on these values the moment of inertia of the car around the z-axis is calculated.
Then from the moment of inertia, the radius of gyration (p) of the car is calculated. The factor
of mass reduction (Y) is calculated using the radius of gyration (p) and the force arm (H) Then
this factor enters the equation of the crash severity index. Therefore changing the dimensions
of the car will affect the crash severity index.
Some assumptions have been made for simplicity. Firstly, to facilitate the calculation of
the moment of inertia of the car, I assumed that the car had a rectangular shape. Using this
assumption I could say that I can successfully calculate the moment of inertia (I) of the car
around its axis of rotation using the following equation :
Another assumption that I made was that the force arm (H) for both my car and the obstacle car
would be = 0.25(L) where L is the length of the car. I made this assumption as it would be difficult
to calculate the force arm based on the geometry of the car and the crashing conditions. Finally, I assumed that the length of the obstacle vehicle is 3.8 m and the width is 1.5 m which
is the minimum length and width for any car.

Constraints for this function are simple as the minimum length allowed for any car is 3.8 m
while the maximum length is 4.9 m and for the width, the minimum value allowed is 1.5 m and
the maximum value allowed is 2 m so, I can keep changing the dimensions as much as I want
to obtain the best crash severity index however, my dimensions cannot go out of these ranges.
