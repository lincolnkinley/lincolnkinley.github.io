---
title:  "Think Tank"
layout: single
permalink: /robotics-projects/Think-Tank/
collection: robotics-projects
---

{% include figure image_path="/assets/images/robotics/Think_Tank.jpg" alt="Think Tank" %}

The Think Tank is the first robot I've ever worked on. I had just arrived as a freshman at Southern Illinois University Carbondale and quickly joined the Robotics Club. At the time, they were preparing to go to the 2015 ATMAE National Robotics Competition, and had been working on their design since early 2015.

The ATMAE National Robotics Competition is held by the Association of Technology, Management, and Applied Engineering every year, and typically is typically a obstacle course and task based competition, but the rules change every year. In 2015 those rules were go through an obstacle course featuring a burlap sack draped over PVC, a teeter totter, autonomously picking up blocks that spell out ATMAE, then going backwards through the obstacle course to the beginning and spelling out ATMAE with the collected blocks.

{% include figure image_path="/assets/images/robotics/think_tank_early.png" alt="Early work on the Think Tank" %}

The Think Tank was a welded steel cube on treads, with an internal conveyor belt system, an external 3-DOF 3D printed robot arm, and an external dustpan. Instead of tires we used tank treads for tank steering. We controlled the Think Tank by connecting the onboard Raspberry Pi and a laptop with a controller to a WiFi network. It was a nightmare to control.

My first task for this robot was to design a method to pick up the 3D printed blocks. My first thought was use suction, however the grooves in the blocks from the layers of 3D printer prevented suction from getting a good enough seal to lift them up. After experimenting, we moved onto the idea of a dustpan that would be able to scoop the blocks up. This is ultimately what we went with, and it worked quite well. I also worked with the electronics and software team a bit, but at the time I lacked the skills to help in any meaningful way. I did start learning how to use Python though.

Our major disaster with the Think Tank occurred about one week before the competition. We had finally put the chassis together in a state where it was capable of driving, and decided to test it out on some of the obstacles. The very first obstacle, the burlap sack, caused an issue where when you near the top, the weight of the robot causes the burlap to sag, resulting in a near vertical incline to get over. Upon reaching about three quarters of the way up the burlap sack, the Think Tank tumbled over backwards to the bottom and landed upside down. The whole time we were designing the robot, we had just thought "It has treads, it can get over anything" without actually testing that theory. Now, one week before competition, we had a robot that couldn't make it over the very first obstacle. Fearing getting zero points on the obstacle course portion, we did the unthinkable. We scrapped the Think Tank and started fresh with the one thing that worked, the dustpan.