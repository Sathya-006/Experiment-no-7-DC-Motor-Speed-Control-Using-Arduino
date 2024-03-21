###  DATE: 21/03/2024

###  NAME: Sathya N
###  ROLL NO : 212221040149
###  DEPARTMENT: CSE
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```
int enable=6;
int input1=3;
int input2=4;

void setup()
{
  pinMode(enable, OUTPUT);
  pinMode(input1, OUTPUT);
  pinMode(input2, OUTPUT);
}

void loop()
{
  analogWrite(enable,255);
  delay(1000);
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(2000);
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
  delay(2000); // Wait for 1000 millisecond(s)
}
```
### OUTPUT
#### CIRCUIT DIAGRAM:
![image](https://github.com/Sathya-006/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/121661327/90b1b3e7-6792-4e56-a7a8-eeba9541775d)

#### SCHEMATIC DIAGRAM:
![Screenshot 2024-03-21 114440](https://github.com/Sathya-006/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/121661327/c23608c6-1ea7-4905-85c8-307f5accc935)


### GRAPH AND TABULATION 


![Screenshot 2024-03-21 114703](https://github.com/Sathya-006/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/121661327/e7f6cac9-f518-4983-9236-0160639f5307)


![image](https://github.com/Sathya-006/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/121661327/229478ed-4eef-40bd-816f-d5f117cfc4c1)







### RESULTS AND DISCUSSION 
 Thus the experiment to control the speed and the direction of a DC motor using L293D driver ic( H- bridge) is executed.
