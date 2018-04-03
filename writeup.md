# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

The goal of this project is to implement PID controller in C++. The PID controller is used for determining the searing angle of a simulator by calculating the Cross Track Error (CTE). 

## Reflections

The 3 parameters have the following effect

### P stand for proportional

This is the ratio the car steers in the direction to where it should go. The bigger the ration the faster/harder the car steers to the right direction. However a big value would overshoot the target and the car would have to steer back to correct the new error it has it self caused. This would lead to the car swing left and right which would be no fun for the passenger. 
I've found that a value between 0.1 and 0.3 works reasonably well.

### D stand for differential

This is the radio by witch the car would steer back as the CTE gets smaller. This parameter determines how smoothly the car would straiten up to the right direction. 
I've found that a bigger value has better effect so in the code I've left a value of 6. So the car would drive more in a straight line. 

### I stand for integral

This parameter is used to catch a recurring error over time like drifting slightly to the right. If this value is big the car gets very bias towards towards the error and starts making full circles. This value should be small so it doesn't make the car bizarre (could find a better term)

