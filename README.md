<h1 align="center">WiFi intelligent indoor air quality guardian system</h1>

## Table of contents

- [About this Project](#about-this-project)
- [Mini host](#mini-host)
- [Air Quality Detection Module](#air-quality-detection-module)
- [Switch valves](#switch-valves)
- [Air purifier](#air-purifier)
- [Ventilator](#ventilator)

## About this project

The WiFi intelligent indoor air quality guardian system can perform indoor air circulation purification, sterilization, air renewal, and emergency exhaust.

The system consists of the following main components：

- Mini host
- Air Quality Detection Module
- Switch valves
- Air purifier
- Ventilator

![systemDiagram](systemDiagram.png)

## Mini host

The Mini host is the control center of this system, it dominates the other 4 components as follows：

- Air Quality Detection Module
- Switch valves
- Air purifier
- Ventilator

Tasks that mini host is responsible for：

- Graphical User Interface
  - System parameters setting
  - Scheduling
  - Data presentation
- Central Control System
  - Execute the control logic set by the system and the user
  - Send commands and perform corresponding actions based on the obtained air quality data
- Server and database system
  - Provide web application routing and https requests processing
  - Manipulate and store various data
- WiFi connection and MQTT communication

## Air Quality Detection Module

Implementation items and responsible tasks：

- UART communication protocol for Sensors
- Detect various harmful gases
- Alarm generation and release
- WiFi connection
- MQTT communication
  - Send air quality data to mini host
  - Receive commands from mini host

## Switch valves

Implementation items and responsible tasks：

- PWM control of motor
- Position and steering detection
- Braking to prevent collisions, loose components
- Abnormal detection such as overcurrent and idling
- Execute the task of switching air ducts in various indoor spaces
- WiFi connection
- MQTT communication
  - Send steering position and abnormal information to mini host
  - Receive steering commands from mini host

## Air purifier

Implementation items and responsible tasks：

- Use Flash as EEPROM to store
  - Air cleaning module parameters
  - Fan motor drive board parameters
  - RF remote control parameters
- UART communication protocol of the motor drive board
- Abnormal detection of fan motor and air purification module
- Error code compilation of motor driver board and air purification module
- Filter and purify harmful substances in the air
- Standby power saving function
- WiFi connection
- MQTT communication
  - Send the operating parameters and abnormal information of the fan motor and air purification module to the mini host
  - Receive the motor gear speed and air purification module parameter commands from the Mini host

## Ventilator

Implementation items and responsible tasks：

- The function is similar to air purifier, without the air purification module
- Accelerate the renewal of indoor air
