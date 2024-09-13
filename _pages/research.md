---
layout: archive
title: "Research Progress"
permalink: /research/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<br/>

1.Machine Tool Intelligent Maintenance System (Shanghai Jiao Tong University)
======

Background
======
Tool wear is a major concern in machining, affecting both production quality and efficiency. As tools wear, they increase friction, cutting forces, and worsen surface finishes, leading to reduced precision and potential tool failure. This can cause costly downtime and damage to the workpiece. Traditional offline inspection methods, which assess wear after machining, are inefficient and fail to provide real-time feedback. Therefore, real-time monitoring is essential for maintaining machining quality. Conventional methods, relying on fixed thresholds, often lack adaptability across different conditions, highlighting the need for advanced, data-driven approaches for online monitoring.

Method
======
To address the challenges of tool wear monitoring, this research proposes an online monitoring method based on a Multi-Channel Parallel Convolutional Neural Network (MC-CNN) combined with an attention mechanism. The MC-CNN is employed to automatically extract feature parameters from time-domain signals, leveraging the network’s ability to capture local features and share weights globally, which enhances the model's generalization capability. Additionally, a channel-based attention mechanism (ECA) is introduced to dynamically adjust the weights within the feature matrix. This approach effectively reduces the impact of redundant information, improves the identification of critical features, and increases computational efficiency.
<br/>
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/method.png" width = "1000" height = ""></center>

Model
======
The proposed model, built using PyTorch, consists of three primary stages: Multi-Channel Parallel Convolutional Neural Networks (MC-CNN), an Efficient Channel Attention (ECA) mechanism, and a final Convolutional Neural Network (CNN) classification block.

First, multi-channel sensor inputs are processed through the MC-CNN, which extracts critical features from the signals using two convolutional layers, each followed by max pooling layers to reduce the dimensionality while preserving important information. The ECA mechanism is then applied to the feature matrix, incorporating an average pooling layer to dynamically adjust the channel weights, enhancing the model's ability to focus on relevant features while minimizing redundant information.

Finally, the refined feature maps pass through additional convolutional layers in the CNN, with max pooling operations for further abstraction. After flattening the data, two fully connected linear layers are used to perform the final classification, categorizing the machining state into one of three categories: Stable, Slight, or Chatter. This architecture improves computational efficiency and increases the accuracy of chatter detection.
<br/>
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/model.png" width = "1000" height = ""></center>

Experiment
======
To validate the performance of the proposed model, an experimental platform was established on a horizontal machining center, and data were collected during the milling process to construct the experimental dataset. A real-time vibration signal acquisition system was set up on the machine tool to capture multi-source input signals throughout the milling operations. A total of 21 accelerometers were installed on the bearing seats, motor seats, and the spindle of the machine's X, Y, and Z axes. These sensors transmitted data to a collection terminal via a high-performance dynamic signal testing and analysis system.

During the experiment, each milling pass was conducted with the same spindle speed and feed rate, but the depth of cut was varied. After each pass, surface roughness measurements were taken, and vibration marks were observed. To ensure accuracy, surface roughness was measured three times per pass to obtain an average value, which was then used to comprehensively assess the level of chatter during the milling process. The milling stability was classified into three levels: Stable, Slight Chatter, and Severe Chatter. The evaluation of the chatter level took into account both surface roughness and vibration patterns. The surface roughness (Ra, in μm) was measured using a Mitutoyo SJ210 surface roughness tester. Based on the distribution of surface roughness at different chatter levels, the following standards were established: 

* When Ra < 1.6 μm and no noticeable vibration marks were present on the workpiece, the milling process was considered stable.
* When 1.6 μm ≤ Ra < 2.0 μm and vibration marks began to appear, the process was classified as experiencing slight chatter.
* When Ra > 2.0 μm and significant vibration marks were present, the process was classified as chatter.
<br/>
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/experiment.png" width = "1000" height = ""></center>

Result
======
In the experiment, a neural network model was constructed using the PyTorch deep learning framework in Python. The input parameters of the model include 21 channels, a single-channel data length of 20,000, and 3 classification categories. During the model training process, the batch size of the training data was set to 32, and the Adam optimizer was used with a learning rate of 0.0001. A weight decay of 0.00001 was applied to prevent overfitting. The model was trained for 1,000 epochs, and the loss function used was cross-entropy.

To validate the effectiveness of the proposed Multi-Channel Parallel Convolutional Neural Network (MC-CNN) and the Efficient Channel Attention (ECA) module, ablation experiments were conducted. These experiments compared the performance of several network configurations: a network with both the ECA and MC-CNN modules, a network without the ECA module, a network without the MC-CNN module, and a network without both the ECA and MC-CNN modules. All networks were evaluated using the same training and testing datasets to ensure fair comparisons.
<br/>
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/fig.png" width = "1000" height = ""></center>
<br/>
Observing the accuracy curves, it was noted that the network employing both the MC-CNN for multi-channel parallel feature extraction and the CNN classification module improved classification accuracy by 0.87% compared to the baseline model using only the CNN classification module. Additionally, the network with MC-CNN reached a stable state within 165 iterations. Furthermore, when the ECA module was introduced alongside the MC-CNN, the recognition accuracy of the model further increased to 99.62%, and the convergence speed significantly improved, requiring only 97 iterations to reach a stable state.

2.Robotic Ultrasound Imaging (The University of Hong Kong)
======

Background
======
Ultrasound imaging has been widely used in medical detection and diagnosis, because of its convenience and safety, compared with CT and MRI. Traditional 2D ultrasound imaging only generate 2D imagines, which is lack of intuitive clarity. 3D ultrasound imaging is time-consuming and need multi-times the storage memory. So we come up with an idea, combining the 2D and 3D ultrasound imaging advantages, reconstruct 3D models from 2D images. To construct the 3D models from 2D ultrasound images, robotic ultrasound is needed to ensure accurate location of the probe and avoid subjectivity and uncertainty.

Build a robotic ultrasound imaging System
======
The robotic ultrasound system is designed with a custom-built slide platform based on synchronized conveyor belts, enabling precise movement of the ultrasound probe. Developed using the STM32 microcontroller, the control algorithm allows the probe to move freely along the X, Y, and Z axes. The system calculates real-time position data based on motor characteristics, ensuring accurate control and feedback. This setup provides a robust and flexible solution for automated probe positioning, essential for applications in medical imaging and robotic-assisted diagnostics.
<br/>
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/system.png" width = "" height = ""></center>

Three automatic scanning experiments
======
The robotic ultrasound system enables the ultrasound probe to automatically and continuously perform B-mode scanning along predefined trajectories. The custom-built probe is equipped with 64 transducers, and real-time B-mode images are captured using a CEPHASONICS acquisition module, generating IQ data. Simultaneously, the microcontroller provides real-time feedback on the probe’s position. Three experiments were conducted, scanning a vascular phantom along different trajectories. By processing the collected IQ data in MATLAB, real-time ultrasound images were obtained, demonstrating the system’s effectiveness in automated scanning and data acquisition.
<br/>
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/scan-exper1.gif" width = "1000" height = "450"></center>
<center>Z-shaped track, extending along the X direction</center>
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/scan-exper2.gif" width = "1000" height = "450"></center>
<center>Z-shaped track, extending along the Y direction</center>
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/scan-exper3.gif" width = "1000" height = "450"></center>
<center>Optimized track, extending along the phantom</center>
