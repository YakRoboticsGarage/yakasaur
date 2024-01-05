# yakasaur

Roving the Earth on Two Wheels

Part of the [Yak Rover](https://github.com/The-Yak-Collective/yakrover) project.

## Project Phases

### 1. Brainstorming / Mission Selection

Platform: 2-wheel + Tail, Solar, Eyes (camera), Ears (mic) and Cell-enabled communication.

Mission:

* Launch in desert (tbd).
* Observe wildlife and insects.
* Movement  by tele-operation.
* Survive for 4 weeks.

### 2. Breadboard

Take some of the parts we've selected and wire together to provide a platform for software work.

Selected Components:

* [ESP32-S3 WROOM CAM board](https://www.amazon.com/gp/product/B0BMQ8F7FN/ref=sw_img_1?smid=AV3WCPW70PEXC&psc=1)
* [Blues Note LTE-M](https://shop.blues.io/products/note-nbna-500)
* [Zephyr RTOS](https://docs.zephyrproject.org/latest/introduction/index.html)

Capabilities:

* Receive commands over cell and wifi (configurable, for development)
* Broadcast telemetry (GPS, battery level, system information) to server (ground station) on a schedule (something on the order of hours)
* Low power mode selection and schedule
* Capture and upload photo

### 3. Prototype

Construct rover that can move but without final PCB and ruggedness.

### 4. Production

Construct final rover.

### 5. Launch

Deploy final rover in desert. Operate for at least 4 weeks.

## Schedule

There is no deadline, but this chart provides general overview of where we think we are.

```mermaid
gantt
    dateFormat YYYY-MM-DD
    title Yakasaur Project

    section Brainstorming
    Project Selection :done, select, 2023-04-25, 2023-05-09
    Block Diagram :done, block, 2023-05-09, 2023-06-06

    section Breadboard
    Part Selection :active parts, after block, 10w
    Prototyping : proto, after parts, 2w
    Development Environment :active, 2023-06-13, 2w
    Demo : milestone, breadboard_demo, 2024-03-01, 1w

    section Prototype
    PCB Design :active, pcb, after parts, 6w
    Print PCB : print_pcb, after pcb, 2w
    Mechanical Design :active, mech, after block, 6w
    Plan : plan, after proto, 1w
    Integration : build, after print_pcb, 4w
    Demo : milestone, prototype_demo, 2024-06-01, 1w

    section Production
    Build : prod_build, after prototype_demo, 4w

    section Launch
    Deploy : deploy, after prod_build, 1w
    Mission : mission, after deploy, 4w




```

## Component Projects

### Mission Planning

### Mechanical Design

### Power

Current Phase 1 experiment is based on:

- [Adafruit Solar Charger](https://learn.adafruit.com/usb-dc-and-solar-lipoly-charger/overview)
  - non-MPPT for more optimal charging
- 3.7V LiPo Battery
- [Buck / Boost](https://www.amazon.com/DEVMO-Adjustable-Step-UP-Converter-Replaces/dp/B07S39M4J5/ref=sr_1_2_sspa?crid=1HDACRKK284EU&keywords=XL6009+Module&qid=1696967719&s=electronics&sprefix=xl6009+module+%2Celectronics%2C122&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1)
  - Pair allows to adjust voltage for compute and motor controller
- Solar Panel
  - AdaFruit only seems to have the big / expensive ones in stock. 

### Electronics

### Vision / Camera

### Audio

### Flight Software

### Ground Control Software
