# Software Architecture Notes

Core Capabilities
* Take a photo
* Store a photo on Memory Card
* Recieve Messages from Cell
* Send messages from Cell
* Start RPi
* Stop RPI
* Start Motor
* Stop Motor


Idle State
* Explore -> Moving State -> Sensing State
* Measure Battery -> Charge State


Interrupts / Events
* Incoming communication
* Low Battery
* High Temperature

User Story
* I want the rover to move forward 1 ft. and take a photo, update gps location, and send the information to the operator.


This is what a sequential motor control loop looks like in arduino-style:

```
  setPin(MOTOR_A, 100)
  sleep(5)
  setPin(MOTOR_B, 100)
  sleep(100)
  setPin(MOTOR_A, 0)
  setPin(MOTOR_B, 0)
```

But can there be other tasks going on at the same time? That might prove more capable, but at the considerable cost of increased complexity.

How much interrupt driven features should we attempt to support vs. serialized command architecture?
