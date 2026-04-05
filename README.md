# 🔢 STM32F446RE 4x4 Keypad Interface with ITM Debug (Bare Metal)

A bare-metal implementation of a 4x4 matrix keypad interface using STM32F446RE.
This project demonstrates low-level GPIO control, matrix scanning, and real-time debugging using ITM (Instrumentation Trace Macrocell) without using HAL libraries.

---

## 🚀 Features

* 🔧 Bare-metal (register-level) programming
* 🔢 4x4 matrix keypad scanning
* ⚡ Efficient row-column multiplexing
* 🖥️ Real-time output via ITM (no UART required)
* 🧠 Debounce handling and key release detection
* 💡 Clean and minimal embedded C implementation

---

## 🧰 Hardware Requirements

* STM32F446RE (Nucleo / custom board)
* 4x4 Matrix Keypad
* ST-Link Debugger
* Jumper wires

---

## 🔌 Pin Configuration

| Keypad | STM32 Pin |
| ------ | --------- |
| R1     | PA5       |
| R2     | PA6       |
| R3     | PA7       |
| R4     | PA8       |
| C1     | PB12      |
| C2     | PB13      |
| C3     | PB14      |
| C4     | PB15      |

---

## 🧠 How It Works

The keypad uses a matrix configuration of rows and columns.

1. All rows are set HIGH
2. One row is pulled LOW at a time
3. Columns are read to detect key press
4. If a column reads LOW → key is pressed
5. Row + Column index maps to a specific key

---

## 🔍 Example Flow

Pressing key `5`:

* Row = R1 (PA6 → LOW)
* Column = C1 (PB13 → LOW)
* Output → `'5'`

---

## ⚙️ Key Concepts Used

* GPIO register configuration (MODER, ODR, IDR, PUPDR)
* Bit masking and shifting
* Matrix scanning algorithm
* ITM-based debugging (SWV)
* Embedded C (no HAL/LL drivers)

---

## 🖥️ ITM Debug Setup

To view output in STM32CubeIDE:

1. Go to **Debug Configurations**
2. Enable **SWV (Serial Wire Viewer)**
3. Set Core Clock = **180 MHz**
4. Open **SWV ITM Data Console**
5. Enable **Port 0**

---

## 📤 Output Example

```
Pressed Key: 1
Pressed Key: 5
Pressed Key: A
```

---

## 📁 Project Structure

```
├── main.c
├── keypad.c (optional split)
├── README.md
```

---

## ⚠️ Common Issues & Fixes

| Issue              | Solution                     |
| ------------------ | ---------------------------- |
| No output in ITM   | Enable SWV + correct clock   |
| Wrong key detected | Check row/column wiring      |
| Multiple prints    | Add debounce + release logic |
| No response        | Ensure GPIO clock enabled    |

---

## 🔥 Future Improvements

* ⏱️ Interrupt-based keypad scanning
* 📟 LCD interface (16x2 / I2C)
* 🔐 Password-based access system
* 🌐 IoT integration (ESP8266 / MQTT)
* ⚡ Non-blocking scan algorithm

---

## 📚 Learning Outcomes

This project helps you understand:

* Low-level STM32 programming
* Embedded system debugging techniques
* Matrix input systems (used in keyboards, HMIs, industrial panels)

---

## 👨‍💻 Author

Md. Samiul Islam Sabbir
Embedded Systems & IoT Engineer

---

## ⭐ If You Like This Project

Give it a ⭐ on GitHub and share with fellow embedded learners!

---
