# CarND-PID-Controller
Self-Driving Car Engineer Nanodegree Program -Term 2 Project

---

## Effect of P, I, D Parameters

* The PID controller has the 3 parameters Proportional, Integral & Derivative
* The Proportional term alone overshoots the car and almost never reaches the desired angle
* The Derivative term is added for the car to reach the desired angle much faster and in a definite time
* The integral term helps when the car has manufacturing defects. For example, when the wheels of the vehicle are deviated slightly, with a PD controller, it is impossible to reach the desired angle. The integral term play a crucial role here. Since we are using a simulator here, the Integral term is of no advantage

<h2>Tuning of Parameters </h2>

- The tuning of hyper parameters is done **manually** and K~p~ & K~d~ are found. The K~i~ is assumed to be zero (since we are using simulator)

- Having a low value of K~p~ results in the car not turning adequately at the turnings, whereas a high value would result is too much oscillation of vehicle as it would never reach the desired steering

- Having a low value of K~d~ results in the car oscillating as it would never reach the  desired steering, whereas a high value would make it difficult at sharp turn as the vehicle will take long time to respond

- Instead of having a constant value for throttle all situations of straight line or curve, a PID controller for throttle would make the vehicle turnings more robust. An alternate way to this is to assume the throttle as function of steering value. The following assumption is used 

  ​                             $throttle = 0.75 - (0.3*|steering\ \ value|) $		

