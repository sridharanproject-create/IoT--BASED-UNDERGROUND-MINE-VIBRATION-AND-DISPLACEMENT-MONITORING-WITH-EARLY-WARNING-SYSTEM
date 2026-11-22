# ⛏️ IoT-Based Underground Mine Vibration and Displacement Monitoring with Early Warning System

## 📌 Project Overview

This project is an IoT-based underground mine safety monitoring system designed to detect vibrations and displacement changes that may indicate unsafe underground conditions.

The system uses an **ESP32 microcontroller**, an **SW-420 vibration sensor**, and a **GY-53 VL53L0X distance sensor** to continuously monitor vibration and changes in distance from a reference surface.

When vibration is detected, displacement exceeds the predefined threshold of 5 cm, or a sensor fault occurs, the system activates a red LED as an early warning indicator. During normal operating conditions, the green LED remains ON.

The project aims to demonstrate a simple hardware-based monitoring and early warning prototype for improving underground mine safety awareness.

## 🎯 Objectives

- Monitor underground mine vibrations using a vibration sensor.
- Measure distance changes using a time-of-flight distance sensor.
- Identify potential displacement conditions.
- Generate visual alerts using LED indicators.
- Detect sensor initialization and measurement faults.
- Demonstrate an IoT-based safety monitoring prototype using ESP32.

## ⚙️ Components Required

| Component | Quantity | Purpose |
|---|---:|---|
| ESP32 Development Board | 1 | Main controller |
| SW-420 Vibration Sensor | 1 | Detects vibrations |
| GY-53 VL53L0X Distance Sensor | 1 | Measures distance changes |
| Green LED | 1 | Indicates normal condition |
| Red LED | 1 | Indicates warning condition |
| 220Ω Resistors | 2 | Limits LED current |
| Breadboard | 2 | Circuit assembly |
| Jumper Wires | Required | Hardware connections |

## 🔌 Pin Configuration

| Component | ESP32 GPIO Pin |
|---|---|
| SW-420 Digital Output | GPIO 27 |
| VL53L0X SDA | GPIO 21 |
| VL53L0X SCL | GPIO 22 |
| Green LED | GPIO 25 |
| Red LED | GPIO 26 |

**Additional connections:**
- Connect the sensors to the appropriate power supply and common ground.
- Connect each LED through a 220Ω current-limiting resistor.
- The distance sensor communicates with ESP32 using the I2C protocol.

**Note:** Verify the GY-53 module's pin labels and voltage compatibility before powering the circuit, as module variants may differ.

## 🧠 Working Principle

1. The ESP32 initializes the vibration and distance sensors.
2. The distance sensor takes multiple readings to establish a baseline distance.
3. The SW-420 sensor continuously detects vibration signals.
4. The VL53L0X sensor measures the current distance from the reference surface.
5. The ESP32 compares the current distance with the baseline measurement.
6. If vibration is detected or distance change exceeds 5 cm, the red LED turns ON.
7. If the system operates normally, the green LED remains ON.
8. If the distance sensor fails to provide valid readings for more than one second, the system activates the warning indicator.
9. Sensor readings and system status are displayed through the Serial Monitor.

## 🔄 Project Workflow

```text
       START
         |
         v
   Power ON ESP32
         |
         v
 Initialize Sensors
         |
         v
 Establish Baseline
    Distance Reading
         |
         v
 Read Vibration Sensor
         |
         v
 Read Distance Sensor
         |
         v
 Compare With Baseline
         |
         v
 Check Warning Conditions
         |
         v
 +---------------------------+
 | Vibration Detected OR     |
 | Displacement > 5 cm OR    |
 | Sensor Fault?             |
 +---------------------------+
        /          \
      YES           NO
       |             |
       v             v
   RED LED ON     GREEN LED ON
   ALERT STATUS   NORMAL STATUS
       |             |
       +------+------+
              |
              v
      Display Sensor Data
       on Serial Monitor
              |
              v
       Repeat Monitoring
```

## 💻 Software and Technologies

- **Arduino IDE** – Programming and uploading code to ESP32.
- **Embedded C/C++** – Microcontroller programming.
- **ESP32** – Main processing and control unit.
- **I2C Communication** – Communication with VL53L0X distance sensor.
- **Adafruit VL53L0X Library** – Distance sensor interfacing.
- **Wire Library** – I2C communication support.

## 📊 Alert Conditions

| Condition | Green LED | Red LED | System Status |
|---|---|---|---|
| Normal operation | ON | OFF | NORMAL |
| Vibration detected | OFF | ON | VIBRATION ALERT |
| Displacement exceeds 5 cm | OFF | ON | DISPLACEMENT ALERT |
| Vibration and displacement | OFF | ON | COMBINED ALERT |
| Sensor fault | OFF | ON | SENSOR FAULT |

## 🛠️ Implementation

- Interfaced the SW-420 vibration sensor with ESP32 through GPIO 27.
- Connected the GY-53 VL53L0X distance sensor using I2C communication.
- Established a baseline distance using multiple sensor readings.
- Implemented a 5 cm displacement threshold for warning detection.
- Developed LED-based visual alert functionality.
- Added sensor fault detection for invalid distance readings.
- Displayed vibration, distance, and warning information through the Serial Monitor.

## ▶️ How to Run the Project

1. Install the Arduino IDE on your computer.
2. Install ESP32 board support in Arduino IDE.
3. Install the **Adafruit VL53L0X** library.
4. Connect the ESP32, SW-420 sensor, VL53L0X sensor, and LEDs according to the circuit diagram.
5. Open the Arduino source code.
6. Select the appropriate ESP32 board and COM port.
7. Upload the program to the ESP32.
8. Open the Serial Monitor at **115200 baud rate**.
9. Keep the reference target stationary during baseline calibration.
10. Observe the LED indicators and Serial Monitor output during testing.

## 📷 Hardware Output

The project prototype consists of an ESP32 board, SW-420 vibration sensor, VL53L0X distance sensor, LEDs, breadboard, and jumper wires.

The hardware demonstrates normal and warning conditions through visual LED indicators.

## 🎥 Working Demonstration

Watch the project demonstration:

[▶️ View Working Demo on YouTube](https://youtu.be/KF_RNg9GUk4)

## 📈 Results and Outcomes

- Successfully developed an ESP32-based underground mine monitoring prototype.
- Detected vibration using the SW-420 sensor.
- Measured distance changes using the VL53L0X sensor.
- Implemented a displacement warning threshold of 5 cm.
- Demonstrated normal and alert conditions using green and red LEDs.
- Implemented sensor fault detection.
- Gained practical knowledge of microcontrollers, sensor interfacing, I2C communication, and embedded programming.

## 🔮 Future Enhancements

- Integrate Wi-Fi-based remote monitoring.
- Add real-time cloud data storage and visualization.
- Implement mobile notifications for warning conditions.
- Add an OLED display for live sensor readings.
- Store historical vibration and displacement data.
- Develop a dashboard for monitoring multiple underground locations.

## ⚠️ Limitations

This project is an educational hardware prototype. It demonstrates vibration detection and relative distance-change monitoring under controlled conditions. It has not been validated as a certified underground mine safety system and should not replace industrial safety equipment or professional monitoring systems.

## 👨‍💻 Project Team

**Nithyasri M**

**Sri Dharan S**

**Kavin K**

Department of Computer Science and Engineering (Cyber Security)

K. S. R. College of Engineering

**Course:** 24ECT56 – Microprocessors and Microcontrollers

---

⭐ If you find this project interesting, consider giving this repository a star!