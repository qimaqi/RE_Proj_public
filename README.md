# RE_PE_21
Recursive Estimation programming exercise in 2021
In this project we finsih two tasks: Hybrid Extended Kalman Filter for Tracking a Boat and Particle Filter to Track a Mobile Robot.

Due to the confidentiality of the code we only show the statement and template here. If you are interested in more detail, feel free to contact me email: qimaqi@ethz.ch

# Task1: Hybrid Extended Kalman Filter for Tracking a Boat
You are driving a motor boat across a big windy lake and don’t want to get lost. You therefore decide to implement a Hybrid Extended Kalman Filter (Hybrid EKF) for tracking the position and orientation of the boat. A schematic diagram of the boat is shown in Figure below:

<img src="asset/hybrid EKF.png" alt="drawing" width="800"/> 

The challenge of this task is:
- The distance measurements from three ground-based radio stations by the river is discrete and noisy
- Angle measurements by a compass is continous but suffer from higher measurement noise.
- Angle measurements also provided by a gyroscope which is affected by sensor drift.
- The boat controlled by thrust commands rudder command. The control inputs to the boat are given at discrete time and are kept constant over the sampling interval.
- The boat dynamic is nonlinear.

To solve this task I use the Hybrid Extended Kalman Filter.


# Task2:Particle Filter to Track a Mobile Robot
<img src="asset/particle filter.png" alt="drawing" width="800"/> 

- The distance measurements between robot and wall is corrupted by large measurement noise.
- The wall location is unkonwn and it is a parameter we need to estimate.
- The initial position is unknown and uniformly distributed in the two shaded circles.

We design a PF that estimates the location and heading of the robot , as well as the offset of the left wall. The uncertainty of the left wall cause a lot of trouble for outlier. See [video](https://www.youtube.com/playlist?list=PLJKXDihfl_-ehS11WOQZinK-DLrv1CPdk) here.

To solve this problem we implement following techniques:
- online check the posterior probability if is too low we resample the position
- roughing: add noise to the sampled position
- fine tune the parameteres.

