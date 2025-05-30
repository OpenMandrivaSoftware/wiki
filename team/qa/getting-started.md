---
title: QA/Getting Started
description: 
published: true
date: 2025-02-11T09:38:33.447Z
tags: qa, documentation
editor: markdown
dateCreated: 2020-03-02T15:35:06.431Z
---

# Getting Started with QA
We are glad that you are interested in QA.
We have compiled this document to help you get started in helping us test OpenMandriva Lx.

You will need to use the command line to test more often than not. Make sure you have an account at [ABF](https://abf.openmandriva.org/) and [Github](https://github.com/OpenMandrivaAssociation).

QA Team daily communication takes place on Matrix Chat `#openmandriva-cooker:matrix.org` but remember that this is also where developers work so mind your IRC netiquette manners. 
Currently OpenMandriva contributor group is small enough that developers and QA work together on Matrix rooms. There is also a dedicated [QA Forum](https://forum.openmandriva.org/c/en/qa).

QA Team members are encouraged to actively attend weekly (if at all possible) TC meetings.
</br>

### Setting up your OpenMandriva Lx system
Because you will probably be working with untested (with our OS at least) software, we strongly urge you to use a dedicated or virtual machine for testing. For QA work on hardware (recommended if at all possible) it is recommended to have Rolling installed on a separate partition so you have a 'stable' system on another partition in case something breaks during testing.

Pre-release software comes through the testing repositories. Packages in Main repository take precedence over those in other repositories. Packages in Unsupported and Non-Free repositories are responsibility of the package maintainer not OpenMandriva developers.

QA-Team members need a thorough understanding of [Release Plan and Repositories](/policies/release-plan-and-repositories) and [Repository Policies](/policies/repository-policies). There will be more as we better document Openmandriva Lx but we like to keep documentation as simple and light as is feasible.

Workflow for packages is: Cooker > Rolling > Stable repo. Developers/package maintainers are responsible for initiating packages in Cooker and for moving them to Rolling/testing repos. Then QA takes over. Thus all QA Team members are encouraged to maintain a Rolling system where they can do package testing.

You can add the testing repositories with the OpenMandriva [Software Repository Selector](/policies/repositories-tldr) GUI, or from command line

For Main repo only:

Rock system:
`sudo dnf config-manager --enable rock-testing-$ARCH`

Rolling system:
`sudo dnf config-manager --enable rolling-testing-$ARCH`

Replace `$ARCH` with your architecture.

For all testing repos:

Rock system:
`sudo dnf config-manager --enable rock-testing-$ARCH rock-testing-$ARCH-unsupported rock-testing-$ARCH-restricted rock-testing-$ARCH-non-free`

Rolling system:
`sudo dnf config-manager --enable rolling-testing-$ARCH rolling-testing-$ARCH-unsupported rolling-testing-$ARCH-restricted rolling-testing-$ARCH-non-free`

To disable simply replace `--enable` with `--disable`.
</br>

### Package Testing with Kahinah
Now that your system is set up, it's time to vote for the packages. Do they work? Are there really bad issues?

We use a system called [Kahinah](https://kahinah.tsn.sh/), which uses voting to determine which packages to push to the stable repository or not.
Login to Kahinah. Use your Github login.
You can see what packages are waiting to be tested in 'Recent Builds'. Give it a thumbs up or thumbs down, and let us know why.

The current procedure is that packages require 3 'Accept' votes to move forward, unless there are any 'Reject' votes. If there is even one 'Reject' vote it should be questioned and discussed before moving packages. Also packages that get stuck in Kahinah with no votes for over 7 days can be moved due to QA inaction. Discussion about this takes place on Libera.Chat IRC channel #openmandriva-cooker.
</br>

### Testing new Alpha/Beta/RC ISOs
This is discussed [here](/team/qa/release-qa).
</br>

### Triaging New Bugs in Issue Tracker
https://github.com/OpenMandrivaAssociation/distribution/issues
This process is in development at this time. (We need to implement something for triaging bug reports.) 