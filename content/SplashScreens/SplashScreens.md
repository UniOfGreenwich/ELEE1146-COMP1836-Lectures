---
title: Splash Screens
description: Splash Screens
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

# Splash Screens 

    Course Code: ELEE1146 and COMP1836

    Course Name: Mobile Applications for Engineers/Technologists

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIEEE MIHEEM FHEA

---

## Bootsplash

- AKA bootscreen
- Graphical representation Boot process of the OS
- is not necessarily designed for marketing purposes; 
- it can be intended to enhance the experience of the user as eye candy
- or provide the user with messages (with an added advantage of color-coding facility) to diagnose the state of the system.

![bg right:50% 100% vertical](https://upload.wikimedia.org/wikipedia/commons/8/88/Ubuntu_9.4_Bootsplash.png)

![bg right:50% 100% vertical](https://upload.wikimedia.org/wikipedia/commons/9/97/Windows_8_booting.png)

---

## Interstital Webpage

- interstital (interval or intervening space or segment)
- displayed before or after expected content page

![bg right:50% 100% vertical](https://w0.peakpx.com/wallpaper/761/975/HD-wallpaper-sunlights-through-green-trees-forest-background-nature.jpg)

---

## Loading Screen

-  is a screen shown by a computer program, very often a video game, while the program is loading (moving program data from the disk to RAM) or initialising.
-  Some loading screens display a progress bar or a timer countdown to show how much data has actually loaded. Others, recently, are not even a picture at all, and are a small video or have parts animated in real time.

![bg right:50% 100%](https://freefrontend.com/assets/img/css-loaders/loading.gif)

---

## Loading Real World: Portal 2

![bg right:60% 70%](https://cdn.mos.cms.futurecdn.net/0fd37af5b0b714d887ed60ac79318bf5-970-80.png.webp)
![bg left:60% 70% ](https://cdn.mos.cms.futurecdn.net/fede8e963be443501170ceec1175d423-970-80.png.webp)
![bg left:60% 70% vertical](https://cdn.mos.cms.futurecdn.net/5880232e41f68a5a3175311c7813e083-970-80.png.webp)

<!-- Portal 2 loads lots of data at the beginning and a lot of smaller files toward the end, as indicated by the spike of read ops and low bandwidth. -->

---

## Android Splash Screen

![bg right:40% 50%](https://journaldev.nyc3.digitaloceanspaces.com/2018/01/android-splash-screen-classical.gif)

```java
new Handler().postDelayed(new Runnable() {
public void run() {
        // This method will be executed once the timer is over
        Intent i = new Intent(SplashActivity.this, MainActivity.class);
        startActivity(i);
        finish();
    }
}, 5000);
```

---

## `Handler` Class

Two main instances...

1. To schedule messages and runnables to be executed as some point in the future
2. To enqueue an action to be performed on a different thread than your own.

Send and notify state changes of your objects to other applications using an Event-driven Architecture

- you want to create a loosely coupled system
- you want to build a more responsive system
- you want a system that is easier to extend


> ref -> `https://developer.android.com/reference/android/os/Handler.html`

---

## `Handler` Class Diagram

![ h:600 center](https://java-design-patterns.com/assets/eda-ca4599f6.png)