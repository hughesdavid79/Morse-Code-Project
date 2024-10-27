Smart Thermostat Prototype
This project implements a smart thermostat using the TI CC3220x LAUNCHXL board and various peripherals, including the TMP006 temperature sensor, buttons, and an LED. The thermostat monitors room temperature, adjusts the heating set-point based on user input, and simulates server communication through UART.

Overview
The system reads the room temperature every 500 ms, allowing for real-time monitoring. Users can adjust the desired temperature (set-point) using two buttons, and an LED indicates when heating is needed by turning on when the temperature falls below the set-point. Every second, data is sent over UART, simulating server communication by transmitting the current temperature, set-point, and heater status.

System Design
A task scheduler driven by a hardware timer manages key tasks: reading temperature, adjusting the set-point, controlling the heater, and sending UART data. The state machine transitions between idle, temperature reading, set-point adjustment, heater control, and data transmission based on events like temperature changes and button presses.

Hardware Components
TI CC3220x LAUNCHXL Board: Equipped with integrated Wi-Fi and sufficient memory for future expansion.
TMP006 Temperature Sensor: Reads temperature via I2C.
Buttons: Adjust the set-point.
LED: Indicates heating status.
UART Communication: Simulates server data transmission.
Hardware Architecture Comparison
The system design considered three hardware options:

TI CC3220x (recommended): Offers integrated Wi-Fi and adequate memory.
Microchip PIC32: Requires an external Wi-Fi module and has limited memory.
Freescale/NXP i.MX: Too complex and power-intensive for this use case.
Setup and Usage
To set up the system, connect the temperature sensor, buttons, and LED to the board. The code can be compiled using TI Code Composer Studio, then flashed onto the CC3220x. Once running, the system continuously monitors the temperature, adjusts the set-point with button inputs, and outputs data via UART.

Future Enhancements
Potential improvements include cloud connectivity for remote monitoring, a display to show the current temperature and set-point, and expanding the task scheduler for more complex control features.
