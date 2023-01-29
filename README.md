# CIRCUITOS-ANALOGICOS
CODIGO ARDUINO
#define MAX_8_BIT_NUM    255

int Sin;

void setup() {
  Serial.begin(9600);

  DDRD = B11111111;

}

void loop() {
  for (int i = 0; i < 360; i++) {
    Sin = ((sin(i * DEG_TO_RAD) + 1) * MAX_8_BIT_NUM) / 2;

    byte Bits = Sin;

    PORTD = Bits;

    delay(10);
    Serial.print(Sin/4);
    Serial.print(",");
    Serial.println(analogRead(A0));
  }
}
