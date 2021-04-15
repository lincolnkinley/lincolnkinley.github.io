---
title:  "Dusty 2.0"
layout: single
permalink: /robotics-projects/Dusty2/
collection: robotics-projects
---

{% include figure image_path="/assets/images/robotics/Dusty2.jpg" alt="Dusty 2.0" %}

Due to the overall poor performance from many of the teams competing at the ATMAE National Robotics Competition in 2015, the rules were not changes for the 2016 competition, with the exception of making the starting box 18 inches by 12 inches. This meant we had a whole year to further develop Dusty into a better design, so enter Dusty 2.0.

Dusty worked quite well at the 2015 competition, but there were some improvements to be made. First, the line following sensors on Dusty for the autonomous portion didn't work well, Dusty could get over the burlap sack, but it would take a while and he would tumble down, often ending up inverted, and overall Dusty just looked... rough. With a year to develop Dusty 2.0, we started from the ground up. Like Dusty, we followed a prototyping model with Dusty 2.0, albeit with less rapid developments and more time spent analyzing and documenting changes. We started with a rough prototype to test the burlap sack so we wouldn't end up in a situation like the Think Tank. Once we had a prototype capable of getting over the burlap sack with ease, we began to modify it, and make CAD reflecting what would end up being Dusty 2.0.

Dusty 2.0 used four wheel skid steering with high traction wheels. This wide base and high traction made it easy to get over the burlap sack without tipping over. The dustpan hinged and controlled, allowing us to lift it up off the ground when not collecting blocks. This made going over obstacles easier as the dustpan did not drag on the ground.

Electronics were simplified for Dusty 2.0 since they weren't inherited from the Think Tank. Dusty 2.0 was controlled with an Arduino instead of a Raspberry Pi, and we used an RC controller instead of a WiFi network. While in teleoperational mode, Dusty 2.0 activated relays that would allow the RC receiver to directly control the motor controllers through a PWM signal. During autonomous the Arduino would shut off the relays and take direct control of the motor controllers. This prevented the high cycle time required to read a PWM signal on the Arduino and gave Dusty 2.0 extremely high responsiveness in teleoperational mode.

We improved the line following part by ditching the infrared sensors and designing our own continuity sensor. Three wires were run dragging on the ground where the middle wire was put at +5 volts and the outer two wires were being sensed for +5 volts. Since the line was made with conductive tape, if either of the outer two wires read +5 volts, then the robot was straying off course, and knew which way to turn to correct it.

I worked mostly on mechanical design of Dusty 2.0, focusing on building the mechanism that moves the dustpan up and down. We were having issues with the servo motor burning out due to the high torque load from suspending the entire weight of the dustpan and the blocks. To overcome this, we added a spring tensioner to the dustpan so when its fully loaded it is in the upright position and instead the servo pushes it down. This balanced the overall torque needed to move the dustpan so the servo would not burn out.

Dusty 2.0 performed quite well at the ATMAE National Robotics Competition in 2016, winning first place overall and first place in every single category. At the competition, I was worried we would see some very stiff competition from other universities, since it's usually the same universities that come every year, and last year they all witnessed how well Dusty performed. I was quite surprised when none of the other teams at the competition had taken inspiration from Dusty. Only two robots made it over the burlap sack, including Dusty 2.0, and only two robots were able to collect any blocks, also including Dusty 2.0. Many of the other teams elected to use a complex robotic arm for collecting the blocks, which typically failed to grab any blocks at all.