# TRAFFIC-SIGNAL-  

<img width="682" alt="image" src="https://github.com/user-attachments/assets/4eb00e9c-0df7-4dea-aa7a-117fabcf9863" />
code 
 const int redLedPin = 2;
const int yellowLedPin = 3;
const int greenLedPin = 6;
const int buttonPin = 12;


const int greenLightDuration = 5000;  
const int yellowLightDuration = 3000; 
const int redLightDuration = 5000;    

void setup() {
  pinMode(redLedPin, OUTPUT);
  pinMode(yellowLedPin, OUTPUT);
  pinMode(greenLedPin, OUTPUT);

  pinMode(buttonPin, INPUT_PULLUP);
}

void loop() {
 
  if (digitalRead(buttonPin) == HIGH) {
    handlePedestrianCrossing();
  } else {
    runTrafficLightCycle();
  }
}

void runTrafficLightCycle() {
   
  digitalWrite(greenLedPin, HIGH);
  digitalWrite(yellowLedPin, LOW);
  digitalWrite(redLedPin, LOW);
  delay(greenLightDuration);
  if (digitalRead(buttonPin) == HIGH) {
    handlePedestrianCrossing();
  }

   
  digitalWrite(greenLedPin, LOW);
  digitalWrite(yellowLedPin, HIGH);
  digitalWrite(redLedPin, LOW);
  delay(yellowLightDuration);
  if (digitalRead(buttonPin) == HIGH) {
    handlePedestrianCrossing();
  }

   
  digitalWrite(greenLedPin, LOW);
  digitalWrite(yellowLedPin, LOW);
  digitalWrite(redLedPin, HIGH);
  delay(redLightDuration);
  if (digitalRead(buttonPin) == HIGH) {
    handlePedestrianCrossing();
  }
}

void handlePedestrianCrossing() {
  digitalWrite(greenLedPin, LOW);
  digitalWrite(yellowLedPin, LOW);
  digitalWrite(redLedPin, HIGH);

  delay(redLightDuration); 
}

#documentation
This program implements a basic traffic light system for controlling vehicle and pedestrian movement. It uses three LEDs to represent the traffic lights (Red, Yellow, and Green) and a button to trigger pedestrian crossing. When the pedestrian button is pressed, the traffic lights switch to a red light for a predefined duration, allowing pedestrians to cross safely.

#Pin Configuration
redLedPin (Pin 2) – Controls the red traffic light.
yellowLedPin (Pin 3) – Controls the yellow traffic light.
greenLedPin (Pin 6) – Controls the green traffic light.
buttonPin (Pin 12) – Reads the input from the pedestrian crossing button.
# Constants
greenLightDuration (5000) – The duration for the green light (5 seconds).
yellowLightDuration (3000) – The duration for the yellow light (3 seconds).
redLightDuration (5000) – The duration for the red light (5 seconds).
# The setup() function runs once when the program starts. It initializes the pin modes for the LEDs and button
redLedPin, yellowLedPin, greenLedPin: Set to OUTPUT to control the traffic light LEDs.
buttonPin: Set to INPUT_PULLUP to detect when the pedestrian button is pressed
# The loop() function continuously checks if the pedestrian button is pressed. It calls either the handlePedestrianCrossing() or runTrafficLightCycle() functions based on the button state.
# runTrafficLightCycle()
This function controls the traffic light cycle, which involves turning the LEDs on and off in sequence. The cycle goes through three stages: green light, yellow light, and red light. After each stage, the button state is checked to see if the pedestrian crossing mode should be triggered.
The green light is turned on for the duration defined by greenLightDuration, while the other lights are turned off.
The yellow light is turned on for yellowLightDuration, while the other lights are turned off.
The red light is turned on for redLightDuration, while the other lights are turned off.
After each light phase, the code checks if the pedestrian button has been pressed. If pressed, it triggers the handlePedestrianCrossing() function.
# handlePedestrianCrossing()
This function is called when the pedestrian button is pressed. It turns off the green and yellow lights, turns on the red light, and keeps it on for a predefined duration (same as the normal red light phase)
This ensures that traffic is stopped for pedestrians to cross by keeping the red light on for the duration defined by redLightDuration.








