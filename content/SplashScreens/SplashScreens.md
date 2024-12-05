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
    @import url(../utilities.css);
    section::after {
    content: attr(data-marpit-pagination) '/' attr(data-marpit-pagination-total);
    }
footer: ELEE1146 | Mobile Applications for Engineers
auto-scaling: false
size: 16:9
paginate: true
_paginate: false
marp: true
math: true
---

<!-- _footer: "[Download as a PDF](https://github.com/UniOfGreenwich/ELEE1146-Lectures/raw/gh-pages/content/SplashScreens/SplashScreens.pdf)" -->
  
# Splash Screens 

    Module Code: ELEE1146 

    Module Name: Mobile Applications for Engineers

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIEEE MIHEEM FHEA

---

## Bootsplash

<div style="font-size:26px">

- AKA bootscreen
- Graphical representation Boot process of the OS
- is not necessarily designed for marketing purposes; 
- it can be intended to enhance the experience of the user as eye candy
- or provide the user with messages (with the added advantage of color-coding facility) to diagnose the state of the system.

![bg right:50% 100% vertical](https://upload.wikimedia.org/wikipedia/commons/8/88/Ubuntu_9.4_Bootsplash.png)

![bg right:50% 100% vertical](https://upload.wikimedia.org/wikipedia/commons/9/97/Windows_8_booting.png)

</div>

---

## Interstitial Webpage

- Interstitial (interval or intervening space or segment)
- displayed before or after the expected content page

![bg right:50% 100% vertical](https://w0.peakpx.com/wallpaper/761/975/HD-wallpaper-sunlights-through-green-trees-forest-background-nature.jpg)

---

## Loading Screen

<div style="font-size:25px">

-  is a screen shown by a computer program, very often a video game, while the program is loading (moving program data from the disk to RAM) or initialising.
-  Some loading screens display a progress bar or a timer countdown to show how much data has actually loaded. Others, recently, are not even a picture at all, and are a small video or have parts animated in real-time.

</div>

![bg right:50% 100%](../../figures/splashAnimationBars.gif)

---

## Loading Real World: Portal 2

![bg right:60% 70%](https://cdn.mos.cms.futurecdn.net/0fd37af5b0b714d887ed60ac79318bf5-970-80.png.webp)
![bg left:60% 70% ](https://cdn.mos.cms.futurecdn.net/fede8e963be443501170ceec1175d423-970-80.png.webp)
![bg left:60% 70% vertical](https://cdn.mos.cms.futurecdn.net/5880232e41f68a5a3175311c7813e083-970-80.png.webp)

<!-- Portal 2 loads lots of data at the beginning and a lot of smaller files toward the end, as indicated by the spike of read ops and low bandwidth. -->

---

## Android Splash Screen

![bg right:40% 50%](../../figures/android-splash-screen-classical.gif)

```Kotlin
private val SPLASH_DELAY: Long = 4000
Looper.myLooper()?.let { looper ->
    val handler = Handler(looper)
    handler.postDelayed({
      // Create an Intent to launch the MainActivity
      val intent = Intent(this, MainActivity::class.java)
      startActivity(intent)
      finish() // Finish the splash screen activity
    }, SPLASH_DELAY)
} // Number is in milliseconds.
```

---

## `Handler` Class

Two main instances...

1. To schedule messages and runnables to be executed at some point in the future
2. To enqueue an action to be performed on a different thread than your own.

Send and notify state changes of your objects to other applications using an Event-driven Architecture

- you want to create a loosely coupled system
- you want to build a more responsive system
- you want a system that is easier to extend


> ref -> `https://developer.android.com/reference/android/os/Handler.html`

---

## `Handler` Class Diagram

![ h:600 center](https://java-design-patterns.com/assets/eda-ca4599f6.png)

---

## Threads/Runnerable

![](../../figures/Runnerable.png)

----

## Animations - Transitions Functions

<div style="font-size:27px">

- ```overridePendingTransition(enterAnim:Int, exitAnim:Int)``` - API 33 and below

- ```overrideActivityTransition(overrideType:Int, enterAnim:Int, exitAnim:Int)``` - API 34

  - `enterAnim`: A resource ID of the animation resource to use for the incoming activity. Use 0 for no animation.
   
  - `exitAnim`: A resource ID of the animation resource to use for the outgoing activity. Use 0 for no animation.

  - `OVERRIDE_TRANSITION_OPEN/CLOSE`:  starting/entering or finishing/closing

Both functions are used to customise the animation for the activity transition with this activity. This can be called at any time while the activity is still alive.

</div>

---

## Using `overridePendingTransition()`

- Store all animation files in the `/res/anim` directory, you will need to create this yourself.

  ```kotlin
  overridePendingTransition(0,R.anim.slide_in_left)

  // fade_out/fade_in are built-in animations
  overridePendingTransition(android.R.anim.fade_out,android.R.anim.fade_in)
  ```

---

## Animations Types:

- Slide -> Vertical(up, down) and Horizontal(left, right)
- Zoom/Scale
- Rotation -> Including spiraling
- More here:
  -  [https://developer.android.com/guide/topics/resources/animation-resource](https://developer.android.com/guide/topics/resources/animation-resource)

---

## Animation configuration XML (Sliding)

<div class="grid" style="columns: 2; gap: 12px;">
<div style="font-size:24px; margin-top:0px">

- `<translate>` for sliding

- `fromXDelta`  Change in X coordinate to apply at the start of the animation
- `toXDelta`    Change in X coordinate to apply at the end of the animation
- `fromYDelta`  Change in Y coordinate to apply at the start of the animation
- `toYDelta`    Change in Y coordinate to apply at the end of the animation 

</div>

<div style="font-size:28px; margin-bottom:-40px">

```xml
<!--Slide out Left-->
<translate
    android:fromXDelta="100%"
    android:toXDelta="0"
    android:duration="3000" />

<!--Slide in Left-->
<translate
    android:fromXDelta="0"
    android:toXDelta="100%"
    android:duration="3000" />
```

</div>
</div>

<!--
- To go right, inverse the toXDetla, start from 100%p and go to 0
-->

---

## Scaling 

<div class="grid" style="columns: 2; gap: 12px;">
<div style="font-size:26px; margin-top:10px">

- `fromX/YScale` - starting from N size offset, where 1.0 is no change
- `toX/YScale` - ending from N size offset, where 1.0 is no change
- `pivotX/Y` - coordinate to remain fixed when the object is scaled

</div>
<div>

**Scale in**
```xml
<scale
  android:fromXScale="1.0"
  android:fromYScale="1.0"
  android:toXScale="0.0"
  android:toYScale="0.0"
  android:pivotX="50%"
  android:pivotY="50%"
  android:duration="1000" />
```
</div>
</div>

---

## Rotate

<div class="grid" style="columns: 2; gap: 12px;">
<div style="font-size:26px; margin-top:10px">

- `fromDegrees` - Starting angular position, in degrees
- `toDegrees` - Ending angular position, in degrees.

</div>
<div>

```xml
<rotate
  android:fromDegrees="0"
  android:toDegrees="359"
  android:pivotX="50%"
  android:pivotY="50%"
  android:duration="1000" />
```

</div>
</div>

---

## Advanced animation: Interpolators

<div style="font-size:23px">

- An interpolator is an animation modifier defined in XML that affects the rate of change in an animation. 
- This lets your existing animation effects be accelerated, decelerated, repeated, bounced, etc

</div>
<div align=center>

  |Kotlin|| XML|
  |---|---|---|
  |`AccelerateDecelerateInterpolator`||	`@android:anim/accelerate_decelerate_interpolator`|
  |`AccelerateInterpolator` ||	`@android:anim/accelerate_interpolator`|
  |`AnticipateInterpolator`	|| `@android:anim/anticipate_interpolator`|
  |`AnticipateOvershootInterpolator` ||	`@android:anim/anticipate_overshoot_interpolator`|
  |`BounceInterpolator`	|| `@android:anim/bounce_interpolator`|
  |`CycleInterpolator`	|| `@android:anim/cycle_interpolator`|
  |`DecelerateInterpolator`||	`@android:anim/decelerate_interpolator`|
  |`LinearInterpolator`	|| `@android:anim/linear_interpolator`|
  |`OvershootInterpolator` ||	`@android:anim/overshoot_interpolator`|

</div>
