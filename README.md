📍 GPS Data Logger with TM1637 Display and SD Card 📘 Overview This project presents an Arduino-based GPS data logger designed for real-time vehicle tracking and data recording. It integrates a GPS module to capture location data, a TM1637 4-digit 7-segment display to show current speed, and an SD card module to store the collected data for future analysis.

The system is ideal for applications such as fleet management, route tracking, and telematics, providing a cost-effective solution for monitoring vehicle movements and performance.

🧰 Components Required Arduino Uno: The central microcontroller that orchestrates data collection, processing, and storage.

GPS Module (e.g., NEO-6M): Captures real-time geographic data including latitude, longitude, altitude, speed, and course.

TM1637 4-Digit 7-Segment Display: Displays the current speed of the vehicle in km/h.

MicroSD Card Module: Stores the logged GPS data in CSV format for later retrieval and analysis.

Jumper Wires: Facilitate connections between components.

Breadboard: Optional, for prototyping and organizing connections.

Power Supply: USB cable or external power source for the Arduino.

🔌 Circuit Connections GPS Module to Arduino: VCC → 5V

GND → GND

TX → Digital Pin 8 (RX)

RX → Digital Pin 9 (TX)

TM1637 Display to Arduino: CLK → Analog Pin A0

DIO → Analog Pin A1

VCC → 5V

GND → GND

SD Card Module to Arduino: CS → Digital Pin 10

MOSI → Digital Pin 11

MISO → Digital Pin 12

SCK → Digital Pin 13

VCC → 5V

GND → GND

🖥️ Software Setup Install Arduino IDE: Download and install the Arduino IDE suitable for your operating system.

Install Required Libraries:

TinyGPSPlus: For parsing GPS data.

SoftwareSerial: To handle serial communication with the GPS module.

SD: To interface with the SD card module.

TM1637Display: To control the 7-segment display.

TimeLib: For time-related functions.

You can install these libraries via the Arduino Library Manager (Sketch → Include Library → Manage Libraries...).

Upload the Code:

Open the provided Arduino sketch from the repository.

Connect your Arduino Uno to your computer via USB.

Select the correct board and port in the Arduino IDE.

Click the Upload button to compile and upload the code to the Arduino.

📊 Data Logging Format The system logs GPS data to the SD card in CSV format with the following columns:

lua Copy Edit

trackpoint,date,time,latitude,longitude,altitude,speed,course Each entry corresponds to a data point captured at a specific time, providing comprehensive information about the vehicle's movement.

📈 Display Functionality The TM1637 4-digit 7-segment display shows the current speed of the vehicle in kilometers per hour (km/h).

If the GPS module provides valid speed data, it is displayed directly.

If the speed data is invalid or the vehicle is stationary, a default value (e.g., 25 km/h) is displayed for demonstration purposes.

🕒 Time Management The system uses the GPS module's time data to timestamp each log entry.

UTC to Local Time Conversion: The code includes a TIME_OFFSET constant to adjust UTC time to your local timezone.

Date and Time Formatting: Dates are formatted as YYYY/MM/DD, and times as HH:MM:SS.

🧪 Testing and Validation To ensure the system operates correctly:

Serial Monitor: Open the Serial Monitor in the Arduino IDE to view real-time GPS data and system messages.

SD Card Verification:

After running the system, remove the SD card and insert it into a computer.

Open the generated CSV file to verify that data is being logged correctly.

Display Check: Observe the TM1637 display to ensure it reflects the current speed accurately.

🛠️ Troubleshooting GPS Signal Acquisition: Ensure the GPS module has a clear view of the sky to acquire satellite signals effectively.

SD Card Issues: Use a properly formatted SD card (FAT16 or FAT32) and ensure it's inserted correctly.

Library Conflicts: Verify that all required libraries are installed and up to date to prevent compilation errors.
