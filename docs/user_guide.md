# User Guide

## Overview

This system detects whether an object is **approaching**, **receding**, or **stopped** using an **HC-SR04 ultrasonic sensor**.

Distance measurements are compared over time to estimate velocity.  
The system provides visual and audio feedback through:

- LEDs
- Piezo buzzer
- LCD display

---

## How to Use

1. Power the Arduino board.
2. Place an object in front of the ultrasonic sensor.
3. Move the object **toward** or **away from the sensor**.

The system will automatically detect motion direction and provide feedback.

---

## Measurement Limits

| Parameter | Value |
|---|---|
| Maximum measurable distance | ~165 cm |
| Reliable motion detection | ~110 cm |

Beyond ~110 cm the distance readings become less stable, which affects velocity estimation.

---

## LCD Display

Example output:
D: 9.4cm STOP
v: 0.00m/s L0


### Display Fields

| Field | Meaning |
|---|---|
| **D** | Distance from the sensor (cm) |
| **STOP / APRCH / RCEDE** | Motion state |
| **v** | Estimated velocity (m/s) |
| **L** | Motion intensity level (0–3) |

---

## LED Indicators

The LEDs visualize motion direction.

| LED Color | Meaning |
|---|---|
| Blue | Object approaching |
| Red | Object moving away |
| Off | No significant motion |

### Motion Intensity Levels

| Level | Meaning |
|---|---|
| L1 | Slow movement |
| L2 | Medium movement |
| L3 | Fast movement |

More LEDs illuminate as motion speed increases.

---

## Buzzer Feedback

The buzzer produces short **sonar-like clicks**, inspired by echolocation.

| Motion | Sound behaviour |
|---|---|
| Approaching | Higher pitch, faster click rate |
| Receding | Lower pitch |
| Stop / far distance | Silent |

---

## Notes

The system stabilizes measurements using:

- multiple distance samples
- velocity smoothing
- motion stability counters
