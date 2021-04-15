---
title:  "IMU Dead Reckoning"
layout: single
permalink: /code-projects/IMU-Dead-Reckoning/
collection: code-projects
---

Dead Reckoning is one of the oldest methods to measure distance traveled. If you're moving at 1 meter/second in a direction, in 100 seconds you will have moved 100 meters in that direction. Modern robots don't use dead reckoning often, because it tends to build up errors over time, however when combined with a method of localizing, we can use dead reckoning to get accurate short timescale location. In this project, we attempt to use dead reckoning with an Inertial Measurement Unit (IMU) to measure changes in position, and we compare this to GPS data.

Before we try dead reckoning, we need to understand what an IMU does. Quite simply, an IMU measure changes in acceleration in lateral movement and radial velocity. An IMU also features a compass to measure magnetic forces, which can be useful for orientation using the earths magnetic poles.

{% include figure image_path="/assets/images/code/IMU_characteristics.png" alt="IMU characteristics" caption="IMU Data from sitting still." %}

There's one last thing to be done before dead reckoning, and that is calibrating the IMU. This can be done by setting the IMU on a flat surface with no vibrations present. Record a few minutes of data, and find the average offsets of linear acceleration and angular velocity. Hard iron and soft iron effects on the magnetometer can be calculated by rotating the IMU and finding the offset and eccentricity of the ellipse, then adjusting so the ellipse is centered with an eccentricity of 1.

{% include figure image_path="/assets/images/code/map_no_adjustments.png" alt="Dead Reckoning without adjustments" caption="IMU Dead Reckoning result in blue, GPS ground truth in red." %}

Now that the IMU is calibrated, we can try doing dead reckoning. Using the raw data from the IMU shows a result that resembles the actual path, but the scales are off.

{% include figure image_path="/assets/images/code/map_adjustments.png" alt="Dead Reckoning with adjustments" caption="Adjustments to the Dead Reckoning Algorithm can improve performance." %}

We can use a few methods to make the IMU more accurate, such as detecting when the vehicle is stopped and resetting the current velocity. These make the solution better, but not perfect.

Ultimately, the proper way to use dead reckoning here would be to localize off GPS. The GPS only records its location about once every second, which is extremely slow for most robotics applications, while IMUs can record changes tens or hundreds of times a second. If we use the GPS to find our actual position every second, and the IMU Dead Reckon our position in between every GPS update, we can get an accurate solution that provides a high update frequency.

<button class="btn btn--primary" onclick="window.open('https://gitlab.com/LKinley/EECE5554_RoboticsSensing/-/tree/master/LAB2/serial_reader')"> Code </button>