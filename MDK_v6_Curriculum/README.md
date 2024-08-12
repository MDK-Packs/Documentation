# MDK v6 Curriculum

This pages contains a list of resources that help you to learn about MDK v6 and understand its basic components. If you go through the material step-by-tep, you should be able to master any embedded software development project with MDK v6. It also contains material about CMSIS v6 as you cannot imagine the one without the other.

**Table of contents**

| Section | What you will learn |
|---------|---------------------|
| [MDK v6 contents](#mdk-v6-contents) | What is MDK v6? |
| [Getting started/installation](#getting-startedinstallation) | How to install the tools in different ways |
| [Licensing Arm tools](#licensing-arm-tools) | How to add a license to your tools |
| [Creating applications](#creating-applications) | How to create your first project |
| [Using Keil Studio Cloud](#using-keil-studio-cloud) | How to use the cloud-native IDE |
| [Debugging](#debugging) | Find errors in your project quickly |
| [Troubleshooting](#troubleshooting) | Manage obstacles that you might encounter |
| [Becoming an expert](#becoming-an-expert) | Deep-dive into sophisticated topics, including could-based development |
| [Tips and tricks](#tips-and-tricks) | Further content that will help you mastering the tools |

## MDK v6 contents

Previously, the term "MDK" was often equally used as the term "µVision". Until MDK v5, µVision was a single installable EXE file for Windows that came with the IDE, build tools, and models. Device and board support was added by installing the approrpriate packs. Thus, MDK and µVision meant essentially the same.

MDK v6 is different: apart from the tools mentioned above (including µVsion), it also contains Keil Studio, a set of VS Code extensions that can be used to achieve the same goals as with the old IDE. The big advantage is the support of other host operating systems, as VS Code is available on *Linux*, *macOS*, and *Windows*. With the exception of AVH FVP models, all tools from Arm are available for these operating systems as well.

Refer to the [comparison table](https://developer.arm.com/Tools%20and%20Software/Keil%20MDK#Editions) to understand the MDK v6 package contents.

## Getting started/installation

All options for installing MDK v6, a set of command line and GUI tools, is explained in the [MDK Getting Started Guide - Installation section](https://developer.arm.com/documentation/109350/latest/Installation).

### Deviations

You might not want to use the official way to install MDK v6 components. There is an alternative way to do so that is described in the [Install tools on the command line using vcpkg](https://learn.arm.com/learning-paths/microcontrollers/vcpkg-tool-installation/) learning path.

## Licensing Arm tools

Some Arm tools require a license to be present. For an easy start, you can use the [MDK-Community](https://www.keil.arm.com/mdk-community/) license. The licensing user's guide helps you to activate your license using different methods:

- [Activate your product using an activation code](https://developer.arm.com/documentation/102516/latest/Activate-and-deactivate-your-product-license/Activate-your-product-using-an-activation-code).
- [Activate your product using a license server](https://developer.arm.com/documentation/102516/latest/Activate-and-deactivate-your-product-license/Activate-your-product-using-a-license-server).

If you want to use an older version of MDK or a legacy tools, [backwards compatibility](https://developer.arm.com/documentation/102516/latest/User-based-licensing-overview/Backwards-compatibility) helps you to generate node-locked licenses for your PC.

## Creating applications

How to start from scratch is described here for the two IDEs:

- [Creating a project with Keil Studio](https://developer.arm.com/documentation/109350/latest/Create-new-applications/Create-a-new-solution-using-the-Keil-Studio-VS-Code-extensions).
- [Creating a project with µVision](https://developer.arm.com/documentation/109350/latest/Create-new-applications/Create-a-new-project-using--Vision).

## Using Keil Studio Cloud

A learning path is available that introduces you to Keil Studio Cloud:

- [Get Started with Keil Studio Cloud](https://learn.arm.com/learning-paths/microcontrollers/keilstudiocloud/)

## Debugging

Debugging is an important task that every embedded developer must master. Here are a couple of pointers how to use the debugging capabilities of MDK (in this case µVision):

- [Start Debugging with µVision](https://learn.arm.com/learning-paths/microcontrollers/uv_debug/)
- [Get started with µVision Code Coverage](https://learn.arm.com/learning-paths/microcontrollers/coverage_mdk/)

## Troubleshooting

If you are moving from MDK or CMSIS v5 to MDK or CMSIS v6, these learning paths help you to manage the complexity:

- [Migrating Projects to CMSIS v6](https://learn.arm.com/learning-paths/microcontrollers/project-migration-cmsis-v6/)
- [Convert uvprojx-based projects to csolution](https://learn.arm.com/learning-paths/microcontrollers/uvprojx-conversion/)
- [Migrating CMSIS-Packs to CMSIS v6](https://learn.arm.com/learning-paths/microcontrollers/pack-migration-cmsis-v6/)

## Becoming an expert

There is many expert knowledge around Keil MDK. The following list contains pointers to these expert topics:

- [Write Arm Assembler functions](https://learn.arm.com/learning-paths/microcontrollers/asm/)
- [Processing Text in Mixed C/Assembly Language](https://learn.arm.com/learning-paths/microcontrollers/mix_c_asm/)
- [Get started with the CMSIS-DSP library](https://learn.arm.com/learning-paths/microcontrollers/cmsis-dsp/)
- [Build an RTX5 RTOS application](https://learn.arm.com/learning-paths/microcontrollers/cmsis_rtx/)

### Developing in the cloud

While [Keil Studio Cloud](#using-keil-studio-cloud) is available as a cloud-native development environment, many users develop locally, but have their repositories hosted in the cloud. The floowing examples show how to develop in the cloud:

- [AVH_CI_Template](https://github.com/Arm-Examples/AVH_CI_Template) - A CI Template for unit test automation.
- [AVH-Virtual-Peripherals](https://github.com/Arm-Examples/AVH-Virtual-Peripherals)	- An example of AVH models and their python extension implementing virtual peripherals.
- [AVH-VSI](https://github.com/Arm-Examples/AVH-VSI)	- A simple Hello World example using VSI interfaces.
- [AVH-Hello](https://github.com/Arm-Examples/AVH-Hello) - A CI project with a test matrix that uses GitHub Actions on a GitHub-hosted runner.

## Tips and tricks

We have collected a broad range of short videos, webinars, and tutorials for MDK v6 and CMSIS v6 here:

- [Keil videos](https://developer.arm.com/Arm_Keil_Video_Tutorials)
- [CMSIS videos](https://developer.arm.com/CMSIS_Videos)
