---
title: "Depth V1"
permalink: /engineering/depthv1
layout: splash
---

<h1 style="text-align: center;">Depth V1 - MakeMIT 2021 2nd Place Project  </h1>
<h2 style="text-align: center;">I Led a Team to Design And Build A Freediving Smart Watch That Won 2nd Place at MakeMIT2021. We did it in 16 days, here is how.  </h2>

1. establish what freediving is
2. establish why a freediving watch matters
3. explain how we tackled the problem
4. show results
5. explain room for improvement, linke to Depth V2



MakeMIT link: devpost.com/software/d3pth 

Why would someone use a freediving smart watch?

The ability to know how deep you are diving and for how long can be critical to make safe diving decisions. D3PTH provides that information and more. In addition, a freediving smart watch can log your dive sessions for review later.

What is freediving?
Free diving is underwater diving that depends on performing an entire dive on a single breath.
Freediving is different from scuba because it does not utilize a scuba breathing apparatus.
Why build D3PTH?
No free diving watch under $500 has a color display, wireless charging, and wireless dive log export. In addition, our team wanted a project that had mechanical, electrical, and software challenges.
D3PTH will be built with a 3D printed plastic body, a glass watch face, and a stretchy watch band to fit over a wetsuit. D3PTH will feature a custom 4 layer PCB. The D3PTH PCB will feature an ESP32, BNO05 IMU, Lipo battery management circuitry, wireless charging circuitry, wifi and bluetooth connectivity, and a haptics system.
Key Features: Full color 240X240 pixel circular screen Buttonless IMU based user interface ESP32 Pico Microcontroller Wireless Charging Underwater compass mode utilizing the Bosch IMU Haptic feedback for in dive depth monitoring Dive logging including dive time, depth, temperature and compass headings Wireless dive log export over bluetooth
How we built it
We used a form 3 SLA 3D printer to make the housing, and used heat set inserts to give us a place to screw down the bezel to seal against water.
We had our 4 layer PCB and SMT stencil fabricated with JLC PCB. After receiving the PCB's we hand placed the components and baked the PCB in a cheap toaster oven.
For the programming we used the Arduino IDE due to the number of plug and play libraries available

Challenges we ran into

Many, many challenges. We had lots of hardware issues with our PCB due to component spacing being so tight. Once the PCB was working we had a pretty stable system.

Accomplishments that we're proud of

We are super proud that it works! We had our doubts that we could design and build a 3D printed waterproof smart watch in 16 days. We programmed our board on a test-bench while it was in transit to maximize our time.

What we learned
How to integrate the ESP32 D4 Pico into a circuit board
How to design a Bluetooth antenna circuit
Limitations of resin printing
Importance of having a backup PCB if the main one fails
What's next for D3PTH
​
We plan on building D3PTH with even more features and a more durable CNC'd metal case. New features we are looking to include:
Flexible PCB's for cable management
A SPo2 sensor
GPS
A second IMU for improved headings