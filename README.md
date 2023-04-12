# Self_Driving_Car

This project builds a virtual self-driving car from sratch on a 2D map, using Deep Q-Learning model 

The environment for this self-driving car is a 2D map inside a Kivy webapp - an open source Python framework. The environment and the car will look like this:

<img width="419" alt="Screenshot 2023-04-11 231500" src="https://user-images.githubusercontent.com/77040892/231367871-fe9c46a6-02a7-4c78-a4bb-f2cd99f17c2f.png">

The whit rectangle is the shape of the car, and the three little dots are the sensors - which will be used by the car to avoid going through "obstacles". 
The blue sensor covers an area at the left of the car, the red sensor covers an area at the front of the car,and the yellow sensor covers an area at the 
right of the car

**Goal:**
- Apply AI and Reinforcement Learning to train the self-driving car to make a trip to desired place while avoiding obstacles on the road.

(in map.py)
Parameters: 
- angle: the angle between the x-axis of the map and the axis of the car
- rotation: the last rotation made by the car (we will see later that when playing an action, the car makes a rotation)
- pos = (self.car.x, self.car.y): the position of the car (self.car.x is the x-coordinate of the car, self.car.y is the y-coordinate of the car).
- velocity = (velocity_x, velocity_y): the velocity vector of the car
- sensor1 = (sensor1_x, sensor1_y): the position of the first sensor
- sensor2 = (sensor2_x, sensor2_y): the position of the second sensor
- sensor3 = (sensor3_x, sensor3_y): the position of the third sensor
- signal_1: the signal received by sensor 1
- signal_2: the signal received by sensor 2
- signal_3: the signal received by sensor 3
- goal_x: the x-coordinate of the goal (which can either be the Airport or Downtown).
- goal_y: the y-coordinate of the goal (which can either be the Airport or Downtown).
- xx = (goal_x - self.car.x): the difference of x-coordinates between the goal and the car.
- yy = (goal_y - self.car.y): the difference of y-coordinates between the goal and the car.
- orientation: the angle that measures the direction of the car with respect to the goal.

**Rewards:**
- The AI gets a bad reward of -1 if it drives onto some sand.
- The AI gets a bad reward of -0.2 if it moves away from the destination.
- The AI gets a good reward of 0.1 if it moves closer to the destination.

Simple Demo:

https://user-images.githubusercontent.com/77040892/231374683-85f0fab7-96c4-4c4b-b93d-e532f850c084.mov


**To Run The File: Use Anaconda Prompt**

Inside the terminal, enter the following:
  
	conda create -n selfdrivingcar python=3.6 

  
	conda activate selfdrivingcar
  
Installing Pytorch in the same terminal using the following:
  
	conda install -c pytorch pytorch

Installing Kivy in the same terminal:
  
	conda install -c conda-forge/label/cf201901 kivy

Then run map.py using python map.py


