---
title: Sensors
description: Sensors
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

# Sensors

    Course Code: ELEE1146 and COMP1836

    Course Name: Mobile Applications for Engineers/Technologists

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIEEE MIHEEM FHEA

---

## Sensors 101

- A sensor is any device that measures an event or change in an environment and transforms it into an electronic signal that can be read and computed.

- Measuring some phenomena 

- Passive (Which require and external signal)
- Active (Which require an external signal)

- Analogue (produce an anlaogue output; ie a continous signal)
- Digital (which work with discrete, digital data)

----

## Arduino `SensorManager`

- The is an abstract class that extends the `Object` class.

- Lets you access the device's **sensors**/

- `Sensor` are their own class that also extends `Object`

- `Sensor.getSensorList` gets you all the available sensors.

- `SensorEventListener` used for receiving notifications from the SensorManager when there is new sensor data. 

---

## `Source Code`

The source code is written in `C` and sits on the Linux Kernel that has been modified for the Android OS.

- [https://android.googlesource.com/platform/hardware/libhardware/+/master/include/hardware/sensors.h](https://android.googlesource.com/platform/hardware/libhardware/+/master/include/hardware/sensors.h)

```c 
...
#define SENSOR_STRING_TYPE_ACCELEROMETER                "android.sensor.accelerometer"
#define SENSOR_STRING_TYPE_MAGNETIC_FIELD               "android.sensor.magnetic_field"
#define SENSOR_STRING_TYPE_ORIENTATION                  "android.sensor.orientation"
#define SENSOR_STRING_TYPE_GYROSCOPE                    "android.sensor.gyroscope"
#define SENSOR_STRING_TYPE_LIGHT                        "android.sensor.light"
#define SENSOR_STRING_TYPE_PRESSURE                     "android.sensor.pressure"
#define SENSOR_STRING_TYPE_TEMPERATURE                  "android.sensor.temperature"
...
```


--- 

## Motion Sensors

The sensors' possible architectures vary by sensor type:

- **Software/Hardware**  
  - Gravity, 
  - linear acceleration,
  - rotation vector,
  - significant motion,
  - step counter,
  - step detector sensors

- **Hardware** **Only**
  - accelerometer 
  - gyroscope

---

## Motion Examples

`TYPE_STEP_COUNTER` is derived from `TYPE_ACCELEROMETER` via software

| Sensor	|Sensor event data|	Description	Units of measure|Type|
|----|----|----|---|
|`TYPE_ACCELEROMETER`	|`SensorEvent.values[0]`|	Acceleration force along the x axis (including gravity).	$m/s2$|Hardware|
||`SensorEvent.values[1]`|	Acceleration force along the y axis (including gravity).||
||`SensorEvent.values[2]`|	Acceleration force along the z axis (including gravity).||
|`TYPE_STEP_COUNTER`	|`SensorEvent.values[0]`|	Number of steps taken by the user since the last reboot while the sensor was activated.Steps|Sofware|

---

## Position sensors

- Two sensors that let you determine the position of a device:
  - Geomagnetic field sensor 
    -  geomagnetic field strength values for each of the three coordinate axes during a single sensor event
  - Accelerometer (we have seen this before)
    - measures the acceleration applied to the device during a sensor event

![bg right:30% 95%](https://developer.android.com/static/images/axis_device.png) 


---

## Position Examples
|Sensor|	Sensor event data|	Description|Units|
|---|---|---|--|
|`TYPE_GEOMAGNETIC_ROTATION_VECTOR`|	`SensorEvent.values[0]`|	Rotation vector x axis ($x * sin(\frac{θ}{2})$).|	Unitless|
||`SensorEvent.values[1]`|	Rotation vector y axis ($y * sin(\frac{θ}{2})$)||
||`SensorEvent.values[2]`|	Rotation vector z axis ($z * sin(\frac{θ}{2})$)||
|`TYPE_MAGNETIC_FIELD`|	`SensorEvent.values[0]`|Geomagnetic field strength along the x axis.|	$μT$|
||`SensorEvent.values[1]`|Geomagnetic field strength along the y axis||.
||`SensorEvent.values[2]`|Geomagnetic field strength along the z axis||.

---

## Environment Sensors

- Four sensors that let you monitor various environmental properties:
   - Tempeature
   - Humidity
   - Pressure
   - light
- All hardware based sensors and are available only if a device manufacturer has built them into a device. 
  - Exception is the light sensor which used to control screen brightness

----

## Environment Examples

|Sensor	|Sensor event data|	Units of measure|	Data description|
|--|--|--|--|
|`TYPE_AMBIENT_TEMPERATURE`|`event.values[0]`|	°C|	Ambient air temperature.|
|`TYPE_LIGHT`|`event.values[0]`|	lx|	Illuminance|.
|`TYPE_PRESSURE`|`event.values[0]`|	hPa or mbar|	Ambient air pressure.|
|`TYPE_RELATIVE_HUMIDITY`|`event.values[0]`|	%|	Ambient relative humidity.|
|`TYPE_TEMPERATURE`|`event.values[0]`|°C	|Device temperature|

---

## 