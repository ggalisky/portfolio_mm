---
title: "Depth V1"
permalink: /engineering/depthv1
layout: splash
---

<h1 style="text-align: center;">D3PTH - Design And Build of A Freediving Smart Watch</h1>
<h2 style="text-align: center;">I Led a Team to Design And Build A Freediving Smart Watch That Won 2nd Place at MakeMIT 2021. We did it in 16 days, here is how:  </h2>
<h10 style="text-align: left;">March 2021  </h10>

[Freediving](https://en.wikipedia.org/wiki/Freediving) - the sport or activity of diving underwater without the use of breathing apparatus, especially in deep water.

## What is D3PTH?
D3PTH is a freediving smart watch/computer that a friend and I built as part of [MakeMIT link](https://www.devpost.com/software/d3pth). We built D3PTH because we though it would be a difficult/fun but doable embedded hardware/software project within the constraints of the MakeMIT hackathon. Those constraints were a 16 day build + demo window and a $500 budget. After being accepted into MakeMIT, we got to work on a plan.

My role on the team was project lead. I worked on the electronics, mechanical engineering, firmware, and physical prototyping (3D printing, soldering etc).

Why do you need a freediving computer? 
- Keep track of surface interval to prevent shallow water blackouts
- Stay informed about your depth, dive speed, dive time, and other metrics
- Log dives for future review + training

### Timeline 

![image](/assets/images/d3pth_timeline.png)

### Design Phase

We identified early on that there were three elements of the design we need to get right to be successful. 
1. Electronics
2. Mechanical Design (pressure vessel)
3. Firmware

#### Electronics

Since our time line was tight, we started working on the electronics first. While we could afford to iterate on the firmware and mechanical design daily, getting a PCB made and shipped takes 5-10 days. Once the electronics were designed and ordered we could then reallocate our time to iterating on the firmware and mechanical design.

Our first step was creating a rough set of requirements. We landed on the following:

- Color screen
- IMU based user interface (no buttons)
- ESP32 MCU (we had experience with this MCU)
- Wireless Charging (no propriety charing dock)
- Haptic feedback for in dive depth monitoring
- Dive logging 
- Wireless dive log export over bluetooth

We then created a basic high level electronics schematic: 

![depth high level EE](/assets/images/d3pth_ee_highlvl.png)

After some googling we found our screen: [GC9A01 Driven 240 x 240 circular display](https://www.makerfabs.com/desfile/files/ER-TFTM1.28-1_Datasheet.pdf)

It took a bit more research, but we were able to come up with a parts list and started working on the schematic. After the schematic was done, we moved on to PCB design and designed the shape of the PCB to fit the diameter of the screen we selected. The dimensions of the mechanical design would also be derived from the screen + PCBA.

![depth high level EE](/assets/images/d3pth_ee_parts_table.png)

![depth high level EE](/assets/images/d3pth_ee_sch.png)

![](/assets/images/d3pth_pcb_render.png)  |  ![](/assets/images/d3pth_oven.png)

### Mechanical Design

Now that our electronics had been designed and we'd placed an order for the parts and the PCB I moved on to the mechanical design. The casing had one main requirement: don't let water in up to 50ft. From there I worked out that SLA 3D printed parts are watertight. Now that I knew I could 3D print the casing I started designing based on the dimensions of the PCB, dimensions of standard o-rings, and standard flat glass disks. This was the result after a few hours in Solidworks:


![](/assets/images/depth_meche_exploded.png)  

![](/assets/images/depth_meche_cross_section.png)

![](/assets/images/depth_3D_print.png)|![](/assets/images/depth_meche_v2.png)

On the left is the V1 casing and on the right is V2. A design iteration was required because the bezel clamping the glass down onto the o-ring was not rigid enough to create a proper seal. As a result of this I increased the thickness of the bezel and added additional mounting points. 

### Firmware

While we waited for our electronics to be manufactured and casing to be 3D printed we started on the firmware. We tried to keep things as basic as possible in order to ensure we would be able to deliver a functional demo. We narrowed down our feature list to:

- Display relevant information (depth, water temperature, surface interval, heading)
- sample pressure at 2hz
- haptic feedback for reaching a preprogrammed target depth

We skipped working on a sleep mode or charging mode as those features weren't necessary for the demo. We implemented our code in C++ with the Arduino frame work through Platform.io. The code runs in a super loop:

![](/assets/images/d3pth_fw.png)


3. explain how we tackled the problem
4. show results
5. explain room for improvement, link to Depth V2



 






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