---
title:  "Image Mosaicing"
layout: single
permalink: /code-projects/Image-Mosaicing/
collection: code-projects
---

{% include figure image_path="/assets/images/code/mosaic.jpg" alt="Mosaiced Image" caption="Images can be combined to form a larger image." %}

Large images can be captured by combining a number of smaller images into a single larger one. We can do this automatically by detecting features in an image, matching these features with a different image that has a high overlap, and combining the two images.

Prior to image mosaicing, it is important to have a properly calibrated camera. Cameras can be calibrated by taking pictures of a checkerboard like image, and aligning the camera intrinsics so the image results in the lines of the checkerboard being straight. C++ and Python can do this with OpenCV and so can MATLAB with the image processing toolbox.

{% include figure image_path="/assets/images/code/all_tf.jpg" alt="Feature Matches" caption="Matched features between images are used to align the images." %}

When capturing a planar surface, image mosaicing can be performed by finding the homography between two images. This includes finding visual features with a feature detector, like Sift or Orb, then matching overlapping features between two images. The homography will give the translation and rotation of images with overlapping features

If capturing a non-planar surface, image mosaicing can be performed by calculating the fundamental matrix between two images. This can be used to reconstruct 3D scenes with images.

<button class="btn btn--primary" onclick="window.open('https://gitlab.com/LKinley/EECE5554_RoboticsSensing/-/tree/master/LAB4/analysis')"> Code </button>