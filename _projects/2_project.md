---
layout: page
title: Force Sensitive Motor Driver
description: Ongoing development for force responsive joints
img: assets/img/Proj/ForceMotorDriver/IMG_7232.jpg
importance: 2
category:
---
Once I completed my graduate program, I felt a huge weight lift off my shoulders. However, I also missed the insight and exploration of my multi-robot system project. I spent some time to reflect on the outcomes and where the research was lacking. One conclusion I believe was the missing physical analogy from the simulation. While we successfully built and tested one robot, the limitations from that prototype were not going to allow for productive behavior testing. The force perception on board and the noise, latency, and mechanical limitations were simply too great to effectively attribute any behaviors to the proposed model. Even if an additional prototype was built, it likely would have not been insightful.

The remedy I am proposing for this is to circumvent logic and processing of the force sensor signals. While the signal may still be observed, feedback should directly affect the motors the instant a change occurs. While this may narrow the configurable behaviors of a system with force perception, the performance gains may be significant. 

## **Goals**
I have a few explicit goals for this project which may enable a full system build to replicate my thesis work. 

- The first is to design and build a test stand utilizing a force sensor and a repeatable means of applying force. The resistance profile of the sensor does not have to be perfectly linear, linearizing will be a priority of the project. 
- The next goal is to build a custom motor driver circuit which generates a PWM signal with the resistance from the force sensor as an input. 
- The third goal of this circuit is for multi-channel support of the force sensors. Notably, how these signals should be represented in a robot's frame and how to generalize the setup.
- To communicate with the system and benchmark performance, data will need to be captured. Notably, motor speed and measured voltage from the force sensor. To achieve this task a microcontroller in the form of a Teensy will be sampling the force sensor analog signals and encoder digital signals. However, due to memory limitations, the data will need to be streamed over serial real time to a host PC which will store the data and then be analyzed. 
- Lastly, I would like to use this data to correspond to simulation as a definable behavior curve. This may evolve later depending on which direction the project goes. However, I believe there is some interesting concepts once the measurements are taken with the force sensor and validated. 

## **Current Progress**
As illustrated below, the current version of the test stand has been built with data collection currently under way. This is the second version as the first had a binding issue in the linear guide system. 


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Proj/ForceMotorDriver/IMG_7232.jpg" title="Force Measurement Test Stand" class="rounded z-depth-1" avoid_scaling=true %}
    </div>
</div>
<div class="caption">
	    Current iteration of the test stand to test the force sensitive motor driver. This is capable of repeatable and measurable force application up to 5kg. The current driver is only powering a 7.4V 2A motor, however this will be easily scaled later. 
</div>

The frame is 3D printed and features a linear guide system to allow for even, consistent, and repeatable force application onto the force sensitive resistor (FSR) at the bottom of the stand. This is achieved with a fine thread bolt which pushes a platform down and compresses a calibrated spring. The displacement of the platform is actively measured by an IMU and time of flight sensor in addition to manual measurements for validation. I have gotten the data to stream consecutively for 20 seconds at a 500Hz sample rate of the FSR and 1kHz+ of the encoder. The next steps is to validate any dropped packages, but I hope to publish results shortly along with more detailed descriptions of the circuit and data streaming software.

While the construction is mostly plastic, this is assumed stiff enough for the load capacity and early iteration of this project. I hope to move to more stiff materials in the future to increase confidence of these results. 
