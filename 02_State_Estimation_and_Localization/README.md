# An_Autonomous_Vehicle_State_Estimator

This is the final project assignment of [State Estimation and Localization for Self-Driving Cars Course](https://www.coursera.org/learn/state-estimation-localization-self-driving-cars) offered by University of Toronto on Coursera. The "es_ekf.py" file contains the state estimator. In this assignment, I implemented the Error-State Extended Kalman Filter (ES-EKF) to localize a vehicle using data from the [Carla Simulator](https://carla.org/).

## Project notes:
* The data folder contains the data you will use for the project, and the rotations.py file contains a Quaternion class and other rotation-related functions that are already implemented for you.
* The filter relies on IMU data to propagate the state forward in time, and GPS and LIDAR position updates to correct the state estimate. 
* In **part 1** you will fill in the skeleton implementation of the ES-EKF that is provided, by writing code to perform the filter prediction step and the correction step.
* In **part 2**, you will examine the effects of sensor miscalibration on the vehicle pose estimates.
* In **part 3**, you will explore the effects of sensor dropout, that is, when all external positioning information (from GPS and LIDAR) is lost for a short period of time. 

## Vehicle State Estimation on a Roadway

Kalman filtering is an algorithm that provides estimates of some unknown variables given the measurements observed over time. Kalman filters have been demonstrating its usefulness in various applications. Kalman filters have relatively simple form and require small computational power. Kalman filters are used to estimate states based on linear dynamical systems in state space format.

While recursive least squares updates the estimater o a static parameter, the Kalman Filter is able to update and estimate of an evolving state. The goal of the Kalman filter is to take a probabilistic estimate of this state and update it in real time using two steps: prediction and corretion. Starting from an initial probabilistic estimate at time **(<img src="https://render.githubusercontent.com/render/math?math=k-1">)**, our goal is to use a motion model which could be derived from wheel odometry or inertial sensor measurements to predict our new state. 