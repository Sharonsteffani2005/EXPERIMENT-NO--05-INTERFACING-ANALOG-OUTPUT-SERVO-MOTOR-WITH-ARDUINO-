###  DATE: 22.03.24

###  NAME: SHARON STEFFANI.F
###  ROLL NO : 212223110049
###  DEPARTMENT: CSE(IOT)


# EXPERIMENT NO 05 INTERFACING ANALOG OUTPUT SERVO MOTOR WITH ARDUINO

### AIM
To interface an Analog output (servo motor) and modify the angular displacement of the servo using PWM signal .
COMPONENTS REQUIRED:
1.	Servo motor of choice (9v is preferred )
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 
6.	Servo rated power supply (dc source )


### THEORY
Servo motors and are constructed out of basic DC motors, by adding:
•	 gear reduction
•	 a position sensor for the motor shaft
•	 an electronic circuit that controls the motor's operation
Typically, a potentiometer (variable resistor) measures the position of the output shaft at all times so the controller can accurately place and maintain its setting.
Servo motors are used for angular positioning, such as in radio control airplanes.  They typically have a movement range of 180 deg but can go up to 210 deg.The output shaft of a servo does not rotate freely, but rather is made to seek a particular angular position under electronic control. 


![image](https://user-images.githubusercontent.com/36288975/163544439-1f477927-fcd4-42f0-9ce4-c863fdbf1210.png)



#### Figure-01 SERVO MOTOR SPLIT VIEW 
Control 
An external controller (such as the Arduino) tells the servo where to go with a signal know as pulse proportional modulation (PPM) or pulse code modulation (which is often confused with pulse width modulation, PWM). PWM uses 1 to 2ms out of a 20ms time period to encode its information.
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544482-3027136f-7135-4f3d-a23f-8dc2fe04194d.png)

### Figure-02 SERVO MOTOR PINS

 ![image](https://user-images.githubusercontent.com/36288975/163544513-ca497421-e6ba-4f91-871f-5cfba77f22a8.png)


### Figure-03 SERVO MOTOR OVERVIEW 

### FIGURE 04 CIRCUIT DIAGRAM

 ![image](https://github.com/Sharonsteffani2005/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979934/88811b49-7b70-499d-b1e0-fde5278c668d)


![image](https://github.com/Sharonsteffani2005/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979934/d7d610c6-0cd4-4792-a1da-7f03a4732959)

 
###SCHEMATIC VIEW:

![Screenshot 2024-03-24 205809](https://github.com/Sharonsteffani2005/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979934/d0c80472-82f7-4af5-9af4-bc1396d8c5be)

###GRAPHICAL REPRESENTATION

![image](https://github.com/Sharonsteffani2005/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/144979934/3478c93c-f273-4d66-bcf3-ba231a5cbdeb)


CIRCUIT DIAGRAM
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544618-6eb8a7b5-7f1a-428a-8d9f-fd899b145efb.png)

### FIGURE 04 CIRCUIT DIAGRAM

### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select your board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device.


### PROGRAM :
```
#include<Servo.h>
Servo sr1;
int pos=0;
int red=9;
int green=8;
void setup()
{
  sr1.attach(6);
  Serial.begin(9600);
  pinMode(red,OUTPUT);
  pinMode(green,OUTPUT);
}
void loop()
{
  for(pos=0;pos<=180;pos+=5)
  {
    sr1.write(pos);
      delay(200);
    Serial.println(pos);
     if(pos>=120)
  {
    digitalWrite(red,HIGH);
      delay(200);
    digitalWrite(red,LOW);
      delay(200);
  }
  }
  for(pos=180;pos>=0;pos-=5)
  {
    sr1.write(pos);
      delay(200);
    Serial.println(pos);
  }

    if(pos<=100)
   {
     digitalWrite(green,HIGH);
     delay(200);
     digitalWrite(green,LOW);
     delay(200);
}
  }
```

### RESULTS: 
Arduino uno interfacing with servo motor is learned and angular position is controlled .
