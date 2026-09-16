# Arduino Development on Kali Linux

A beginner-friendly Arduino project demonstrating how to set up Arduino development on Kali Linux and upload a basic Blink program to an Arduino board.

## Project Overview

This repository provides a simple starting point for Arduino development in a Kali Linux environment.

The included example uses the Arduino built-in LED to demonstrate:

- Arduino IDE setup
- Arduino programming
- Basic GPIO control
- Compiling and uploading an Arduino program
- Git and GitHub project management

## Project Structure

```text

arduino-kali-linux-setup/
├── README.md
├── examples/
│   └── blink/
│       └── blink.ino
├── docs/
└── requirements/
    └── libraries.txt

Hardware Requirements
Arduino-compatible development board
USB cable compatible with the Arduino board
Computer running Kali Linux

The Blink program uses LED_BUILTIN, so the exact LED pin does not need to be specified in the program.

Software Requirements
Kali Linux
Arduino IDE
Git
USB access to the Arduino board

Arduino IDE
This project was tested with:

Arduino IDE 1.8.19

Check your Arduino IDE installation with:
arduino --version

Expected output:
Arduino: 1.8.19

Git
Check Git with:

git --version

Example:
git version 2.53.0

Download the Repository
Clone the repository using:

git clone https://github.com/YOUR-USERNAME/arduino-kali-linux-setup.git

Enter the project directory:
cd arduino-kali-linux-setup

Arduino Blink Example
The Blink example is located at:

examples/blink/blink.ino

The program turns the built-in LED ON for one second and OFF for one second repeatedly.

Program
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000);

  digitalWrite(LED_BUILTIN, LOW);
  delay(1000);
}

How to Upload the Program

Method 1: Using Arduino IDE
Connect the Arduino board to the computer using USB.
Open Arduino IDE.

Open:
examples/blink/blink.ino

Select the correct board:
Tools → Board

Select the correct serial port:
Tools → Port

Click Verify to compile the program.
Click Upload.
Wait for the upload to complete.

After successful uploading, the built-in LED should blink continuously.

Running Arduino IDE on Kali Linux
Arduino IDE can be started from the terminal with:

arduino

If the Arduino IDE opens successfully, you can use the graphical interface to select the board, port, compile the program, and upload it.

Serial Port Troubleshooting
If the Arduino does not appear under:

Tools → Port

first check the available serial devices:
ls /dev/ttyUSB*

and:
ls /dev/ttyACM*

You can also check connected USB devices with:
lsusb

Disconnect the Arduino, run the command, reconnect the Arduino, and run it again to identify the newly detected device.

Linux Permission Troubleshooting
If you receive a permission error while accessing the serial port, check the current user groups:

groups

On many Linux systems, the Arduino serial device is accessible through the dialout group.

You can add your current user to the group with:
sudo usermod -aG dialout $USER

Then log out and log back in for the group membership to take effect.

Required Libraries
The Blink example does not require any external Arduino library.

The dependency information is available in:
requirements/libraries.txt

Expected Result
After uploading the program:

LED ON
   ↓
1 second
   ↓
LED OFF
   ↓
1 second
   ↓
Repeat

The Arduino's built-in LED should continuously blink at one-second intervals.

Learning Objectives
After completing this project, a beginner should understand:

How to install and launch Arduino IDE on Kali Linux.
How to connect an Arduino board through USB.
How to select an Arduino board and serial port.
How to write a basic Arduino program.
How to compile and upload an Arduino sketch.
How to organize an Arduino project.
How to use Git for version control.
How to publish an Arduino project on GitHub.

Future Improvements
Possible additions to this repository include:

Button input example
LED control using a button
Serial communication
Analog sensor reading
DHT11 temperature and humidity sensor
Ultrasonic distance sensor
MQ-series gas sensors
Buzzer control
ESP32 examples
Sensor integration projects

Author
Created as a learning project for Arduino development and GitHub-based project sharing.

License
This project is intended for educational and learning purposes.
