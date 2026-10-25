# Fast-line-follower
High-speed line follower robot using Arduino Nano, QTR-8A sensor array and TB6612FNG driver. Goal: fastest lap with PID control. Low-cost build under $50 for Nivel 4.

Componentes:
- Microcontrolador: ESP32 / STM32 
- Sensores: Regleta 16 sensores IR (2x QTR-8A) - PCB personalizada
- Motores: 2x Pololu N20 Micro Metal Gearmotor
- Driver: TB6612FNG
- Batería: LiPo 7.4V 1000mAh JST con fusible 2A
- Chasis: Plástico 1.5-2mm altura, distancia entre ejes 70mm

Prueba 1 de código realizada de 2 sensores(con mis materiales actuales):
Código - Prueba de Sensores
```cpp
int s1, s2;
void setup(){
  pinMode(8, OUTPUT); 
  pinMode(9, OUTPUT); 
  Serial.begin(9600);
}
void loop(){
  s1 = analogRead(A0);
  s2 = analogRead(A1);
  Serial.print(s1); Serial.print(" - "); Serial.println(s2);
  digitalWrite(8, s1 < 500);
  digitalWrite(9, s2 < 500);
  delay(100);
}
