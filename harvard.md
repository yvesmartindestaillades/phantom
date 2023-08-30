---
layout: inner
title: About
permalink: /harvard/
---

# A Proprioceptive Method for Soft Robots Using Inertial Measurement Units

*Harvard Microrobotics Lab, USA - Oct. 2021 to May 2022. This work was made in collaboration with Dr. Daniel K. Bruder and Prof. Robert J. Wood.*

<img src="/img/posts/proprioception/RB8_GOOD_VERSION.gif" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 1: This project is about using IMUs to estimate the state of a soft limb</div>

### There's no silver bullet for soft robots state estimation

Soft robots are naturally compliant robots. They are great for safe human interaction, wearables, and many others (show hand example).

Though, the infinity of degrees of freedom makes their state estimation challenging. This problem has no silver bullet. Existing solutions are motion capture, which has high resolution but is expensive and indoors-bounded, and onboarded curve Sensor, which are expensive, usually custom and lead to error integration.

<img src="/img/posts/proprioception/soft_hand.png" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 2: soft robotic hand. Where would you put the sensors?</div>

### Our approach: outfit soft robots limbs with Inertial Measurement Units (IMUs)

An IMU (Inertial Measurement Unit) is a sensor system that measures and reports a device's orientation, velocity, and gravitational forces. IMUs are cheap, small, easy to use, and available off the shelf. 

By outfitting a soft arm with IMUs, we can interpolate the signals to get the state of the arm. We model the limb as a chain of flexible uniform segments. This design is specifically interesting for long limbs, as the error doesn't integrate along the arm like for bending sensors.

<img src="/img/posts/proprioception/approach.png" style="width: 100%; max-width: 1000px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 2: Outfit a soft limb with IMUs and interpolate their signals. We model the limb as a chain of flexible uniform segments.</div>


### Experimentation and results

The sensing algorithm was implemented on a 64cm-long soft limb and runs real-time. The 8 BNO055 IMUs were read through an I2C multiplexer and an Arduino board. The board was connected to a [ROS package](https://github.com/yvesmartindestaillades/State-Estimator-for-Soft-Arm-SESA), that interpolated the signals and published the state of the arm. 

At any point of the arm, the error was less than 10% w.r.t the arm length for 75% of the measurements. 


<img src="/img/posts/proprioception/shell.png" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 3: 75% of the measurements were within 10% of the arm length. This shell encapsulates 75% of the measurements.</div>

### Conclusion

This work is an additional method for proprioception for soft robots. It is a simple and inexpensive solution that can be used for long limbs. 

### Cite this work

If you use this work, please cite it as:

```
Y. J. Martin, D. Bruder and R. J. Wood, "A Proprioceptive Method for Soft Robots Using Inertial Measurement Units," 2022 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), Kyoto, Japan, 2022, pp. 9379-9384, doi: 10.1109/IROS47612.2022.9982185.
```