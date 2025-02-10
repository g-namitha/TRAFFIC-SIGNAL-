# TRAFFIC-SIGNAL-  
# Components and Connections
Components:
Arduino Uno
3 LEDs (Red, Yellow, Green)
3 Resistors (220Ω for LEDs)
Push button (for pedestrian crossing)
1 Resistor (10kΩ for the button pull-down)
Breadboard and Wires
Circuit:
LEDs:

Green LED: Connect the anode (long leg) of the Green LED to a digital pin on the Arduino (e.g., pin 2), and the cathode (short leg) to a 220Ω resistor. The other side of the resistor goes to GND.
Yellow LED: Connect the anode (long leg) of the Yellow LED to a digital pin on the Arduino (e.g., pin 3), and the cathode (short leg) to a 220Ω resistor. The other side of the resistor goes to GND.
Red LED: Connect the anode (long leg) of the Red LED to a digital pin on the Arduino (e.g., pin 4), and the cathode (short leg) to a 220Ω resistor. The other side of the resistor goes to GND.
Push Button (Pedestrian Crossing):

One leg of the button connects to 5V on the Arduino.
The other leg connects to a digital input pin on the Arduino (e.g., pin 5).
A 10kΩ pull-down resistor is placed between the button's leg connected to the input pin and GND. This ensures that when the button is not pressed, the pin reads LOW.

# How it Works:
When the button is pressed, the red light turns on immediately for 5 seconds, allowing pedestrians to cross. After 5 seconds, it returns to the normal cycle.
When the button is not pressed, the LEDs cycle through the normal traffic light sequence:
Green for 5 seconds (cars can go),
Yellow for 2 seconds (prepare to stop),
Red for 5 seconds (cars must stop).
<img width="682" alt="image" src="https://github.com/user-attachments/assets/4eb00e9c-0df7-4dea-aa7a-117fabcf9863" />
