# Smart Car Parking System – Logic Lab Final Project (Fall 1403)

A Verilog-based digital system for intelligent vehicle placement in a simplified smart parking lot, designed as a final project for the Logic Circuits Lab course. The system is implemented on an FPGA development board and simulates real-time parking guidance, entry control, parking status display, and optional features like ultrasonic sensors and parking duration timers.

---

## 📌 Project Description

This project implements an FPGA-based smart parking system capable of:
- Monitoring car entry and exit using sensors.
- Displaying available spots using a 4-digit 7-segment display.
- Automatically opening/closing parking gates based on availability.
- Guiding incoming vehicles to the optimal (lowest-numbered) available parking spot.
- Supporting additional features like ultrasonic sensors and parking timers (optional).

---

## 🚗 System Features

### ✅ Basic Functionalities:
- **Entry Control**: Parking door opens only if a spot is available.
- **Occupancy Detection**: Each of 4 parking spots is monitored (via switch or ultrasonic simulation).
- **Display**: A 7-segment display shows:
  - Number of available spots.
  - Suggested spot number for the next car.
- **Status LEDs**:
  - Red/Green LED to indicate door status.
  - "FULL" LED blinks 3 times if parking is full.

### 💡 Optional Features:
- **Ultrasonic Sensors** (HC-SR04) for real-time vehicle detection.
- **Parking Duration Timer** for each spot, shown on display.
- **Debounced Button Handling** for reliable entry/exit triggers.

---

## 🔧 System Architecture

### 🔢 Modules Overview:
- `main.v`: Top-level module integrating all components.
- `FSM.v`: Finite State Machine controlling the system's behavior.
- `G5_ParsaExirBahramEmami.v`: Core logic for parking management.
- `debouncer.v`: Stabilizes noisy mechanical button inputs.
- `divider.v`: Divides the system clock for timing purposes.
- `doorFreq.v`: Controls the frequency of door operations.
- `fullFreq.v`: Manages the blinking frequency of the "FULL" LED.
- `segmenDivider.v`: Divides signals for 7-segment display multiplexing.
- `sevenSeg.v`: Drives a multiplexed 4-digit 7-segment display.

---

## 🧪 Testbench

For each major module, a testbench is provided and simulation results are generated using Xilinx ISE or ModelSim.

- Use `.txt` files for defining test scenarios (inputs/expected outputs).
- Simulations verify:
  - Entry/exit logic
  - Display correctness
  - Spot selection mechanism
  - Door control behavior
