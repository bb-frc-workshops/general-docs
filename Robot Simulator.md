# 2D Robot Simulator for BB FRC Workshops

## Introduction
This document describes a 2D robot simualator that can be used as part of the BB FRC Workshop series. It is currently a work in progress, but will serve as a guiding document for the implementation of said simulator.

## Background and Motivation

### Current state of workshops
We have conducted weekend workshops in the fall as part of our efforts to help train BB sponsored FIRST Robotics Competition teams in how to design, build and program FRC robots. Below is a description of the evolution of this workshop series:

- Early Days
  - Lecture Based
  - Java programming and walkthrough of robot hardware
  - Students wrote code that was deployed to the live robot
- Cardboard Robots
  - More hands on
  - Students design and build robots out of cardboard
  - Program robots using web-based IDE
- Cardboard Robots v2
  - Better hardware (Raspberry Pi 3 + Polou Robot Controller)
  - API is a closer match to what students would use to program a real FRC robot
  - Full tournaments
  
The hands-on approach to the workshops has been a great success, as students gain experience with designing a (albeit simple) robot to play a simple game, and gain experience writing almost-FRC level code. Coupled with the tournament that we run throughout the workshop event, this makes for a tangible learning and fun experience.

The use of cheap hardware (a full kit that we use for the workshops runs something in the $100-150 range) and web-based IDE gives us the opportunity to:
- Have more kits available so that multiple teams can each work on their own robot
- Have kits that can be used anywhere with minimal setup (no need to download an IDE etc)
- Make it easy for students to experiment with proreamming and robot design at their own pace, at a time and place of their choosing

Given that, we are currently working on the next generation of cardboard/low-cost robots, as well as improving the overall software experience. For more on this, see the sections that follow, as well as the `drivethru` and `halsim-drivethru` projects in this organization.

### Motivation for a 2D robot simulator
The `drivethru` and `halsim-drivethru` projects allow us to leverage the tools that students will need to use anyway while programming their competition robots, but repurpose them to control essentially anything on a network that speaks the `drivethru` protocol. Our initial explorations have yielded demos with actual robot hardware (powered by Raspberry pis etc) that can be controlled with code written with WPILib, and driven using the FRC Driver Station. Essentially, we now have a way to replicate the FRC robot experience using commodity hardware.

However, as with hardware in general, it is not the easiest thing to get into, and requires time to set up, configure, troubleshoot, etc. Also, even with the relatively low cost of the basic components, it is still a non-trivial amount of money to get a kit into the hands of every student that we want to support. Additionally, with the COVID-19 pandemic and social distancing, it will be hard to get multiple teams in the same place, building robots to compete with each other in person.

Thus, we propose the idea of a software based robot simulator that works with the `drivethru`/`halsim-drivethru` projects, and will allow students to program an FRC robot and have it be simulated on their computer.

#### Aren't there already solutions like this?
Yes, indeed there are. WPILib includes a simulation GUI which allows users to test inputs/outputs from a robot program. This is a fantastic resource for low fidelity testing and ensuring that the right inputs/outputs are triggered. However, it doesn't give the same feeling as watching a robot moving across the screen.

There are also HALSim modules that interface with Gazebo, a professional grade robot simulator which allows one to load in CAD models of their robot and access physics-accurate simulations. Howver, the learning curve is steep, and gazebo only runs on Linux (plus it's resource intensive). Additionally, it takes a great deal of setup time before being able to get started with this.

Thus, we want to build something that sits between these two extremes, with a physics-ish simulation, but still being easy to use, and more importantly, be quick to set up so that any student, regardless of ability, can start writing FRC robot code and testing. Further sections in this document will elaborate on some of the proposed features of this simulator.
