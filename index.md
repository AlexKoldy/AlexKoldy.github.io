# Alexander Koldy's Portfolio

## Hello, welcome to my portfolio!

My name is **Alexander Koldy** and I am a senior mechanical engineering and computer science student at The Cooper Union for the Advancement of Science and Art. I am an **aspiring roboticist** with a strong interest in **mechanical design** and **controls**. Below, you will find some of my most recent robotics-related projects. If you are interested in learning more about my work, please send an email to koldy@cooper.edu (resume available upon request)!


|[Soft Robotics](#dexterous-manipulation-with-soft-robotic-end-effectors)|[Actuated Ball Joint](#actuated-ball-joint)|[Humanoid Control](#humanoid-control)|[Gearbox Design](#u12-gearbox-mechanical-design)|[Autonomous Golf Cart](#intelligent-ground-vehicles-competition)|[ViT Probing](#visual-transformer-probing)|[Aircraft Controls](#aircraft-controls-simulations)|[Self-Balancing Cube](#self-balancing-cube)|[Maze Robot](#maze-solving-robot)|[Robot Tank](#mobile-robot)|

## Dexterous Manipulation with Soft-Robotic End-Effectors

<div align="center">
<img src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/soft poster-1.png"/>
</div>

### Skills used:
- SolidWorks
- 3D Printing
- Arduino
- Python

### Details
For my senior project, I originally wanted to develop a robot that could cook various meals. After analyzing the most important aspects of human cooking, I determined that  hands were most important to the many of the motions we as humans perform during the cooking process. This led me to explore dexterous manipulation in robotic end-effectors as a potential project. However, I realized that traditional (hard) robots, aren't exactly ideal for the kitchen settings: the kitchen has objects and liquids that can potentially damage traditional robotic systems if they aren't properly protected. Moreover, I realized that traditional robots need percise force-feedback in order to adequately move and manipulate easy-to-break objects such as eggs. This led me to explore soft robotics as a potential solution. Thus, my senior project, **Dexterous Manipulation with Soft-Robotic End-Effectors** was born.

So far, I have been involved with the mechanical design of soft robotic fingers. Together with my group, I design fingers and their molds in SolidWorks. I then 3D print the molds on my printer. In the Robotics Laboratory at The Cooper Union, we pour silicone into the molds and let it cure. This allows us to turn around different designs within about a day (with curing the silicone taking anywhere from 4 to 12 hours). Next semester, I will be working on developing more advanced finger designs, likely containing multiple pressure channels for added degrees-of-freedom (DoF). I will additonally be looking to add DoF by using small servos, which do not make any contact with the work environment or objects within it.

In terms of software, an Arduino Mega 2560 will be used to handle pressure control and acquire pressure data. Additionally, a Python script to extract curvature based off of video frames is being developed so that pressure vs curvature graphs can be generated. 


## Actuated Ball Joint
### Skills used:
- Solidworks
- Python

### Details:
Earlier this year, an active ball joint mechanism was published (https://ieeexplore.ieee.org/document/9415699). To my peers at New York University (NYU), I proposed that this mechanism could potentially be used for 3DoF joints in humanoid robots. Thus, our group began to work on improving this mechanism and making it more compact. At the beginning, I spent a lot of time in SolidWorks optimizing the published mechanical design. I helped develop a more space-efficient 2DoF actuation mechanism, which we call the differential module, to control the main ball joint, a cross-spherical gear (CS gear). This new design works with individually actuated larger bevel gears connected by a smaller bevel gear in between. The smaller gear is on the same shaft as the monopole gear (MP gear), the gear which drives the CS gear, and therefore the end-effector. The mechanism works as follows:
- If both larger bevel gears spin at the same speed and in the same direction, the MP Gear will rotate about the same axis as these bevel gears
- If both larger bevel gears spin at the same speed, but in the opposite direction, the MP Gear will rotate about its own axis
- Spinning the larger bevel gears at different speeds will allow for a combination of the two effects described above

I also developed the SolidWorks macro that generates the MP gear based off of geometry of the CS gear (which can easily be generated with a few revolutes and revolve-cuts). The macro itself represents a hobbing process that utilizes the _Move/Copy_ and _Combine_ (Boolean Subtraction) features in SolidWorks.

As the project began to develop, I started to work as more of an advisor. I ensured all design changes were feasible for manufacturing (FDM and SLA printing) and that the mechanism would properly work. I also assisted with both the final design, where I found ideal motor placements to compact the design further, and the prototype design, which is currently being physically constructed by my peers at NYU.

I am also assisting in the development of the the controls system for the physical prototype. Together with a peer, I developed a mathematical python simulation to verify the forward and inverse kinematics of both the original published design and our new design. Over the break, I will be working on admittance control, as the group has decided to focus on mouth-swabbing application of the mechanism before applying it to humanoids.

## Humanoid Control
### Skills used:
- Python
- PyBullet
- C++
- Linux

### Details:
At NYU, I have also developed software used to control humanoid robots. A lot of my work is heavy in linear algebra (NumPy and Eigen), and I make use of the rigid-body dynamics library Pinocchio (in both Python and C++). I have worked on LQR control for stable Zero Moment point (ZMP)-based walking stability, and have done work in [firm] realtime control. Most recently, I assisted in the humanoid throw project, where I also worked on establishing a realtime environment (RT-preempt Linux kernel) our robot's main computer. More information about the project and our paper can be found [here](https://nyu-legged-group.github.io/throw).

In addition, I am working to understand the work of Masahiko Yamaguchi ([DrGuero2001](https://www.youtube.com/channel/UC-ujS0hAM5-RNMRyI4HUZmA) on YouTube), and apply it to our humanoid. Most specifically, I am working with a peer to dissect his upper body vertical control (UVC) software in order to experiment with a similar concept on our robot. So far, I have translated much of his code to Python in order to use PyBullet as a physics engine. I actualled reached out to him and some of my questions can be found on [his website](http://ai2001.ifdef.jp/). I hope to make significant progress after the completion of the Fall 2021 semester.


## U12 Gearbox Mechanical Design

## Intelligent Ground Vehicles Competition

## Visual Transformer Probing

## Aircraft Controls Simulations

## Self-Balancing Cube

## Maze-Solving Robot

## Mobile Robot










