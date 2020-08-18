---
permalink: /projects/
title: "Selected Projects"
author_profile: true
---

I list here some of the interesting recent and past projects I have worked on. Currently I am more interested in and learning about autonomous systems and computer vision. 



# ISAR: An Authoring System for Interactive Tabletops (2018-2019)
ISAR is an augmented Reality (AR) authoring system for interactive tabletops.

Authoring systems for AR try to compensate the complexity and challenge of development of AR applications by providing frameworks that can be reused. These frameworks are available at different levels of abstraction, from software libraries to high-level GUI solutions
targeted towards end-users. 

ISAR targets end-user development of AR applications for an interactive tabletop. By using ISAR, different domain experts, such as teachers or physiotherapist, who do not have any expertise in programming can created their own interactive applications. 

ISAR consists of camera-projector based interactive tabletop and an authoring environment. The application author (e.g. a teacher) uses the authoring environment to creates an interactive application by defining scenes and interactions. A scene is a combination of virtual content and physical objects. The application is then projected on the tabletop and the application user interacts with it. 


<figure>
  <img src="{{site.url}}/images/projects/isar/isar_setup.png" alt="ISAR Authoring Environment and camera-project setup"/>
  <figcaption>ISAR Authoring Environment and camera-project setup.</figcaption>
</figure>

<figure>
  <img src="{{site.url}}/images/projects/isar/scene_projection.png" alt="The designed scene is projected on the tabletop. The annotations are rendered according to position and orientation of the detected physical objects."/>
  <figcaption>The designed scene is projected on the tabletop. The annotations are rendered according to position and orientation of the detected physical objects.</figcaption>
</figure>

The application author creates an interactive application by defining the scenes and
interaction rules. Each scene consists of different annotations, such as text, images, geometric shapes, videos and audio, etc., and physical objects. To design a scene the  application author directly sees a camera feed of the table and can test his application directly from the authoring environment. The annotations can be attached to the scene, or attached to the physical objects. In the latter case their rendering is changed depending on the position and orientation of the physical objects.

Beside the scenes, the application author also defines interaction rules. Interaction rules
define the response of the table upon different interactions of the user, the form of “If EVENT then ACTION”. For example, the application author can define a rule that plays a sound as soon as an object appears on the table. Several templates for interaction rules are available in ISAR, and the set of events and actions can also be extended by a programmer. 

ISAR can be used to create interactive tabletop applications for different domains. In the following three applications are shown: An application for learning vocabulary; An application for guiding through a manual workflow; And two games for cognitive and upper body motor rehabilitation.

<figure>
  <img src="{{site.url}}/images/projects/isar/vocabulary_learning.png" alt="Example of the vocabulary learning application: An application for learning the name of different tools. When the user points at the pincers, a sound is played for positive feedback. Selecting the screw driver, plays a negative feedback sound."/>
  <figcaption>Example of the vocabulary learning application: An application for learning the name of different tools. When the user points at the pincers, a sound is played for positive feedback. Selecting the screw driver, plays a negative feedback sound.</figcaption>
</figure>

An  interactive application was created using ISAR to guide the user through a workflow of assembling a computer mainboard. Scenes were created for each step of the workflow. Each scene consisted of hints and guidance on how to perform the step, such as arrows that show where to place a part. Interaction rules defined the transition between scenes and if a part was missing or the wrong part was picked. 

<figure>
  <img src="{{site.url}}/images/projects/isar/mainboard_assembly.png" alt="A scene of mainboard assembly workflow. The part (CPU) is highlighted and an arrow shows the position of the CPU lock lever. A video also shows how to close the lock."/>
  <figcaption>A scene of mainboard assembly workflow. The part (CPU) is highlighted and an arrow shows the position of the CPU lock lever. A video also shows how to close the lock.</figcaption>
</figure>

ISAR can be used to create interactive applications that support medical rehabilitation. Such an application can be used for example for post stroke rehabilitation. The application consists of two games. In the first game, the user (e.g. a post stroke patient) should hit moving flies on the table. In the second application the user should follow a projected path on the table and gest scores on how well he could follow the path. In both cases interaction rules are defined for calculating feedback that is shown using a feedback annotation. 

<figure>
  <img src="{{site.url}}/images/projects/isar/rehab_games.png" alt="Hit the flies and follow the path game for rehabilitation."/>
  <figcaption>Hit the flies and follow the path game for rehabilitation.</figcaption>
</figure>

The source code of ISAR can be found [here](https://github.com/zardosht/isar) and [here](https://www.youtube.com/watch?v=KyvFT0S5rww) is a short video demonstrating the system. 




# 2D Object Tracking (2018)
As part of [ISAR](#isar-an-authoring-system-for-interactive-tabletops-2018-2019), I wrote code for tracking of the objects put on the tabletop. The tracking code uses Yolo V2 for object detection. Pose estimation is done using feature matching (AKAZE features) and OpenCV's `estimateAffineTransform`. Pose refinement is done through image alignment using Enhanced Correlation Coefficient (ECC).


<iframe width="560" height="315"
  src="https://www.youtube.com/embed/FpB5MsbWenY" 
  frameborder="0" 
  allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

<br/>


[Here](https://github.com/zardosht/tracking2d) is the link to project source code. 



# Lane detection using OpenCV (2020)
Detecting the lane lines under challenging real conditions, including lane cruvatures, change of lighting and lane colors, shadows, and different road conditions.
For each frame in the input video the steps of a pipeline is are applied including image processing, detection of the lanes, and estimation of lane curvature. The result of the pipeline is overlaid back on the original image.

For each frame in the input video the steps of a pipeline is are applied including image processing, detection of the lanes, and estimation of lane curvature. The result of the pipeline is overlaid back on the original image.

<iframe width="560" height="315"
  src="https://www.youtube.com/embed/4jLnZ5f-2uQ" 
  frameborder="0" 
  allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>


**Steps:**
* Camera calibration
* Distortionn correction
* Gradient and color thersholding
* Perspective transform to rectify the image
* Detecting lane pixels and fitting a polynomial
* Detemining lane curvature and vehicle offset
* Warping detected lane boudaries back to the original image
* Visualizing lane boudaries and outputing lane curvature and vehicle offset

<figure>
  <img src="{{site.url}}/images/projects/lane_detection/lane_detection_steps.png" alt="Top row: Undistored Image, Combined RGB and HSV thresholding, Binary thresholding; Bottom row: warped binary image, detecting lane pixels using sliding window, fitting a polynomial to lane pixels."/>
  <figcaption>Top row: Undistored Image, Combined RGB and HSV thresholding, Binary thresholding; Bottom row: warped binary image, detecting lane pixels using sliding window, fitting a polynomial to lane pixels.</figcaption>
</figure>

<br/>

Source code of the project can be found [here](https://github.com/zardosht/Advanced_Lane_Finding_SDCP2).



# Traffic Sign Classification (2020)
description 

video / image 


github




# Behavioral Cloning for Autonomous Driving (2020)
description 

video / image 


github




# Tracking and Localization (2020)
description 

video / image 


github




# Path Planning for Autonomous Driving (2020)
description 

video / image 


github




# ViewGuide (2018)
description 

video / image 



# MindSight (2017)
description 

video / image 



# iPaula (2016)
description 

video / image 




# MagicTouch (2016)
description 

video / image 



# BSB Navigator (2015) 
description 

video / image 



# Hack the Hotel (2015)
description 

video / image 



