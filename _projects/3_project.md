---
layout: page
title: Sim-to-Real Space Debris Simulator
description: Simulating space debris free motion on earth to understand trajectories mirrored in space
img: assets/img/3.jpg
importance: 3
category: 
giscus_comments: true
---
This was a class project completed in conjunction with ongoing research during the 2022 spring semester. The primary objective for this project was to simulate the free body motion of space debris on a physical platform (Fanuc CR35IA collaborative robot). This would provide a means to develop control algorithms for craft bound robotics to grab the tumbling debris before full deployment.

## Goals
- Attach a box/object to the platform and simulate space debris tumbling 
- Create a virtual trajectory simulation to validate joint limits and proper debris tumbling motion
- Create a communication bridge with the fanuc controller

## Tools Used
- Matlab
- Custom python script
- ROBODK
- Ros 1 (Melodic)

## Outcomes
- Model free, tumbling motion of space debris
- Matlab generation of intial trajectories without joint limits
- ROBODK Simulation with python control and proper joint limits to validate trajectories
- ROS system to communicate with Fanuc CR35-IA and transmit preplanned trajectory in timestamped configurations 


{% raw %}
<iframe width="560" height="315"
  src="https://www.youtube.com/embed/My8vmd7egcA?autoplay=1&mute=1&loop=1&controls=0&rel=0"
  title="Simulation Video"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>
{% endraw %}

{% raw %}
<iframe width="560" height="315"
  src="https://youtube.com/embed/yx0fwhHJBRw?autoplay=1&mute=1&loop=1&controls=0&rel=0"
  title="Simulation Video"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>
{% endraw %}

{% raw %}
<iframe width="560" height="315"
  src="https://youtube.com/embed/nI5H-AkyNOA?autoplay=1&mute=1&loop=1&controls=0&rel=0"
  title="Simulation Video"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>
{% endraw %}
