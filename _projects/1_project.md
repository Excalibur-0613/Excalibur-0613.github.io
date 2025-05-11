---
layout: page
title: Thesis
description: Multi-Robot Collaboration via Contact Perception & Non-Prehensile Object Transportation
img: assets/img/12.jpg
importance: 1
category: 
related_publications: true
cv_pdf: BenjaminRuss_Thesis.pdf
---
To round off my graduate tenure at the University of Cincinnati, I explored the interaction of mobile robot systems relying on contact to communicate. This work was completed within the Embodied and Interactive Systems laboratory overseen by Dr. Tamara Lorenz whom I am grateful for her guidance and mentorship. 

At the onset of this project, the fundamental question that I formulated was: 

*What behaviors and structures will arise from a system coordinating strictly with implicit communication? Additionally, how will tasking this system with transporting an object more massive than one agent of this system adapt to a non-prehensile condition?*

With this question, my vision for this project has been a means for robots to be operational alongside humans without barriers or separation. Simultaneously, enabling robots to directly contact within a complex system may naturally cooperate the individuals for greater system achievements. My desired outcome is creating a system of smaller robots at scale for moving objects rather than larger AGVs or AMRs. Lastly, I hope to generally apply this framework to industrial arms and other robotic systems to better generalize to tasks and complex workspaces.
## **Objectives**

1. Develop a trajectory planning model best suited to handle dynamic environments with a target position and current position feedback
2. Develop a multi-robot system in simulation to develop a control system in ROS and observe theoretical behavior with varying dynamic properties and number of active agents
3. Build a physical concept as simulated and better understand the measurement of applied force for mobile robots

## **Simulation Challenges & Outcomes**

While the scope for this question was large, it holds some exciting challenges. Firstly, coordinating agents with contact as the sole means of communication challenges much of the status quo for mobile robot systems. Many current systems are relying on laser range finder, optical, and/or ultrasonic for localization, object detection and obstacle avoidance. This works perfectly fine in simple, static or mostly static environments. Alternatively if the workspace of a robot with other agents (humans or robots) are in perfect direct communication with each other this perception is non-problematic. However, in practice any unexpected and dynamic agents, obstacles, or features often prove too much information for the aforementioned optical/ultrasonic systems to react quickly. In theory, adding contact feedback provides a last resort for the robot to stop or maneuver instead of stopping or faulting in the case of an unexpected contact. Furthermore, an opportunity for a "language" or queues to form between the robots while completing a task. Ultimately in my work, a simple version of this emerged by maintaining contact with a fellow agent once contact was established. Throughout testing, this could be modulated with the dynamic variables I outlined in my thesis in addition to other variations of the contact behavior. However, this tendency to maintain contact may have been assisted by the common task between the agents. 


The next challenge is stability. When connecting the two robots together with minimal communication, each controller instantaneously has a number of new stimuli to overcome. The first is a change in position depending on the impulse of the collision. The feedback of the actuator input and spatial perception may decouple depending on how great the collision is. The next is the stiffness/restitution of the materials of the robot. Many methods have overcome this factor during collision. However, it is still present in the interaction and does impact the physical interaction, especially at scale. The next is a doubling of the inertia of the controller to account (assuming each robot is identical). Lastly is the resistance from the other robots motors. Some energy with this method will always be lost pushing into the other robot while attempting to maintain contact. Ultimately, my testing and controller implementation showed that one additional robot is not an issue. However, when many robots are introduced into the system and encouraged to complete the same task in the same workspace, chaos begins to overtake the system. This presented as many different behaviors. The first was an oscillating motion in the robot which was observed in the heading data as high frequency oscillations. The next was separation from the group near the target object and holding still or "walking" in place for a moment before stabilizing the controller. This was deemed as the "Growing DOF Problem" which was not surmounted in this project. Some of my current thoughts to stabilize this problem revolve around increasing the feedback modalities, further investigating the simulator force calculation, and implementing a reinforcement learning or CNN/Deep Neural Network method to remove some dynamic dependencies within the controller. 


The last prominent challenge I faced during this thesis project was the lack of support for contact simulation in the traditional ROS/Gazebo simulation pipeline. As mentioned prior, the existing art has many options regarding vision and optical localization and mapping libraries. However, some inspiration may be taken from FEA or other existing stress solvers to better calculate and handle applied and resultant forces in robotic simulations. While some additional time could have been spent on a custom solution, it was a large time investment that was outside the scope of this work. However, after submitting my thesis, I noticed a significant increase in publications proposing various methods of simulated and physical contact methods. The result of this seems to be some development in the simulation space in ROS and other simulators which I hope to contribute to some day. 

## **Physical Robot Challenges & Outcomes**

With the assistance of my senior capstone group (1 Mechanical 2 Computer Engineering students), we plotted out a means to replicate the capabilities as practically as possible. The frame was 3D printed out of ABS and the sensors, logic, and power distribution were commodity electronics. This illustrates the first challenge for this project, the load cells chosen to measure force were not robust. Notably, once a load cell is overloaded it is no longer usable due to the de-lamination of the epoxy which bonds the strain gauge to the metal substrate. The same is true for shock, even if load is appropriate. While some countermeasures could have been implemented to prevent overloading, shock could not be guaranteed and was a flaw in this design. Furthermore, the load cells are incredibly temperature sensitive and delaminate outside a small temperature range. Reflecting on this choice, there may be some better options today and with more funding. Ultimately, the robot did have some basic movement it did not demonstrate the simulation behavior and responsiveness to force as expected. The likely culprit for this is the force measurement system and some software bugs preventing data acquisition and flow throughout the controller. If I were to redesign this system, it would be a multichannel force controller where sampling is not directly required. Some of this vision can be seen in my ongoing projects on this site. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Proj/Thesis/IMG_4657.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Proj/Thesis/IMG_4667.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
