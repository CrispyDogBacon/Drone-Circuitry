# Drone-Circuitry


// Include Libraries #include "Arduino.h" #include "Servo.h"

// Pin Definitions #define BRUSHLESSMOTOR1_1_PIN_DATA	5 #define BRUSHLESSMOTOR2_2_PIN_DATA	6 #define BRUSHLESSMOTOR3_3_PIN_DATA	9

// Global variables and defines const int brushlessMotor1_1LowSpeed = 1000; //Starting speed const int brushlessMotor1_1FastSpeed = 2000; //Top speed const int brushlessMotor2_2LowSpeed = 1000; //Starting speed const int brushlessMotor2_2FastSpeed = 2000; //Top speed const int brushlessMotor3_3LowSpeed = 1000; //Starting speed const int brushlessMotor3_3FastSpeed = 2000; //Top speed // object initialization Servo brushlessMotor1_1; Servo brushlessMotor2_2; Servo brushlessMotor3_3;

// define vars for testing menu const int timeout = 10000; //define timeout of 10 sec char menuOption = 0; long time0;

// Setup the essentials for your circuit to work. It runs first every time your circuit is powered with electricity. void setup() { // Setup Serial which is useful for debugging // Use the Serial Monitor to view printed messages Serial.begin(9600); while (!Serial) ; // wait for serial port to connect. Needed for native USB Serial.println("start");

// WARNING! DO NOT CONNECT THE PROPELLER UNDER TEST!
brushlessMotor1_1.attach(BRUSHLESSMOTOR1_1_PIN_DATA);
brushlessMotor1_1.writeMicroseconds(brushlessMotor1_1LowSpeed);
// WARNING! DO NOT CONNECT THE PROPELLER UNDER TEST!
brushlessMotor2_2.attach(BRUSHLESSMOTOR2_2_PIN_DATA);
brushlessMotor2_2.writeMicroseconds(brushlessMotor2_2LowSpeed);
// WARNING! DO NOT CONNECT THE PROPELLER UNDER TEST!
brushlessMotor3_3.attach(BRUSHLESSMOTOR3_3_PIN_DATA);
brushlessMotor3_3.writeMicroseconds(brushlessMotor3_3LowSpeed);
menuOption = menu();
}

// Main logic of your circuit. It defines the interaction between the components you selected. After setup, it runs over and over again, in an eternal loop. void loop() {

if(menuOption == '1') {
// A2212 Brushless Motor 1000KV (with 30A ESC) #1 - Test Code
// The motor will rotate, statrting from low speed to high speed gradually.
// WARNING! DO NOT CONNECT THE PROPELLER UNDER TEST!
// In order to reverse the motor direction disconnect the power from the circuit and replace any 2 of the 3 blue wires between the motor and the ESC (marked: 30A OPTO)
for(int brushlessMotor1_1RotationSpeed = brushlessMotor1_1LowSpeed; brushlessMotor1_1RotationSpeed <=  brushlessMotor1_1FastSpeed; brushlessMotor1_1RotationSpeed += 10)
{
brushlessMotor1_1.writeMicroseconds(brushlessMotor1_1RotationSpeed);  // 2. spin the motor at the rated speed. This number gradually changes during the 'for' loop
Serial.println(brushlessMotor1_1RotationSpeed);
delay(100);                              // 3. waits 100 milliseconds (0.1 sec). change the value in the brackets (100) for a longer or shorter delay in milliseconds.
}
for(int brushlessMotor1_1RotationSpeed = brushlessMotor1_1FastSpeed; brushlessMotor1_1RotationSpeed >=  brushlessMotor1_1LowSpeed; brushlessMotor1_1RotationSpeed -= 10)
{
brushlessMotor1_1.writeMicroseconds(brushlessMotor1_1RotationSpeed);  // 2. spin the motor at the rated speed. This number gradually changes during the 'for' loop
Serial.println(brushlessMotor1_1RotationSpeed);
delay(100);                              // 3. waits 100 milliseconds (0.1 sec). change the value in the brackets (100) for a longer or shorter delay in milliseconds.
}
brushlessMotor1_1.detach();                    // 4. release the brushless motor to conserve power and accidental operation.
}
else if(menuOption == '2') {
// A2212 Brushless Motor 1000KV (with 30A ESC) #2 - Test Code
// The motor will rotate, statrting from low speed to high speed gradually.
// WARNING! DO NOT CONNECT THE PROPELLER UNDER TEST!
// In order to reverse the motor direction disconnect the power from the circuit and replace any 2 of the 3 blue wires between the motor and the ESC (marked: 30A OPTO)
for(int brushlessMotor2_2RotationSpeed = brushlessMotor2_2LowSpeed; brushlessMotor2_2RotationSpeed <=  brushlessMotor2_2FastSpeed; brushlessMotor2_2RotationSpeed += 10)
{
brushlessMotor2_2.writeMicroseconds(brushlessMotor2_2RotationSpeed);  // 2. spin the motor at the rated speed. This number gradually changes during the 'for' loop
Serial.println(brushlessMotor2_2RotationSpeed);
delay(100);                              // 3. waits 100 milliseconds (0.1 sec). change the value in the brackets (100) for a longer or shorter delay in milliseconds.
}
for(int brushlessMotor2_2RotationSpeed = brushlessMotor2_2FastSpeed; brushlessMotor2_2RotationSpeed >=  brushlessMotor2_2LowSpeed; brushlessMotor2_2RotationSpeed -= 10)
{
brushlessMotor2_2.writeMicroseconds(brushlessMotor2_2RotationSpeed);  // 2. spin the motor at the rated speed. This number gradually changes during the 'for' loop
Serial.println(brushlessMotor2_2RotationSpeed);
delay(100);                              // 3. waits 100 milliseconds (0.1 sec). change the value in the brackets (100) for a longer or shorter delay in milliseconds.
}
brushlessMotor2_2.detach();                    // 4. release the brushless motor to conserve power and accidental operation.
}
else if(menuOption == '3') {
// A2212 Brushless Motor 1000KV (with 30A ESC) #3 - Test Code
// The motor will rotate, statrting from low speed to high speed gradually.
// WARNING! DO NOT CONNECT THE PROPELLER UNDER TEST!
// In order to reverse the motor direction disconnect the power from the circuit and replace any 2 of the 3 blue wires between the motor and the ESC (marked: 30A OPTO)
for(int brushlessMotor3_3RotationSpeed = brushlessMotor3_3LowSpeed; brushlessMotor3_3RotationSpeed <=  brushlessMotor3_3FastSpeed; brushlessMotor3_3RotationSpeed += 10)
{
brushlessMotor3_3.writeMicroseconds(brushlessMotor3_3RotationSpeed);  // 2. spin the motor at the rated speed. This number gradually changes during the 'for' loop
Serial.println(brushlessMotor3_3RotationSpeed);
delay(100);                              // 3. waits 100 milliseconds (0.1 sec). change the value in the brackets (100) for a longer or shorter delay in milliseconds.
}
for(int brushlessMotor3_3RotationSpeed = brushlessMotor3_3FastSpeed; brushlessMotor3_3RotationSpeed >=  brushlessMotor3_3LowSpeed; brushlessMotor3_3RotationSpeed -= 10)
{
brushlessMotor3_3.writeMicroseconds(brushlessMotor3_3RotationSpeed);  // 2. spin the motor at the rated speed. This number gradually changes during the 'for' loop
Serial.println(brushlessMotor3_3RotationSpeed);
delay(100);                              // 3. waits 100 milliseconds (0.1 sec). change the value in the brackets (100) for a longer or shorter delay in milliseconds.
}
brushlessMotor3_3.detach();                    // 4. release the brushless motor to conserve power and accidental operation.
}

if (millis() - time0 > timeout)
{
    menuOption = menu();
}
}

// Menu function for selecting the components to be tested // Follow serial monitor for instrcutions char menu() {

Serial.println(F("\nWhich component would you like to test?"));
Serial.println(F("(1) A2212 Brushless Motor 1000KV (with 30A ESC) #1"));
Serial.println(F("(2) A2212 Brushless Motor 1000KV (with 30A ESC) #2"));
Serial.println(F("(3) A2212 Brushless Motor 1000KV (with 30A ESC) #3"));
Serial.println(F("(menu) send anything else or press on board reset button\n"));
while (!Serial.available());

// Read data from serial monitor if received
while (Serial.available()) 
{
    char c = Serial.read();
    if (isAlphaNumeric(c)) 
    {   
        
        if(c == '1') 
			Serial.println(F("Now Testing A2212 Brushless Motor 1000KV (with 30A ESC) #1"));
		else if(c == '2') 
			Serial.println(F("Now Testing A2212 Brushless Motor 1000KV (with 30A ESC) #2"));
		else if(c == '3') 
			Serial.println(F("Now Testing A2212 Brushless Motor 1000KV (with 30A ESC) #3"));
        else
        {
            Serial.println(F("illegal input!"));
            return 0;
        }
        time0 = millis();
        return c;
    }
}
}
