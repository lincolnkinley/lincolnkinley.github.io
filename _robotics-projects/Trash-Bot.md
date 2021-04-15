---
title:  "Trash Bot"
layout: single
permalink: /robotics-projects/Trash-Bot/
collection: robotics-projects
---

{% include figure image_path="/assets/images/robotics/Trash_Bot.png" alt="Trash Bot" %}

Trash Bot was the first robot I built after starting my Masters degree at Northeastern University. Me and a team of three other students built Trash Bot as a project for a class, Mobile Robotics.

Trash Bot is built on the Husarion ROS Bot platform and utilizes a camera and a LiDAR as its primary means of sensing its environment. Originally conceived as a robot that launches cheese puffs into people's mouths, which was obviously too ambitious and brought up ethical questions about robots launching things at people's faces, we changed to a robot that launches garbage into garbage bins. This was still too ambitious, so the premise for a robot that pushes trash to a garbage bin was born.

Since the project was a mobile robotics project, and not a computer vision or machine learning project, we decided to simplify the visual processing by placing aruco tags on the trash (also dubbed the payload) and the garbage bin (also dubbed the delivery zone). These aruco tags made it easy for the robot to detect and recognize the payload and delivery zone, without the need for a fancy recognition algorithm.

Trash Bot uses a finite state machine to deliver the payload. First Trash Bot attempts to create a map using gmapping, a SLAM algorithm, and the LiDAR sensor. Once this map is created, frontiers on the map in which Trash Bot can explore are found. Trash Bot will attempt to drive to these frontiers, which causes the map to expand again, which may include more frontiers, and so on. While Trash bot is exploring, it's running an aruco tag detection and recognition algorithm, which will detect and add the payload and delivery zone as features on the map. Once no more frontiers that are large enough for Trash Bot to explore are found, Trash Bot will drive to the payload, and attempt to push it to the delivery zone, completing the Finite State Machine.

While Trash Bot's premise was delivering trash to garbage bins, a similar system can be applied to many robotic logistics applications. The focus here is that the robot is unaware of the location of the payload, or where it is supposed to deliver it. This principal could be used to develop a highly distributed robotic logistics system that doesn't rely on a single point of communication to function.