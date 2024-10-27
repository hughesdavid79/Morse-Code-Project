CS-350 Milestone 3: Morse Code LED Blinker
This project involves programming the TI CC3220S LaunchPad to blink LEDs in Morse code patterns representing "SOS" and "OK." It uses timers, interrupts, and a state machine to manage the blinking sequences.

Overview
The Morse code LED blinker is controlled by a timer and button input. When the timer reaches a specified period, it triggers a callback function to drive the state machine, which controls the LED patterns. The system toggles between "SOS" and "OK" sequences based on button presses, with the state machine transitioning through each Morse code character.

Functionality
LED Blinking Patterns: The LEDs blink in Morse code for "SOS" (dot-dot-dot, dash-dash-dash, dot-dot-dot) or "OK" (dash, dot, dash) based on user input.
Button Control: Pressing a button toggles between the "SOS" and "OK" sequences.
Timer-Based State Machine: A hardware timer periodically triggers state transitions to control the speed of the blinking.
System Design
Timer Configuration
The system uses a continuous callback timer, configured to trigger every 500 ms (500,000 µs). This callback drives the state machine, which dictates the LED pattern based on the toggled flag.

Button Interrupts
The button is configured with a falling edge interrupt to detect presses. When the button is pressed, an interrupt service routine toggles the pattern between "SOS" and "OK."

State Machine
The state machine transitions through different states to execute the Morse code patterns:

SOS State Sequence: Moves through states to blink the LEDs in a dot-dot-dot, dash-dash-dash, dot-dot-dot pattern.
OK State Sequence: Moves through states to blink in a dash, dot, dash sequence. The state machine returns to the start state after completing a sequence.
File Structure
src/ - Source code for the timer, interrupts, and state machine logic.
docs/ - Documentation and diagrams explaining the project structure and state machine flow.
hardware/ - Configuration files for the LaunchPad.
Setup and Usage
Connect the LaunchPad: Set up the TI CC3220S LaunchPad with the necessary peripherals.
Build and Flash: Compile the code using Code Composer Studio and flash it onto the board.
Run the Program: Press the button to switch between "SOS" and "OK" LED blinking patterns.
Diagrams
The project includes a state machine diagram that shows the flow through each state during the Morse code sequences. The diagram illustrates how the system initializes, executes dot and dash sequences, and loops back to the start.
