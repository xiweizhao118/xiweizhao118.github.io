---
layout: page
title: VLA application in Deformable manipulation
description: Octo, OpenVLA application for plastic bag manipulation in IsaacSim
img: assets/img/bag_vla.png
importance: 2
category: work
giscus_comments: true
---
Work was done in October, 2024.

### Dataset collection
- **Teacher system**: Created a plastic bag manipulation framework with <a href="https://docs.isaacsim.omniverse.nvidia.com/latest/cortex_tutorials/tutorial_cortex_1_overview.html">Isaac Cortex</a> for automated dataset collection. Implemented behavior tree technique for adaptive subtask transitions, adjusting strategies based on object states.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bag_vla_bt.jpg" title="Behavior Tree for Bag Manipulation" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/bag_manipulation.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>
<div class="caption">
    The left image shows the behavior tree for plastic bag manipulation, while the right video demonstrates the manipulation process using Cortex in IsaacSim.
</div>

- **Dataset collection system design**: Developed a comprehensive dataset collection system leveraging the capabilities of Isaac Cortex, enabling efficient data gathering for training and evaluation.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bag_vla_communication.jpg" title="Communication System for Dataset Collection" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bag_vla_two_views.jpg" title="Two camera views for Dataset Collection" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The left image shows the communication system for dataset collection, while the right image illustrates the two camera views used for capturing data.
</div>

### VLA Model Fine-tuning

- Fine-tuned <a href="https://octo-models.github.io/">Octo</a> model for deformable object grasping tasks on IsaacSim.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/bag_vla_inference_offline.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>
<div class="caption">
    The video shows the offline inference process for the bag manipulation task.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bag_vla_offline_mse.jpg" title="Offline MSE Results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The right image presents the offline MSE results of the position target signals (x, y, z of the end effector and gripper control signal) for the finetuned model.
</div>
The target point’s trajectory shows the inference results of end effector’s position. The inference MSE is around 0.02.
The ground truth sequence of the images are input to the fine-tuned model and make the inference.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/v6_online_inference.webm" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>
<div class="caption">
    The video shows the online inference process for the bag manipulation task, where the model predicts the end effector's position in real-time.
</div>

The online inference results are not ideal; the robot may not reach the target object precisely. This may be due to several factors below:
- Training dataset too small: 
    Only 50 episodes are collected.
- The Octo model’s generalization ability is not good enough: 
    Angles of the figures influence the inference result a lot.
- The gripper does not open may also influence the images input.

### Discussion

The project demonstrates the potential of using VLA models for deformable object manipulation tasks. The fine-tuned Octo model shows promising results, but further improvements are needed to enhance its performance in real-time applications. Future work will focus on expanding the dataset, improving the model's generalization capabilities, and refining the grasping strategies to achieve better manipulation results. Meanwhile, more advanced VLA models should also be implemented.
