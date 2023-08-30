---
layout: inner
title: About
permalink: /harvard/
---

# A Proprioceptive Method for Soft Robots Using Inertial Measurement Units

*Harvard Microrobotics Lab, USA - Oct. 2021 to May 2022. This work was made in collaboration with Dr. Daniel K. Bruder and Prof. Robert J. Wood.*

### There's no silver bullet for soft robots state estimation

Soft robots are naturally compliant robots [1]. They are great for safe human interaction, wearables, and many others (show hand example).

Though, the infinity of degrees of freedom makes their state estimation challenging. This problem has no silver bullet. Existing solutions are motion capture, which has high resolution but is expensive and indoors-bounded, and onboarded curve Sensor, which are expensive, usually custom and lead to error integration.

### Our approach: outfit soft robots limbs with Inertial Measurement Units (IMUs)

An IMU (Inertial Measurement Unit) is a sensor system that measures and reports a device's orientation, velocity, and gravitational forces. IMUs are cheap, small, easy to use, and available off the shelf. 

By outfitting a soft arm with IMUs, we can interpolate the signals to get the state of the arm. This design is specifically interesting for long limbs, as the error doesn't integrate along the arm like for bending sensors.

### Results: less than 10% error w.r.t the arm length

The sensing algorithm was implemented on a prototype and runs real-time. The 8 BNO055 IMUs were read through an I2C multiplexer and an Arduino board. The board was connected to a [ROS package](https://github.com/yvesmartindestaillades/State-Estimator-for-Soft-Arm-SESA). 

with less than 10% error w.r.t the arm length.
- 

![Approach: outfit a soft limb with IMUs and interpolate their signals. We model the limb as a chain of flexible uniform segments.](/img/posts/proprioception/approach.png)

![Results: outfit a soft limb with IMUs and interpolate their signals. We model the limb as a chain of flexible uniform segments.](/img/posts/proprioception/shell.png)
![Results: outfit a soft limb with IMUs and interpolate their signals. We model the limb as a chain of flexible uniform segments.](/img/posts/proprioception/RB8_GOOD_VERSION.gif)

