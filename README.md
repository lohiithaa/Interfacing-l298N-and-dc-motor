# Interfacing-l298N-and-dc-motor
int ENA = D7;
int IN1 = D1;
int IN2 = D2;

void setup() {
  pinMode(ENA, OUTPUT);
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT); 
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);
}

void loop() {
  setDirection();
}

void setDirection()
{
  analogWrite(ENA, 255);
  digitalWrite(IN1, HIGH);
  // IN2 pin is not set to LOW
  delay(5000);
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);
  // stop the motor
  analogWrite(ENA, 0);
}
