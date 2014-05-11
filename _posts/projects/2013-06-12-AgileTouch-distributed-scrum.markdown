---
layout: project
title:  "Agile Touch: an augmented Scrum backlog"
period: June 2013
categories: projects school
lang: en
---

### The idea

[Thibault Friedrich](http://thibaultfriedrich.fr/cv/) is the one who came up
with the concept of an augmented backlog for agile development. A standard
backlog for Scrum methods is as simple as a blackboard on which developers
stick Post-It notes. Thibault envisioned more:

> Agile Touch save the contents of the Post-Its, their position, their
> progress. This software improves greatly over the traditional backlog, with
> advantages such as: 
> 
> *   real-time backups
> *   distributed use
> *   desktop version
> *   augmented reality

I became part of this project after he decided to implement it and submitted
his idea as an end-of-second-year project. Our four-student team turned his
design into a real thing, and it worked very well, as you can see in the
following video demonstration.

<video controls>
<source src="http://duet.imag.fr:8080/EnsimagVideo/2013_ScrumBacklog.mp4"/>
<source src="/public/2013_ScrumBacklog.ogg"/>
You can simply [download the video presentation](http://duet.imag.fr:8080/EnsimagVideo/2013_ScrumBacklog.mp4).
</video>
{:.fullwidth.resize}


### Peripherals and architectural overview

The touch-enabled blackboard is provided by an old DiamondTouch device lent by
the [User Interface laboratory of Grenoble](http://iihm.imag.fr/en/). Photos of
Post-Its are taken using a Marlin telecamera. These two devices need an Apple
computer to run: one because the drivers we had are mac-only, and the other
because it uses a Firewire cable. Then the main application is hosted on the
Linux PC of one of the team members, which is connected to the video projector.
It also host the database where post-its are stored. Finally a third PC is used
to emulate distant use cases.

We did the real thing: the application is designed in such a way that it could
really be used by several distant teams.
{:.margin.note}

![Architecture diagram](/public/agiletouch_archi.png)

All the code was written in C++, except for the drivers which were already
available in Objective C.
{:.margin.note}

We based all our software architecture on top of the Qt framework. It provides
our graphical interface, our network stack and database access.  We also used
OpenCV to do the image processing part. I worked mostly on the algorithm to
extract Post-Its using OpenCV, and on the network part between the DiamondTouch
device and the main PC. I also spent a lot of time debugging code and working
around some of the problems we encountered.

From left to right: original photo, border detection, square detection,
homography, thresholding and final result.
{:.margin.legend}

![OpenCV recognition steps](/public/agiletouch_post_it_steps.png)

### The Qt framework, the bad Apple and the ugly drivers

We stumbled upon many problems while implementing our project. The most
annoying ones revolved around our need for an Apple computer. At first we were
given an old PowerPC server, which we had to compile our project on. To make it
work, I learned how to use the CMake build system, and wrote a set of
CMakeLists files which could select the right parts of the project to compile
depending on the target architecture. That was a bit tricky, because the
program we wrote for the Mac was linked against both our Qt/C++ architecture
and the Objective C/Apple drivers. But in the end (and after countless hours of
compilation for the whole Qt library), it worked.

![Dead drive Mac icon](/public/dead_drive_mac_icon.jpg) \\
Fear this icon.
{:.margin}

The next day, the hard drive gave its last spin away, and we had to switch to a
newer iMac with a brand new 64bits Intel processor. Unfortunately, the drivers
for the peripherals were not ready for such a big step forward: they were 32bit
only, which required a new round of CMake witchcraft to deal with.

### The end

You may find information about other
aspects of this project on the websites of other team members:

* [Thibault Friedrich](http://thibaultfriedrich.fr/cv/)
* [Youcef Mammar](http://ymammar.com/?q=about)
* Cyril Lorenzetto

