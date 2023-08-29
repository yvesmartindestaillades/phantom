---
layout: inner
title: About
permalink: /harvard/
---

# A Proprioceptive Method for Soft Robots Using Inertial Measurement Units

*Harvard Microrobotics Lab, USA - Oct. 2021 to May 2022. This work was made in collaboration with Dr. Daniel K. Bruder and Prof. Robert J. Wood.*

### There's no silver bullet for soft robots state estimation

- Soft robots are naturally compliant robots [1]. They are great for safe human interaction, wearables, and many others (show hand example).
- The infinity of degrees of freedom makes their state estimation challenging.
- No silver bullet solutions: options include motion capture or onboarded curve Sensor => error integration => drift; also expensive and custom.

### Approach: outfit soft robots limbs with Inertial Measurement Units (IMUs)

- IMUs are cheap, small, easy to use, and available off the shelf. The only downside is drift.
- By outfitting a soft arm with IMUs, we can interpolate the signals to get the state of the arm.
- Better design for long limbs, as the error doesn't integrate along the arm like for bending sensors.

### Results: less than 10% error w.r.t the arm length

- Works in real-time with less than 10% error w.r.t the arm length.
- Implemented on ROS using Arduino and bno055.

![Approach: outfit a soft limb with IMUs and interpolate their signals. We model the limb as a chain of flexible uniform segments.](/img/posts/proprioception/approach.png)

![Results: outfit a soft limb with IMUs and interpolate their signals. We model the limb as a chain of flexible uniform segments.](/img/posts/proprioception/shell.png)
![Results: outfit a soft limb with IMUs and interpolate their signals. We model the limb as a chain of flexible uniform segments.](/img/posts/proprioception/RB8_GOOD_VERSION.gif)

