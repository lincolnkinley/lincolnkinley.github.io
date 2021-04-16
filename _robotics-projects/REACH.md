---
title:  "Robotic Enhanced Amputee Controlled Hand v2"
layout: single
permalink: /robotics-projects/REACH/
collection: robotics-projects
---

{% include figure image_path="/assets/images/robotics/arm.png" alt="REACH v2 Render" %}

Robotic Enhanced Amputee Controlled Hand v2, or REACH, is a robot that was built for a class project in Assistive Robotics. REACH v2 was the continuation of a capstone project done by one of my classmates during his undergrad at Northeastern University. The idea is to create a 3D printable, low cost robotic prosthetic arm with force feedback on the fingers and myoelectric sensor for controlling.

The original REACH project completed a 3D printed hand that was capable of motion. This model lacked proper human dimensions and didn't perform force feedback on objects it was gripping. We chose to upgrade these two properties for the class project.

{% include figure image_path="/assets/images/robotics/hand.png" alt="REACH v2 Hand" %}

The CAD was remade to be much smaller, and more human like. The original design was somewhat blocky and moved unnaturally. While this isn't a major fix, resizing the wrist to get the battery, Raspberry Pi, servos, and sensors was.

{% include figure image_path="/assets/images/robotics/wrist.jpg" alt="REACH v2 Wrist" %}

Sticking to the spirit of low cost design, we wanted to avoid purchasing expensive force measuring sensors. We settled on one of the cheapest forms of force sensing, force sensing resistors (FSR), for our design. Fishing line was used to simulate tendons in fingers, and low power servos in the wrist would control the position of the fingers. This fishing line ran through an angled channel that applied force to the FSR. When a force was applied beyond a maximum threshold, the fingers would release slightly.

REACH v2 was completed working as intended. The dimensions were much more realistic for a human being, and the servos would dynamically adjust to reach to correct gripping force. All of this was done with a bill of materials of just over $400, much lower than other state of the art robotic prosthetic arms.

<iframe width="420" height="315"
    src="https://www.youtube.com/embed/xwAZOqJ3z2k">
</iframe> 