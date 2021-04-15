---
title:  "Dynamic Object in Point Cloud Detection"
layout: single
permalink: /code-projects/Dynamic-Object-Point-Cloud-Detection/
collection: code-projects
---

Many autonomous mobile robot technologies use LiDARs that generate points clouds for to build highly accurate maps of their environment. However, if the point cloud is used to perform SLAM, moving objects will be detected by a LiDAR, and could be added to the list of landmarks. This can cause issues if the robot returns to the location of the moving object, as the landmarks will no longer be detected, and localization could fail. This project seeks to solve that issue by automatically detecting, classifying, and tracking moving objects in a point cloud. Furthermore, this project does not use any machine learning whatsoever.

{% include figure image_path="/assets/images/code/voxel_PCL.png" alt="Voxel PCL" caption="LiDAR Rings converted to 2D Voxel Grid." %}

We start by converting a ring of the point cloud into a 2D voxel grid, which can be represented as an image. Black is anywhere that points are not and white is anywhere that points are. This gives us an outline of everything that is detected by the LiDAR at a specific height.

{% include figure image_path="/assets/images/code/subtraction.png" alt="Voxel Subtraction" caption="Subtraction removes static objects but leaves some noise behind." %}

The next step is subtracting the 2D voxel grid of the previous detected frame and the current detected frame. Any points that were detected previously that are detected in the same location get subtracted and go away. The result is noisy, but we can filter it to get a better result

{% include figure image_path="/assets/images/code/filtering.png" alt="Voxel Filtering" caption="Filtering the image removes noise." %}

We filter the voxel grid by doing this operation on multiple rings of interest in the point cloud and combining the result. Features that are moving in more of the rings of interest become more apparent while features that only move in one or a few of the rings are filtered out.

{% include figure image_path="/assets/images/code/pedestrian_detection_img.png" alt="Detection image" caption="Contours detect appropriately sized objects with high intensity." %}

Next, we attempt to classify detected objects. We find the contours of the image. Large contours of low values are noise from static objects, while small contours of high values are moving objects. Depending on the size and velocity, these objects are classified as pedestrians, cyclists, or cars.

{% include figure image_path="/assets/images/code/pedestrian_detection_pcl.png" alt="Detection PCL" caption="Pedestrians are detected in the point cloud." %}

Finally, using the detected contours, we can add a bounding box around the image using the height of the rings of interest and the top and bottom of the moving object.
This project was the class project for Robot Sensing and Navigation. 

<button class="btn btn--primary" onclick="window.open('https://github.com/lincolnkinley/PointCloud_DynamicObjectFinder')"> Code </button>