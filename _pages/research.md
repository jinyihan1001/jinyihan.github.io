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

Method
======
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/method.png" width = "1000" height = ""></center>
<br/>

Model
======
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/model.png" width = "1000" height = ""></center>
<br/>

Experiment
======
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/experiment.png" width = "1000" height = ""></center>
<br/>

Result
======
<center><img src="https://jinyihan1001.github.io/jinyihan.github.io/images/fig.png" width = "1000" height = ""></center>
<br/>

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
