# OpenPosterPrinter

OpenPosterPrinter is an open-source project for designing and building a DIY large-format poster printing system from the ground up.

The project starts with a simple and testable motion platform capable of drawing large graphics with a pen or marker, then progressively evolves toward a practical inkjet-based poster printer.

The long-term goal is to support large paper sizes such as A2, A1, and eventually A0 while keeping the design understandable, modular, repairable, and accessible to makers, students, and contributors.

## Project Goals

- Build an open-source large-format poster printer.
- Design a reliable X-axis print-head carriage.
- Design controlled Y-axis paper feeding.
- Support stepper-motor-based motion control.
- Create a PC-to-printer image processing pipeline.
- Convert images into printable raster data.
- Add calibration and alignment tools.
- Progress from pen plotting to inkjet printing.
- Support increasingly larger paper formats as the hardware matures.
- Keep the hardware and software modular so individual parts can be improved independently.

## Development Strategy

OpenPosterPrinter will not begin with a complex commercial-style inkjet mechanism.

The project will be developed in stages:

1. Build and validate the mechanical motion system.
2. Use a pen or marker as the first drawing tool.
3. Verify positioning, paper movement, scaling, and calibration.
4. Add the raster/image processing pipeline.
5. Develop an inkjet print-head interface.
6. Integrate color printing and higher-resolution output.
7. Scale the platform toward larger poster sizes.

This approach allows each major subsystem to be tested independently before the full printer is assembled.

## High-Level Architecture

```text
Poster Image / Document
        |
        v
PC Raster Processing
        |
        v
Print Job Generator
        |
        v
Motion + Print Controller
     /             \
    v               v
X-Axis Carriage   Y-Axis Paper Feed
    |
    v
Pen / Print Head
    |
    v
Printed Poster
```

## Main Subsystems

### Mechanical System

Responsible for:

- printer frame
- X-axis carriage
- guide rails or linear motion system
- paper rollers
- Y-axis paper transport
- print-head mounting

### Motion Control

Responsible for:

- stepper motor control
- position tracking
- acceleration and speed control
- homing
- limit switches
- synchronization between carriage movement and paper feed

### Print Controller

A microcontroller-based controller may be used for real-time hardware control.

Possible platforms include:

- ESP32
- Arduino-class boards
- other suitable microcontrollers

The final choice will be made through testing rather than being permanently tied to one controller.

### PC Software

The PC-side software will handle tasks such as:

- loading poster images
- resizing and scaling
- page layout
- raster conversion
- print-job generation
- calibration data
- communication with the printer controller

### Print Tool / Print Head

The project will progress through multiple output mechanisms:

```text
Pen / Marker
     |
     v
Experimental Print Mechanism
     |
     v
Inkjet Print Head
     |
     v
Color Large-Format Printing
```

## Planned Paper Sizes

Development will progress gradually:

- A3 — early validation
- A2 — first large-format target
- A1 — advanced target
- A0 — long-term target

Support for a paper size should only be considered complete after real hardware testing.

## Roadmap

### P0 — Architecture

Define system boundaries, mechanical layout, electronics, controller responsibilities, interfaces, and safety constraints.

### P1 — X-Axis Carriage

Build and test accurate horizontal movement for the pen or print head.

### P2 — Y-Axis Paper Feed

Develop controlled paper movement using rollers and stepper motors.

### P3 — Motion Controller

Implement homing, movement commands, motor synchronization, and basic fault handling.

### P4 — Pen Plotter Prototype

Produce large drawings using a pen or marker to validate the complete motion platform.

### P5 — Inkjet Interface

Research and prototype a safe interface between the controller and a suitable inkjet print head.

### P6 — Raster Pipeline

Convert images into structured printable data and generate print jobs.

### P7 — A3 Printing Validation

Validate positioning, scaling, repeatability, and image output on A3 media.

### P8 — A2 / A1 Large-Format Printing

Scale the mechanics and paper transport system for larger posters.

### P9 — Color and Calibration

Develop color handling, nozzle alignment, print-head calibration, and quality-control tools.

### P10 — Final Prototype

Integrate the mechanical, electrical, firmware, and PC software systems into a complete prototype.

## Project Principles

OpenPosterPrinter follows a few core principles:

- **Build in small stages.** Every subsystem should be testable before full integration.
- **Prefer measurable progress.** Hardware claims should be backed by real tests.
- **Keep modules replaceable.** Motors, controllers, print heads, and software components should not be unnecessarily coupled.
- **Document failures.** Failed experiments are useful engineering data.
- **Design for repairability.** Parts should be understandable and replaceable wherever practical.
- **Do not claim unsupported print capability.** A format or feature is complete only after successful physical validation.

## Current Status

The project is in its initial architecture and planning stage.

```text
Architecture / Planning   [██░░░░░░░░] Early stage
Mechanical Prototype     [░░░░░░░░░░] Not started
Motion Control           [░░░░░░░░░░] Not started
Raster Pipeline          [░░░░░░░░░░] Not started
Inkjet Integration       [░░░░░░░░░░] Not started
Large-Format Validation  [░░░░░░░░░░] Not started
```

## Safety

This project may involve moving mechanical parts, motors, power electronics, tools, and experimental print-head electronics.

Always disconnect power before modifying wiring or mechanical assemblies. Use suitable power supplies, current protection, emergency-stop mechanisms, and safe mechanical limits during hardware testing.

## Contributing

Contributions are welcome in areas such as:

- mechanical design
- electronics
- firmware
- motion control
- raster processing
- print-head research
- calibration
- documentation
- testing

Please keep contributions modular, well documented, and easy to reproduce.

## License

A project license will be selected before the first public hardware and software release.

---

**OpenPosterPrinter** — building an open, modular large-format poster printer one verified subsystem at a time.
