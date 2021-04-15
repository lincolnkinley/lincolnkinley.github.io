---
title:  "Winston"
layout: single
permalink: /robotics-projects/Winston/
collection: robotics-projects
---

{% include figure image_path="/assets/images/robotics/Winston.png" alt="Winston" %}

Coming off our extremely successful 2016 academic year, getting first place at the 2016 ATMAE National Robotics Competition and first and second place at the Midwestern Robotics Design Competition, we at SIU Robotics knew it was time to step our game up. Now we had a reputation to uphold. Our 2017 academic year started with the 2017 ATMAE National Robotics Competition. 

This year the rules changed to a larger obstacle course with five hacky sacks scattered in various locations. One hacky sack was in the open, one was inside a box the driver was not allowed to see into, one was on top of a weight, one was underneath a weight, and one was (where?). These hacky sacks would need to be collected and deposited into two cornhole boards, and autonomously into three PVC pipe end caps.

Shortly after the rules for the competition were released, we started looking for inspiration. The robot would need to be able to grab and manipulate items precisely, as well as able to lift up a weight. Shortly before receiving these rules, the Carbondale police force bomb disposal squad had just asked us for help repairing one of their old robots. We took it apart to find the only significant issue was its battery needed to be replaced, so we placed an order for a new one and the bomb disposal robot sat around until we got it in. While we were looking for inspiration, we saw the capabilities of the bomb disposal robot and what the robot would need to be able to do at the competition, and the two lined up. We settled on a robot with an extendable arm with a claw at the end of it

Once we decided on the idea, we got to work on the design. Rough ideas were laid out in CAD, which allowed us to 3D print components for testing. Like previous robots to compete at ATMAE Competitions, we created a prototype as early as possible which we could tinker with, however unlike past robots, we worked on the CAD extensively prior to manufacturing.

{% include figure image_path="/assets/images/robotics/WinstonCAD.png" alt="Winston CAD" %}

One important aspect of Winston, is the way we handled software development. Previously, hardware was developed first with the software to follow. This would occasionally result in difficulties meeting expectations with software, due to the way the hardware was designed. With Winston, software and hardware was designed simultaneously. This provided a smooth integration of software and hardware components, meaning Winston was more complex, but easier to control than previous robots.

Winston featured a welded aluminum frame joined together in three parts. The left side, the right side, and the center. The center held the arm and battery. The left side held the Arduino Mega, power electronics, driving motor controllers, and sensors. The right side held the motor controllers for the arm and power distribution.

Like past robots, Winston was controlled using an RC controller and receiver, which outputs PWM signal to the Arduino. The Arduino would read six channels from the RC receiver, which could take as much as 12 milliseconds to process. This resulted in a noticeable delay in responsiveness when driving Winston, but it was by no means uncontrollable.

I was the software development team leader for Winston. We used the Arduino IDE to develop a C++ program for controlling Winston. We used two infrared sensors and an ultrasonic sensor for autonomous line following. The line was reflective on the edges with black in the middle, so the infrared sensors could detect when they were over the shiny edge, or the dark center, which would indicate if the robot was veering off course. The ultrasonic sensor would measure distance to the target, and would automatically open the claw to drop a hacky sack when we were close to the PVC pipe end cap.

Winston was very successful at the 2017 ATMAE National Robotics Competition. In the obstacle course, Winston was the only robot that achieved a perfect score, and his elegant design went on to capture the hearts of many judges. While we weren't able to repeat the winner of every category like we did with Dusty 2.0 the year before, competition was more stiff at the 2017 competition.
