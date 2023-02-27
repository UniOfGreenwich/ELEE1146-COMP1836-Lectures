---
title: Development Kits
description: Development Kits
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

# Development Kits

    Course Code: ELEE1146 and COMP1836

    Course Name: Mobile Applications for Engineers/Technologists

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIHEEM FHEA

---

## What is a Software Development Kit (SDK)?

- is a collection of software development tools in one installable package.

- Can come with:
  - compiler
  - debugger
  - software framework
    - provides generic functionality
    - user code can augment code base
    - **inversion of control**- behavioural design,
    - **extensibility** - overriding, or adding specialised user code
    - **non-modifiable framework code** - user can extend the code, not modify the base
  
---


## SDKs Platform Specificity 

![bg right:50% 100%](https://sp-ao.shortpixel.ai/client/to_auto,q_glossy,ret_img,w_768/https://adimorahblog.com/wp-content/uploads/2022/08/imgonline-com-ua-Resize-B84sKXCLYd-768x448.jpg) 
![bg right:50% 100% vertical](https://www.tutorialsteacher.com/Content/images/core/install-vs2019.PNG)


- Android
- Java
- iOS
- .Net
- UWP ())

<!--
 Universal Windows Plaform
-->

---

## Average SDKs in Mobile Apps

![](https://assets-global.website-files.com/5ee715da7b6fbc3bf68c6bfe/61e005f615a0214b8a8470d9_how-social-sdks-revolutionize-app-development-for-software-teams-1.jpg)

---

## SDK, is safe?
**Mintegratal SDK**

- tap an ad  
- SDK hijacks the click referral process, 
- making it appear to the underlying iOS operating
- system that the user clicked on one of its ads, instead of a competitor's, effectively robbing revenue from other SDKs and advertising networks.

![bg right:50% 100%](https://www.zdnet.com/a/img/resize/441b5d42569a00aad5979f3e5a60477a6c22799a/2020/08/24/b6e74a91-0d9d-465c-95b0-180c0ed07589/mintegral-sdk.png?auto=webp&width=1280)


<!--

can violate users' data privacy, damage app performance, 
or even cause apps to be banned from Google Play or the App Store

-->

--- 

## [Open] Java Development Kit ([Open]JDK)

**JDK***
- Implements Java Language Specifications (JLS)
- Implements Java Virtual Machine Specifications (JVMS)
- Provides Standard Edition (SE) of the Java API.

**Open JDK**

- is the FOSS implementation of JDK

![bg right:50% 100% vertical](https://windows-cdn.softpedia.com/screenshots/Sun-Java-JDK_1.jpg)
![bg right:50% 100% vertical](https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/OpenJDK_logo.svg/300px-OpenJDK_logo.svg.png)


---
## SDK vs APK

- A **SDK** is typically a set of software development tools that allows the creation of applications for a certain software package, software framework, hardware platform, computer system, video game console, operating system, or similar development platform.

- **Android Package** is the package file format used by the Android operating system for distribution and installation of mobile apps and middleware

---

## SDK vs API

<p align="center">
  <img alt="Light" src="https://miro.medium.com/v2/resize:fit:720/0*7p6SKeXy_eDjh4uT" width="48%">
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="Dark" src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*bjQLLYpzN7VK8_6SxOHD0Q.jpeg" width="45%">
</p>

---

## Appilcation Development Tools (ADT)

- Android developers use an ADT that includes:
  - Android Platform-tools
  - Android SDK Tools
  - Eclipse + ADT plug-in


---

## Native Development Kit (NDK)

 - Android has an NDK
 - Uses GCC compiler, as code base is in C/C++
 - To execute code directly through the core OS
 - Normally done via Virtual machine or interpreter

![bg right:50% 80%](https://discoversdkcdn.azureedge.net/runtimecontent/companyfiles/5997/3236/thumbnail.png?v131180657035340794)

---

## Driver Development Kits (DDK)

- Used for developing drivers

![bg right:50% 100%](https://www.usefullcode.net/2006/12/02/ddk01-thumb.gif)
![bg right:50% 80% vertical](https://resources.infosecinstitute.com/wp-content/uploads/040813_1645_WritingaWin7.png)

---

## Making your own SDK

![bg right:30% 100%](https://miro.medium.com/v2/resize:fit:720/0*lh-qVjpSpQtrsGqz)


1. **Initial Creation and ramp-up time**
   -  you will have to build a CI/CD pipeline end-to-end
   -  will take some time to build and get right.

2. **Ongoing maintenance and development**
    - Fixing bugs, improvements, new features

3. **Release management**
   - You have track each change... 5 different lanuages, 10 updates... 50 versions of SDK
<!--
1.
   -  generating or writing the code, 
   -  triggering tests, updating 
   -  the documentation for each language and releasing the SDK.

1.  
  
   - mid-sized startups (~100 employees) may have a team of 3–5 on SDKs
   - Fortune 500 companies, you might find a group of 10–20 engineers
-->