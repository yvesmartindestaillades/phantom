---
layout: inner
title: RRL
permalink: /rrl/
---

# Design, fabrication, modeling and control of an Origami Haptic Platform

*This project was made in collaboration with Mustafa Mete and Prof. Jamie Paik at the Reconfigurable Robotics Lab, in the context of a semester project.*

<img src="/img/posts/rrl/gif.gif" style="width: 50%; max-width: 600px; margin: 0 auto; display: block; overflow: hidden;">
<div class='caption' style="text-align: center;">
Final prototype of the DWB actuated by DC motors. </div>

## Robotics + Origami = Robogami

Robogamis are lightweight, flexible and robust structures. They are made of rigid tiles and flexible hinges. Like a paper origami, they allow by design only certain movements. They are well suited for haptics because they are flexible and can be actuated to provide force feedback.
****
In this project, I designed, built and actuated a haptic robogami controller for VR. The controller has 3 DOF, roll pitch and yaw. I developed a kinematic model of the controller and I actuated an real-life prototype using DC motor and PIDs.

<img src="/img/posts/rrl/dwb.png" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 1: Double WaterBomb robogami</div>

## Design

I used an existing design called the Double WaterBomb (DWB), an origami-
based spherical joint structure. The degrees of
freedom are all rotational and will be called roll,
pitch, yaw. As any origami-based structure, the
DW is a 3D structure folded from a 2D sheet. The
DW is controllable from its 4 bottom hinges.



<img src="/img/posts/rrl/rpy.png" style="width: 100%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 2: Roll, pitch, yaw for the Double WaterBomb robogami</div>

## Manufacturing

The design of the structure consists in drawing in 2D the Waterbombs, in order to fold them into a 3D structure afterwards. The 2D structure is a sandwich of rigid tiles in FR4 and in the middle a layer of Kapton. They are hold together by a layer of double-sided tape. 

The dimensions of the Kapton were selected so that the hinges are rigid enough for the structure to stand by itself. 

<div class='row'  style="text-align: center; margin-left: 10px; margin-right: 10px;">
<img src="/img/posts/rrl/manufacturing.png" style="width: 65%; max-width: 600px" >
<img src="/img/posts/rrl/manufacturing2.png" style="width: 30%; max-width: 600px">
</div>
<div class='caption' style="text-align: center; margin-left: 10px; margin-right: 10px;">
Figure 3: On the left, the design for the FR4 layer (rigid). On the right, the design for the Kapton layer. </div>

A challenging part of the manufacturing was to find the right distance between the tiles W_hinge, so that the hinges can fold but don't have parasites movements. See the figure below.

<img src="/img/posts/rrl/hinge_size.png" style="width: 100%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 4: The optimal distance between two tiles depending on the width of the kapton, the FR4 and the adhesive is determined experimentally. On the left, the experimental setup, on the right, the results: epsilon = 0.3mm. </div>

## Characterization

To characterize the force feedback of the DWB, I used a force sensor and a torque sensor. I measured the force and torque applied on the DWB for different angles. Measurements are made backward and forward, to account for the hysteresis. 
The setup and results are shown in the figure below.

### Setup

<img src="/img/posts/rrl/characterization_setup.png" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 5: Experimental setup for the characterization of the DWB. The DWB is actuated by an arm that holds a force sensor. </div>


### Model
<img src="/img/posts/rrl/characterization_model.png" style="width: 80%; max-width: 600px; margin: 0 auto; display: block;">


### Results

- Spring behavior in a certain range of motion around the origin with torque constants of KRoll, KP itch and KY aw. KP itch is surprisingly negative, almost zero.
- 
- Increasing torque - over-passing the spring behavior - when pushing the DW to
its extrema.

- Plastic deformation when pushing the DW in a direction, adding a Tof f component to the equation, which means an hysteresical behavior


<div class='row'  style="text-align: center; margin-left: 10px; margin-right: 10px;">
<img src="/img/posts/rrl/characterization1.png" style="width: 65%; max-width: 600px" >
<img src="/img/posts/rrl/characterization2.png" style="width: 30%; max-width: 600px">
</div>
<div class='caption' style="text-align: center; margin-left: 10px; margin-right: 10px;">
Figure 6: Torque characterization of the DWB for roll, pitch and yaw. </div>


## Modeling

I developed a kinematic model of the DWB using empirical data. The model maps the bottom-hinges angles to the joystick position.
The angles of the DW have been measured, using the DC-motors encoders on the motor actuated prototype, and
fitted to polynoms.

Inspired by the [superposition principle](https://en.wikipedia.org/wiki/Superposition_principle), I modeled the DWB as a combination of 3 independent movements: roll, pitch and yaw. 

Each movement is measured while the other two are kept constant. By fitting the data to polynoms, I obtained the following results:

<div class='row'  style="text-align: center; margin-left: 10px; margin-right: 10px;">
<img src="/img/posts/rrl/roll.png" style="width: 31%; max-width: 600px" >
<img src="/img/posts/rrl/pitch.png" style="width: 31%; max-width: 600px" >
<img src="/img/posts/rrl/yaw.png" style="width: 31%; max-width: 600px">
</div>
<div class='caption' style="text-align: center; margin-left: 10px; margin-right: 10px;">
Figure 7: Roll, pitch and yaw angles as a function of the bottom-hinges angles. </div>

It turned out that summing the models for roll, pitch and yaw allowed to predict the angles of the DWB with a good accuracy.
The model is extensively described in the [report](/assets/pdf/RRL___Semester_Project.pdf) if you want to know more.

<img src="/img/posts/rrl/model.png" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 8: The kinematic model of the DWB. C is the rest position. </div>



## Actuation

### Pouch actuators

At first, I wanted to use pouch actuators, which would bring more flexibilty to the design. I developed a system of stacked pouches to gain more range and strength. However, I had to switch to DC motors because the pouch motors were too hard to control. 


<img src="/img/posts/rrl/stacked.png" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 9: Stacked pouches actuator. </div>


### DC motors

Using the following setup, I implemented open-loop control using the model described above. The DC motors are controlled by a PID. The PID gains are tuned manually using the Dynamixel Wizard software. These motors are great btw, check them out!


<img src="/img/posts/rrl/control_setup.png" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;">
<div class='caption' style="text-align: center;">
Figure 10: Experimental setup for the control of the DWB. </div>

## Main contributions

- Enhanced the design of the DWB to make it more robust and easier to manufacture.

- Characterized the force feedback of the DWB.

- Developed a kinematic model of the DWB using empirical data.

- Implemented open-loop control of the DWB using DC motors and PIDs.


Thanks for reading! If you want to know more, check out the [report](/assets/pdf/RRL___Semester_Project.pdf) or contact me.
