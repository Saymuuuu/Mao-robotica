#include <Servo.h>
Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;
Servo servo5;
 
int flex1 = A1;
int flex2 = A2;
int flex3 = A3;
int flex4 = A4;
int flex5 = A5;

void setup() {
  Serial.begin(9600);
  servo1.attach(2);
  servo2.attach(3);
  servo3.attach(4);
  servo4.attach(5);
  servo5.attach(6);
}
void loop() {
  int flex1_pos = analogRead(flex1); 
  int servo1_pos = map(flex1_pos, 790, 859, 0, 180); 
  servo1.write(constrain(servo1_pos, 0, 180));
 
  int flex2_pos = analogRead(flex2); 
  int servo2_pos = map(flex2_pos, 880, 831, 0, 180); 
  servo2.write(constrain(servo2_pos, 0, 180));
 
  int flex3_pos = analogRead(flex3); 
  int servo3_pos = map(flex3_pos, 793, 827, 0, 180); 
  servo3.write(constrain(servo3_pos, 0, 180));
  int servo4_pos = map(flex4_pos, 835, 859, 0, 180); 
  servo4.write(constrain(servo4_pos, 0, 180));
 
  int flex5_pos = analogRead(flex5); 
  int servo5_pos = map(flex5_pos, 827, 793, 0, 180); 
  servo5.write(constrain(servo5_pos, 180, 0));
 
  Serial.print(flex1_pos);
  Serial.print("--");
  Serial.print(flex2_pos);
  Serial.print("--");
  Serial.print(flex3_pos);
  Serial.print("--");
  Serial.print(flex4_pos);
  Serial.print("--");
  Serial.print(flex5_pos);
  Serial.println("--");
    delay(300);
}
