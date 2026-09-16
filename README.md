# Arduino Development on Kali Linux with ESP32

A beginner-friendly ESP32 project demonstrating Arduino development on Kali Linux, including setup, compilation, uploading, and a basic Blink example.

## Project Overview

This repository provides a simple starting point for developing ESP32 applications using the Arduino IDE on Kali Linux.

The included Blink example was tested successfully with:

- Kali Linux
- Arduino IDE 1.8.19
- ESP32 Dev Module
- `/dev/ttyUSB0`
- GPIO 2 for the onboard LED

## Features

- Arduino IDE setup on Kali Linux
- ESP32 board configuration
- USB serial port configuration
- Basic ESP32 GPIO programming
- Blink LED example
- Git and GitHub workflow
- Beginner-friendly setup instructions

## Hardware Requirements

- ESP32 development board
- USB data cable
- Computer running Kali Linux

> The Blink example uses GPIO 2, which is commonly connected to the onboard LED on ESP32 development boards. If your particular ESP32 board uses a different onboard LED pin, change `LED_PIN` accordingly.

## Software Requirements

- Kali Linux
- Arduino IDE 1.8.19 or compatible Arduino IDE
- ESP32 board support package for Arduino IDE
- Git
- USB access to the ESP32

## Arduino IDE Setup

Start Arduino IDE from the Kali Linux terminal:

```bash
arduino

Check the Arduino IDE version:
arduino --version

Example:

Arduino: 1.8.19

ESP32 Board Configuration
In Arduino IDE, select:

Tools → Board → ESP32 Arduino → ESP32 Dev Module

The ESP32 board package must be installed before the ESP32 Dev Module appears in the Board menu.

Serial Port Configuration
Connect the ESP32 to the computer using a USB data cable.

Then select:
Tools → Port → /dev/ttyUSB0

The port can be different on another Linux system.

To find the detected serial device from the terminal:
ls /dev/ttyUSB* /dev/ttyACM* 2>/dev/null

You can also check USB devices with:
lsusb

Download the Repository
Clone the repository:

git clone https://github.com/lav-singh-2003ls786/arduino-kali-linux-setup.git

Enter the project directory:
cd arduino-kali-linux-setup

Project Structure
arduino-kali-linux-setup/
├── README.md
├── .gitignore
├── examples/
│   └── blink/
│       └── blink.ino
├── requirements/
│   └── libraries.txt
└── docs/

Blink Example
The Blink example is located at:

examples/blink/blink.ino

The program uses GPIO 2 to turn the LED ON and OFF every second.

Source Code
#define LED_PIN 2
void setup() {
  pinMode(LED_PIN, OUTPUT);
}
void loop() {
  digitalWrite(LED_PIN, HIGH);
  delay(1000);
  digitalWrite(LED_PIN, LOW);
  delay(1000);
}

How the Program Works
The program has two main functions.

setup()
pinMode(LED_PIN, OUTPUT);

This configures GPIO 2 as an output pin.

loop()
digitalWrite(LED_PIN, HIGH);
delay(1000);

The LED is turned ON for one second.

Then:
digitalWrite(LED_PIN, LOW);
delay(1000);

The LED is turned OFF for one second.
The loop() function repeats continuously.

How to Upload the Program
Connect the ESP32 to the computer using USB.
Start Arduino IDE:

arduino

Open:
examples/blink/blink.ino

Select:
Tools → Board → ESP32 Arduino → ESP32 Dev Module

Select the appropriate serial port:
Tools → Port → /dev/ttyUSB0

Click Verify to compile the program.
Click Upload.

Wait until Arduino IDE displays:
Done uploading.

The ESP32 should then restart and run the program.

Expected Result
The onboard LED should repeatedly follow this pattern:

LED ON
  ↓
1 second
  ↓
LED OFF
  ↓
1 second
  ↓
Repeat

ESP32 Upload Troubleshooting
ESP32 is not shown under Port

Check the available serial devices:
ls /dev/ttyUSB* /dev/ttyACM* 2>/dev/null

Also check:
lsusb

Try disconnecting and reconnecting the ESP32 USB cable.
Make sure the USB cable supports data transfer. Some USB cables provide power only.

Permission denied for /dev/ttyUSB0

Check your groups:
groups

If required, add your user to the dialout group:
sudo usermod -aG dialout $USER

Log out and log back in afterward.

ESP32 cannot connect while uploading
If Arduino IDE remains at:

Connecting........

some ESP32 development boards require the BOOT button to be held briefly while the upload begins.
The exact procedure can vary by ESP32 board.

LED does not blink
This example uses:

#define LED_PIN 2

GPIO 2 is common on many ESP32 development boards, but the onboard LED pin is not identical on every ESP32 board.

If your board has an onboard LED connected to another GPIO, change:
#define LED_PIN 2

to the appropriate GPIO number for your board.

Required Libraries
The Blink example does not require any external Arduino library.

The dependency information is available in:
requirements/libraries.txt

The ESP32 Arduino board support package is required for compiling ESP32 sketches.

GitHub Workflow
After cloning the repository, users can update their local copy with:

git pull

To create their own changes:

git add .
git commit -m "Describe your changes"
git push

Users need appropriate GitHub permissions to push directly to this repository. Other users can also fork the repository and work on their own copy.

Learning Objectives
After completing this project, a beginner should understand:

How to run Arduino IDE on Kali Linux.
How to install and configure ESP32 board support.
How to select an ESP32 board.
How to identify a Linux serial port.
How to write a basic ESP32 program.
How to compile an Arduino sketch.
How to upload a sketch to an ESP32.
How to use Git for version control.
How to clone a public GitHub repository.
How to organize and document an Arduino project.

Future Improvements
Possible additions to this repository include:

Button input example
External LED control
Serial communication
Analog sensor reading
DHT11 temperature and humidity sensor
Ultrasonic distance sensor
MQ-series gas sensors
Buzzer control
ESP32 Wi-Fi example
ESP32 Bluetooth example
Multiple sensor integration

Author
Created as a learning project for Arduino/ESP32 development on Kali Linux and GitHub-based project sharing.

License
This project is provided for educational and learning purposes.
