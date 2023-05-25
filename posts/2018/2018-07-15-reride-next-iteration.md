---
tags: post
title: Designing the next iteration of ReRide
date: 2018-07-15
category: Design
cover: https://cdn.mathscapes.xyz/static/images/2018/3.jpg
layout: layouts/default.njk
permalink: /notes/reride-next-iteration
--- 
ReRide, after the [demo at Interact 2017](../2017/post-interact.html) went into its dormancy for some time due to our teaching engagements. But after an [excellent, rigorous session of making](../2017/pre-interact.html) and building the prototype for Interact 2017, we did learn a few things about rethinking the underlying architecture to create a more stable platform.

Technical challenges in the earlier demonstration

> Genuino board fell short at handling simultaneous BLE connections from the sensors and the visualisation app suffered due to untimely handshakes and connection latency.

1.  Genuino board also couldn’t support continuous power supply for more extended periods of time and couldn’t sustain the BLE polling continuously.
2.  The sensors individually however worked well as intended, but we realized the need for designing better placements to get more accurate and relevant data for posture information.

Given this unreliability, we could not test the prototype the way we wanted, and these are the critical technical challenges that we are trying to solve in the new iteration.

The first round of work development post-Interact conference was doing an exploration of existing information and methods available to map body posture through camera setup. We thought the camera would be exciting interface that would eliminate the need to instrument the rider and yet fetch information from the rider. Understanding challenges in image recognition in real-time scenarios on Indian roads and traffic, we still went on to explore what can be made possible for a research-oriented perspective and personally, I’m very keen to explore the possibility of a camera-only system to estimate posture in real-time.

Camera System for posture estimation (Version 1)

1.  One of the earlier demos that we built included a simple camera setup to read face and upper body torso and calculate relative change in their size and location on the frame to estimate front/back lean and left/right tilt. This information is equivalent of what we were able to achieve from the accelerometer setup which was previously worn by the rider. Regression analysis indicated that rider lean could be detected just by tracking face/torso with reasonable confidence.
2.  However, the caveat was reliance on face recognition to get the data-points as mentioned earlier. While this is still an excellent base to explore more in camera-based posture tracking, this is a vast area in itself to examine.

Reimagined architecture for modularity and fast prototyping

1.  During April, we went back to the physiotherapist to get insights into the relevant body parts or aspects that should be read to understand rider’s posture. One of the information highlighted through the conversation is the complexity of extracting posture information itself, and need sophisticated machinery or multiple different scanning of crucial parts/joints which can only be deciphered by the specialist to recommend corrective measures to the patient. However, we are not trying to get exact configuration at which rider’s body part is in, but trying to get an overall sense of the posture through a minimal set of sensing points which can be useful in preventive healthcare.
2.  We went back on the paper and planned how we can now move forward conceptually and design the prototype. Over the next month, Anchit joined us to work on the new iteration. The second week of May went quite fast-paced when Tomas Sokoler visited us to rework on the higher level architecture of the platform and to meet possible collaborators to explore intersections.

<img src="https://cdn.mathscapes.xyz/static/images/2018/1.jpg"/>
<p class="caption">ReRide 2 System Architecture — Bike Area Network</p>

ADAFruit Mess and hiccups with ARM architecture

Switching to Raspberry Pi seems such a good option until you realize that Raspberry Pi does not allow native serial interfacing for analog devices. Well, there are a lot of possibilities to an interface, we found out that ADAfruit has a lot of readily available ADC (Analog to Digital converters) that support I2C communication. While that was supposed to not take much time for interfacing, it took us a little more due to multiple issues in circuit and ADAfruit library for the ADS1115.

<img src="https://cdn.mathscapes.xyz/static/images/2018/2.jpeg"/>

<p class="caption">Mounting FSRs to study weight distribution during different postures</p>

One small but significant bit is to understand that Raspberry Pi is based on ARM architecture and you may not find pre-compiled binaries for a lot of libraries that may be required to develop an IoT prototype. In our case, we are using Python >3.4, and OpenCV >3.2 and that led us to build all the dependencies from source on RPi to ensure maximum compatibility. Building OpenCV from source on RPi ZeroW took us over 4+ hours.

Camera system for posture estimation (Version 2)

In the next version, we took a step back and looked at first accomplishing the ability to detect and extract posture information rather than spending time on image recognition problem itself. The camera system uses an 8 MP NoIR camera with an RPi Zero, capable of detecting specific markers which are placed on the rider’s helmet and body to get the coordinates of head and shoulder to extract proximity and orientation.

<img src="https://cdn.mathscapes.xyz/static/images/2018/4.jpg"/>

<p class="caption">System to extract useful data points for posture estimation from the markers</p>

<img src="https://cdn.mathscapes.xyz/static/images/2018/3.jpeg"/>

<p class="caption">Enclosure for mounting camera system (by Chakra/Vineeta)</p>

Fixing the Tech stack

> How do we decide and fix the technology stack for the prototype, when the prototype is evolving? Working on the same stack will be easier and convenient for teams but less flexible. And the changing stack could be more flexible to achieve the goals, but not easy for the team.

Learning from previous attempt, our codebase is now largely written using consistent framework and have lesser dependencies than previous. Also, we have just two — Anchit and I working on the code and thus, we did not face any issues in this context. Also, the codebase is being documented with detail to scale this into full fledged SDK and more contributors in the future.

Evolving ReRide space

I cannot thank enough to the members of ReRide team to create this space for research. It is evolving into a learning space for me, and now since, we are towards the end of putting together the primary system to test, it will be super exciting to look at data and how we can make sense of the data! While my interest area in ReRide intersects at computer vision, mathematical modelling, and machine learning, I’m equally excited about the overall prospects of this project in the future.