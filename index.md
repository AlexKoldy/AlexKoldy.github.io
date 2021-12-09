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
<p float="center" align="center">
  <img width=400 height=400 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/robot.PNG"/>
  <img width=400 height=400 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/Robot2.PNG"/>
</p>

### Skills used:
- Python
- PyBullet
- C++
- Linux

### Details:
At NYU, I have also developed software used to control humanoid robots. A lot of my work is heavy in linear algebra (NumPy and Eigen), and I make use of the rigid-body dynamics library Pinocchio (in both Python and C++). I have worked on LQR control for stable Zero Moment point (ZMP)-based walking stability, and have done work in [firm] realtime control. Most recently, I assisted in the humanoid throw project, where I also worked on establishing a realtime environment (RT-preempt Linux kernel) our robot's main computer. More information about the project and our paper can be found [here](https://nyu-legged-group.github.io/throw).

In addition, I am working to understand the work of Masahiko Yamaguchi ([DrGuero2001](https://www.youtube.com/channel/UC-ujS0hAM5-RNMRyI4HUZmA) on YouTube), and apply it to our humanoid. Most specifically, I am working with a peer to dissect his upper body vertical control (UVC) software in order to experiment with a similar concept on our robot. So far, I have translated much of his code to Python in order to use PyBullet as a physics engine. I actualled reached out to him and some of my questions can be found on [his website](http://ai2001.ifdef.jp/). I hope to make significant progress after the completion of the Fall 2021 semester.


## U12 Gearbox Mechanical Design

<p float="center" align="center">
  <img width=400 height=400 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/u12.PNG"/>
  <img width=400 height=400 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/u12_inside.PNG"/>
</p>

### Skills used:
- SolidWorks

### Details:
In this project, I designed a modified U12 motor with a 6:1 gear reduction. This would allow for the motor to be used in a humanoid leg. The biggest challenge with this project was ensuring that the sun gear and planetary gear carrier were able to spin freely on the same axis, without compromising the support of the shaft. To do this, I placed an internal bearing on the inside of the planetary carrier and extended the main rotor shaft (sun gear shaft). This constrained the axis of rotation and helped support the rotor shaft at its farthest end. Moreover, this allowed the two shafts to spin at different speeds despite being on this same axis of rotation. Another bearing was placed inside a stator-adapter to constrain the other end of the main rotor shaft. The planetary carrier also had an outer, larger bearing that interfaced with the motors external casing (not pictured; designed by a peer), which helps keep the whole system together.


## Intelligent Ground Vehicles Competition
<div align="center">
  <img weight=600 height=600 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/Car.png"/>
</div>

### Skills used:
- SolidWorks
- Arduino

### Details:
At The Cooper Union, I am part of the Intelligent Ground Vehicles Competition Team where I am the Mechanical Engineering Lead and also a Controls Engineer. For this competition, the goal is to modify a golf cart-like vehicle to navigate autonomously. Most of my engineering work focuses on low-level control (brakes, steering, throttle) and mechanical enhancements. Below, I detail some of the components I've worked on.

**Designing a Multi-input, single-output brake system**
<div align="center">
  <img weight=600 height=600 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/Brakes.png"/>
</div>

As my first project, I had to redesign the commerical brake system that came with the car. The car needed to have an adequate pressure feedback system, and also had to be actuated electronically. I opted to use a hydraulic trailer brake actuator (HydraStar) as a means of actuating the brakes electronically; a PWM signal can easily be sent to this actuator in order push fluid through the system. I scrapped all of the brake lines attached to the front disk brakes. Typically, most of the brake force happens in the front of a vehicle, so I wanted to ensure both mechanical (pushing the pedal) and electronic (hydraulic actuator) actuation could be achieved on the front disk brakes. I did this by using a hydraulic shuttle valve, which allows for pressure differentials to control which output is being used. A small ball covers the output of the shuttle valve until a high pressure is felt:
- If the brake pedal is pressed and the hydraulic actuator is not powered, the pressure from the master cylinder will cause the ball to cover the actuator line, so fluid will flow from the master cylinder to the disk brakes
- If the actuator is sent a PWM signal and the brake pedal is unpressed, the pressure from the actuator will cause the ball to cover the master cylinder line, so fluid will flow from the actuator to the disk brakes

Entire system is connected as follows:
- The master cylinder is connected to input 1 of the shuttle valve
- The hydraulic actuator is connected to input 2 of the shuttle valve
- A custom tee fitting is connected to the output of the shuttle valve. This tee fitting was manufactured in the machine shop, as it must interface with connections of 3 different sizes and types of flares
- The second end of the tee fitting is connected to the pressure sensor for feedback control
- The final end of the tee is connected to the front disk brakes via a double banjo connection. Copper crush washers and gasket rings are used to ensure no leaks spring out in the system

**Modifying the Electric Power Assisted Steering**
<div align="center">
  <img weight=600 height=600 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/EPAS.png"/>
</div>

For the purposes of actuating the steering column, the electric power assisted steering module was removed and modified. I designed an absolute encoder mount which fits directly inside the module, as this was the simplest way of obtaining position feedback for steering the car. All measurements had to be estimated and I made use of rapid prototyping to perfect the designs. The main mount was drafted to match the draft angles of the casted metal whcih made up the EPAS body. I also designed a shaft adapter to adapt the main shaft to the inner diameter of the absolute encoder. An O-Drive also replaces the original control board from the car. With the O-Drive, a cascaded PID loop is run, where angular velocity is the inner loop and steering angle is the outer loop.

**Designing an Encoder System**
<div align="center">
  <img weight=600 height=600 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/Encoders.png"/>
</div>

In order to properly mount encoders on the wheels, I had to make use of the geometrically complex lower control arm. Using a caliper, I estimated the distance of multiple points on the lower control arm to a set point. I think used these points to generate curvatures (in multiple dimensions) in SolidWorks. After modelling a large portion of the lower control arm, I designed an encoder mount that clamps around it. The end result is a robust encoder system that does not slip; this system gives more than adequate position feedback with 1024ppr.

## Visual Transformer Probing
<div align="center">
  <img weight=1000 height=1000 src="https://raw.githubusercontent.com/AlexKoldy/AlexKoldy.github.io/main/img/vit probes.png"/>
</div>

### Skills used:
- Python
- Tensorflow

### Details:
In this project, a peer and I wanted to explore what parts of a visual transformer are most useful to classification. The visual transformer made was used to classify CIFAR-10 images and achieved approximately 50% - 60% accuracy. This was because we lacked the training resources to develop a better and deeper network. We also did not augment the data significantly and did not optimize our hyperparamters. Regardless of accuracy, we were able to get insight into how important each layer was to classification. I wrote a linear probing algorithm to take outputs at each layer of the ViT and attempt to classify the image. From our results, we saw that patching and preprocessing significantly affected the accuracy, but the encoders (transformers) themselves did not. We also ran tests using a convolutional layer placed directly before the patching and preprocessing layer. We noticed that while it increased accuracy, there is almost no point to using a convolutional layer beforehand as patching and preproccesing has a similar affect. We posit that patching is the most important part of a ViT; in other words, using patching with other neural networks may prove to be signifcantly beneficial.


## Aircraft Controls Simulations


## Self-Balancing Cube

## Maze-Solving Robot

## Mobile Robot










