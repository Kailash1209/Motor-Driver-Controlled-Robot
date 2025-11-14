# Custom Motor Driver

A complete repository for a custom motor driver hardware + firmware project.  
Includes schematics, BOM, and firmware examples for ESP32 (Arduino).

---

## 📌 Contents
- Hardware design (schematic,Simulation, BOM)
- Firmware for ESP32 (PWM + dead-time + direction)
- Bench test script and wiring diagrams
- Photos and oscilloscope captures

---

## 🔋 Supported features (typical for this repo)
- MOSFET-based,transformer and DPDT based driver
- PWM control (up to 20 kHz typical; depends on MOSFET/driver)
- Dead-time insertion to avoid shoot-through
- Current sensing (shunt + amplifier / ACS712 option)
- Over-current and thermal protection points (fuse pads, thermistor footprints)
- Logic-level interfacing: 3.3V (ESP32)
- Optional gate driver footprint (IRF540 / driver IC / gate-driver isolator)
- Connectors: power, motor, encoder inputs, UART/Serial

---

## 📸 Project photos
Add your images to `/images/` then reference them here:

![Board Photo](images/board_photo.jpg)
![Schematic](images/schematic.png)
![Waveform](images/waveform.jpg)

---

## 🧭 Quick start (flash + basic wiring)
1. Power OFF. Connect motor to `MOTOR+` / `MOTOR-`.  
2. Connect DC supply to `V+` and `GND` (observe polarity). Use appropriate fuse.  
3. Connect control MCU (ESP32) 3.3V, GND, and PWM pins to `CTRL_PWM_A` / `CTRL_PWM_B`.  
4. Verify gate-driver power rails (if using isolated gate drivers).  
5. Upload firmware from `/firmware/arduino/`.  
6. Power ON the board and run bench tests at low duty to confirm direction and response.

---

## ⚠️ Safety & warnings
- This hardware deals with high currents and potentially high voltages. Wear eye protection.  
- Always test with a current-limited source or series resistor for first-power-up.  
- Use proper heatsinking for MOSFETs and place fuses on supply.  
- Double-check MOSFET orientation and gate resistors before applying power.

---

## 🗂 Files of interest
- `hardware/BOM.csv` — bill of materials
- `hardware/kicad/` — KiCad project (placeholder)
- `firmware/arduino/MotorDriver_ESP32_PWM/` — ESP32 example

---

## 🧰 Recommended components (example)
- MOSFETs: IRF540 / IRLZ44N / AOD4184 (choose by voltage/current)
- Gate driver: IR2110 / TC4427 / IRS2003 / TLP250
- Current sense: 50 mΩ shunt + INA219 / INA826 or ACS712 (hall)
- MCU: ESP32 dev board / STM32F103 (BluePill)
- Capacitors: low-ESR electrolytic + ceramic decoupling 

---

## 📜 License
MIT — see [LICENSE](LICENSE)

---

## 🤝 Contributing
See `CONTRIBUTING.md` for guidelines.

---
