---
title: Introduction to Android Studio
description: Introduction to Android Studio
class: gaia
_class:
  - lead
  - invert
style: |
    #img-right{
      float: right;
    }
     img[alt~="center"] {
      display: block;
      margin: 0 auto;
    }
    table {
      border-collapse: collapse;
      font-size: 22px;
    }
    table, th,tr, td {
      border: none!important;
      vertical-align: middle;
    }
size: 16:9
paginate: true
_paginate: false
marp: true
math: true
---

# Introduction to Android Studio

    Course Code: ELEE1146 and COMP1836

    Course Name: Mobile Applications for Engineers/Technologists

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIHEEM FHEA

---

## Meet Android

- Open-source mobile platform
- 11 major platform releases so far
- 2.5 billion monthly active Android devices
- 2+ billion monthly active Google Play users

![bg right:45% 100%](../../figures/android_logo.png)

---

## Meet Android

- **Form Factors**
  - Most popular are Galaxy family, fold, etc
  - OS also powers tablets, netbooks, e-readers, MP4 playert, Smart TVs, Smart white applicances and Vehicles 
- **Emulator**
  - Duplicates how the app looks and feels on a particular device

![bg right:40% 100%](./../../figures/MeetAndroid.png)

---

## Monolithic Kernel
- Arm and X86 Architecture
- Android kernel is based on an upstream [Linux Long Term Supported (LTS) kernel](https://www.kernel.org/).
- HAL
  - Hardware abstraction layer provides abstraction for the hardware to kernel (software) using devices drivers and firmware

![bg right:50% 100%](https://source.android.com/static/docs/core/architecture/images/generic-kernel-image-architecture.png)

---

## Versions

- 14 Platform Versions and 34 API levels 

<div align=center >

|Platform Version|	API Level|	VERSION_CODE|
|--|--|--|	
|Android 14.0	|34	|UPDSIDE DOWN CAKE|	
|Android 13.0	|33	|TIRAMSU|
|Android 12.0	|31 - 32	|SNOW CONE|	
|Android 11.0	|30	|RED VELVET CAKE|	
|Android 10.0	|29	|QUINCE TART|
|Android 9.0	|28	|PIE|	
|Android 8.0	|27	|OREO|	
|Android 7.0	|26	|NOUGAT|	

</div>
<!--
14 is in beta
-->

---

## Programming and Environment

- **Writing Android Apps**
  - `Java` and `Kotlin` are  Object-oriented programming languages patterned after the `C++` language
- **Android Studio**
  - An `integrated development environment (IDE)` for building and integrating application development tools and open-source projects. 
  - Android Studio `IDE` is exclusively dedicated to the purpose of creating Android applications
  - Includes the `Android Software Development Kit (SDK)`
  - `XML` is used to assist in the layout of the Android emulator
---

## Emulator vs Simulator

- **Simulator**
  -  is designed to create an environment that contains all of the software variables and configurations that will exist in an app's actual production environment. 
- **Emulator**
  - attempts to mimic all of the hardware features of a production environment and software features.

- **Android Emulator**
  - Design, develop, prototype, and test Android apps without using a physical device
  - Mimics almost every feature of a real Android handset, except placing phone calls

---

## What about Kotlin

- Kotlin is an open-source programming language that can run on Java Virtual Machine (JVM). The language can run on numerous platforms.

- It is a language that combines Object Oriented Programming (OOPs) and functional programming in an unrestricted, self-sufficient and distinctive platform.
- In 2019, Google announced Kotlin as its preferred programming language for Android application developers


---

## Getting Oriented with Market Deployment

- Platform consists of the Android OS, application development tools, and marketplace Apps are compiled into package files with an `.apk` extension
- Google Play (http://play.google.com) sells and deploys all apps
- Programs must meet minimum standards
- Apps are free or paid (If you want to charge for your app, the standard split is 70/30 between developer and wireless carrier)
- Also sold through Amazon (amazon.com/appstore) and iTunes (both charge a $99 registration fee)


---

## Opening Android Studio to Create a New Project

- We will be using Android Studio Giraffe | 2022.3.1 Canary 8 March 6, 2023
- Download and install the Android Studio from https://developer.android.com/studio/archive. 
- Search for th "Android Studio Giraffe | 2022.3.1 Canary 8 March 6, 2023"
- Make sure you have enough space on the disk, it takes 2.6GB and you would also need extra space to run it.
![bg right:40% w:500](../../figures/download.png)

---

## Opening Android Studio to Create a New Project (cont’d)

<div align=center>

![w:900 center](../../figures/createProject1.png)

</div>

---

## Opening Android Studio to Create a New Project (cont’d)

![w:800 center](../../figures/selectDefaultActivity.png)

---

## Opening Android Studio to Create a New Project (cont’d)

![w:800 center](../../figures/emptyActivity.png)

---

## Opening Android Studio to Create a New Project (cont’d)

![w:1000 center](../../figures/projectView.png)

---

## Building the User Interface

- **Must** be intuitive
- Interface **must** not distract from functionality
- Java / Kotlin code or XML layout files are needed 
  - Can design interface without writing large amounts of code

---

## Taking a Tour of the Android Project View


- **Java folder** – contains Java / Kotlin source code
- **Res folder** – contains images, music, and video
- **Manifests folder** – contains the `Android Manifest.xml`, which contains information about the application that Android needs to run

![bg right:45% 90%](../../figures/resourcesView.png)

---

## Designing the User Interface Layout within the Virtual Device

- **Widget** – a single element on the screen (Button, Text Box, etc.)
- **Layout** – a container that holds as many widgets as needed
- **Properties pane** – contains the properties of the currently active app project or object 
- **Android Virtual Device (AVD)** – Android Studio displays an emulator configuration for design and layout purposes

---

## Designing the User Interface Layout within the Virtual Device (Cont’d.)

Click Device Manager on the menu and Create Virtual Device at the bottom of the screen 

![bg right:50% 90% center](../../figures/avd.png)

---
## Designing the User Interface Layout within the Virtual Device (Cont’d.)

![w:850 center](../../figures/selectingAVD.png)

---
## Designing the User Interface Layout within the Virtual Device (Cont’d.)

![w:850 center](../../figures/selectingAVDImage.png)

---
## Downloading SDK

![w:850 center](../../figures/downloadingSDK.png)

---
## Designing the User Interface Layout within the Virtual Device (Cont’d.)

![w:850 center](../../figures/selectingAVDVerification.png)

---
## Designing the User Interface Layout within the Virtual Device (Cont’d.)

Step 1: Click ‘Device for Preview (D)’ button (the emulator button) directly to the right of the Palette on the `activity_main.xml` tab, and then click Nexus 6 

---
## Designing the User Interface Layout within the Virtual Device (Cont’d.)

![w:950 center](../../figures/nexusSelection.png)

---
## Designing the User Interface Layout within the Virtual Device (Cont’d.)

Step 2: Click on the text in the middle to display the Attributes window 


![w:850 center](../../figures/mainActivityView.png)

---

## Modifying the Text in the TextView Control

![w:850 center](../../figures/stringsXML.png)

---

## Referencing the String

![w:800 center](../../figures/referenceString.png)

---
## Testing the Application in the Emulator

- Step 1:  Tap or click the Run ‘app’ button on the toolbar 
- Step 2: After you have run the app once and have started the emulator, next time around the Run ‘app’ button has changed

![bg right:50% 60%](../../figures/Emulator.png)