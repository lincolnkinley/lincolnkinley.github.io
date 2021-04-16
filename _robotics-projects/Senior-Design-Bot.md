---
title:  "Senior Design Bot"
layout: single
permalink: /robotics-projects/Senior-Design-Bot/
collection: robotics-projects
---

{% include figure image_path="/assets/images/robotics/sr_design_robot.jpg" alt="Senior Design Bot" %}

In 2016, SIU Robotics began searching for other robotics competitions to go to. Up until then, the ATMAE National Robotics Competition was the only competition we attended, and was the focus of the whole organization. We started branching out, and attended the 2016 Midwestern Robotics Design Competition (MRCD). As we weren't ready to commit large funds to new competitions, our first robot to compete at MRDC cost about $200, was made almost entirely of wood, and won third place overall (the budget bot became a tradition and competes every year at MRDC with less than $200). The following year, ready to commit to the competition, SIU Robotics sent three teams, and I was selected to lead the senior design team. 

MRDC is a large scale obstacle course and task based competition where multiple robots compete in an arena at the same time. The rules and arena typically change every two years, and 2017 featured a new set of rules and a new arena. The goal was to collect small soccer balls and deposit them into your bin to score points. From the start, robots would have to navigate through a tunnel that drivers couldn't see into, pick up a "key", optionally pick up a neutral ball, inset their key into their slot which would release colored soccer balls that could then be collected and scored. Neutral balls could be scored by anyone but released soccer balls could only be collected by their team.

{% include figure image_path="/assets/images/robotics/sr_grabbing_key.jpg" alt="Grabbing the Key" %}

Since rapid prototyping worked so well for us in the past, our team chose to follow the same design, but we quickly decided that picking up soccer balls that are capable of rolling around requires high mobility. To start, we build a low chassis with inset Mechanum wheels, with a sheet of aluminum that parts could easily be mounted to.

{% include figure image_path="/assets/images/robotics/sr_pneumatics.jpg" alt="Pneumatics System" %}


The Key was an 3 inch by 0.5 inch aluminum plate suspended about 4 feet in the air. This was an issue since robots had to begin and finish in a volume of 3' by 3' by 3', so the robot would need to extend up to grab the key. We put a tipable basket on top of a linear actuator on top of a chain driven vertical slide. With the linear actuator and the slide extended, we could reach up into the air high enough to get the key off its hook, and then tip it out of the basket onto the ground. From there, we would use a vacuum and suction cup attached to the linear slide to pick up the key and drop it onto second basket that was aligned with the key slot. With the key aligned, we only needed to drive up to the key slot to insert it.

We tried to keep the mechanism for picking up soccer balls as simple as possible. We used a chain driven linear slide with a basket with bungee cords. By driving the basked down, we could force the soccer balls through the bungee cords. After we lift the slide up, a hinge on the basket would tilt and deposit the soccer ball onto a track for storage while we retrieved the rest of the balls. We had just enough track to hold all the balls at once. Once all the balls were retrieved, we could deposit them one by one into the bin, preventing any jamming from trying to deposit them all at once.

{% include figure image_path="/assets/images/robotics/sr_scoring.jpg" alt="Scoring soccer balls" %}

We used two Arduinos for controlling the robots. One of the Arduinos controlled exclusively the driving, and the other controlled the onboard actuators. Two Arduinos were used because we used an RC controller and receiver to communicate with the robot. The receiver outputs a PWM signal, which can take an Arduino up two milliseconds to read. This may not sound like much, but when you have eight signals, this delay can add up. To keep the driving responsive, the driving Arduino only reads three channels and the actuator Arduino reads the other five.


As the design team leader, it was my responsibility to lead the project. Holding meetings, setting deadlines, helping teammates. Keeping members inspired to continue working on the robot, even after many late nights, was perhaps the most challenging part of this project. Aside from leading the team, I also was responsible for all the software on the Robot. The Arduino IDE made writing the code very simple, and the robot was fully teleoperational, meaning the Arduinos adjusted the inputs from the controller to the input for the motor controller. The most complex part was the channel mixing for getting the Mechanum wheels to drive properly. The right stick of the controller would change X and Y location of the robot without rotating and the left stick would control rotations.

{% include figure image_path="/assets/images/robotics/sr_trophy.jpg" alt="First place trophy" %}

The Senior Design Bot performed better than our expectations. In the past at ATMAE Competitions, we would build the obstacles so we have a clear idea of how the robot is going to perform prior to the competition, but the MRDC arena is 40' by 40'. Ultimately, we won first place after achieving a near perfect score in the final after we captured all our soccer balls and one of the two neutral balls. Surprisingly, the second place team was none other than the SIU Robotics Budget team, who also achieved a near perfect score by collecting all their soccer balls and the other neutral ball, however since we deposited the balls first, we won the tiebreaker.