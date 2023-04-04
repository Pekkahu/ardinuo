# ardinuo
```c++
#include <AFMotor.h>
#include <Servo.h>

AF_DCMotor motor1(1);
AF_DCMotor motor2(2);
AF_DCMotor motor3(3);
AF_DCMotor motor4(4);
Servo servo_motor;

int speed(int percent) {
    return map(percent, 0, 100, 0, 255);
};

void setup() {
    servo_motor.attach(10);
    Serial.begin(9600);
    Serial.println("show me your motivation");
    servo_motor.write(90);
}

void loop() {
    while (Serial.available() > 0) {
        String data = Serial.readStringUntil("\n");
        int data1 = data.toInt();
        switch (data1) {
            case 1:
            //FORWARD
            servo_motor.write(90);
            motor1.setSpeed(speed(100));
            motor2.setSpeed(speed(100));
            motor3.setSpeed(speed(100));
            motor4.setSpeed(speed(100));
            motor1.run(FORWARD);
            motor2.run(FORWARD);
            motor3.run(FORWARD);
            motor4.run(FORWARD);
            break;
            case 2:
            //BACKWARD
            servo_motor.write(90);
            motor1.setSpeed(speed(100));
            motor2.setSpeed(speed(100));
            motor3.setSpeed(speed(100));
            motor4.setSpeed(speed(100));
            motor1.run(BACKWARD);
            motor2.run(BACKWARD);
            motor3.run(BACKWARD);
            motor4.run(BACKWARD);
            break;
            case 3:
            //RIGHT
            servo_motor.write(45);
            motor1.setSpeed(speed(50));
            motor2.setSpeed(speed(50));
            motor3.setSpeed(speed(100));
            motor4.setSpeed(speed(100));
            motor1.run(FORWARD);
            motor2.run(FORWARD);
            motor3.run(FORWARD);
            motor4.run(FORWARD);
            break;
            case 4:
            //LEFT
            servo_motor.write(135);
            motor1.setSpeed(speed(100));
            motor2.setSpeed(speed(100));
            motor3.setSpeed(speed(50));
            motor4.setSpeed(speed(50));
            motor1.run(FORWARD);
            motor2.run(FORWARD);
            motor3.run(FORWARD);
            motor4.run(FORWARD);
            break;
            case 5:
            //BACKWARD RIGHT
            servo_motor.write(45);
            motor1.setSpeed(speed(50));
            motor2.setSpeed(speed(50));
            motor3.setSpeed(speed(100));
            motor4.setSpeed(speed(100));
            motor1.run(BACKWARD);
            motor2.run(BACKWARD);
            motor3.run(BACKWARD);
            motor4.run(BACKWARD);
            break;
            case 6:
            //BACKWARD LEFT
            servo_motor.write(135);
            motor1.setSpeed(speed(100));
            motor2.setSpeed(speed(100));
            motor3.setSpeed(speed(50));
            motor4.setSpeed(speed(50));
            motor1.run(BACKWARD);
            motor2.run(BACKWARD);
            motor3.run(BACKWARD);
            motor4.run(BACKWARD);
            break;
        }
    }
}
```
