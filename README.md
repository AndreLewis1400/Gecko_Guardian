Leopard Gecko Monitoring System

Overview

This Python script is designed to monitor and control a leopard gecko's habitat environment using a Raspberry Pi. It integrates various sensors and devices, including temperature and humidity sensors, an OLED display, a motion sensor, and a heat lamp relay, while providing remote monitoring capabilities via a Flask web server.

Features

Temperature & Humidity Monitoring: Uses an I2C temperature and humidity sensor to log environmental data.

Heat Lamp Control: Automatically regulates the basking lamp based on temperature thresholds.

Motion Detection: Detects movement inside the habitat.

OLED Display: Provides real-time system information including temperature, humidity, CPU, RAM, and disk usage.

Data Logging: Logs temperature and humidity data to a CSV file.

Web API: Exposes sensor data and heat lamp status via a Flask-based REST API.

Automatic Resource Cleanup: Ensures proper handling of hardware resources on shutdown.

Hardware Requirements

Raspberry Pi (Tested on Raspberry Pi 5)

I2C Temperature & Humidity Sensor (Address: 0x44)

OLED Display (SSD1306, I2C)

Relay Module for Heat Lamp (GPIO 27)

Motion Sensor (GPIO 24)

NVMe Storage (Optional for logging storage)

Software Requirements

Python 3

Flask

psutil

gpiozero

smbus2

luma.oled

PIL (Pillow)

Installation

Ensure Python and required libraries are installed:

sudo apt update && sudo apt upgrade -y
sudo apt install python3 python3-pip i2c-tools
pip install flask psutil gpiozero smbus2 luma.oled pillow

Enable I2C on the Raspberry Pi:

sudo raspi-config
# Navigate to "Interfacing Options" > "I2C" and enable it.

Clone the repository and navigate to the script directory:

git clone https://github.com/AndreLewis1400/HomeProjects.git
cd HomeProjects

Run the script:

python3 leopard_gecko_monitor.py

Configuration

Edit the CONFIG dictionary in the script to customize temperature thresholds, GPIO pins, and file paths.
