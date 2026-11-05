# Fast-line-follower
High-speed line follower robot using Arduino Nano, QTR-8A sensor array and TB6612FNG driver. Goal: fastest lap with PID control. Low-cost build under $50 for Nivel 4.

Componentes de la v1 :
- **Controlador:** Arduino Uno R3 
- **Driver Motores:** TB6612FNG (STBY, PWMA, PWMB, A01/A02, B01/B02)
- **Sensores:** 2x TCRT5000 infrarrojos (V1) -> 5x TCRT5000 (V2 - J3 a J7)
- **Motores:** 2x Motor DC (M2 Izquierdo, M4 Derecho)
- **Alimentación:** Batería LiPo 7.4V 
- **Control:** Switch 
  
Componentes de la v2 :
 - esp32 blue pill
 - driver tb6612fng
 - motores pololu n20
 - switch
 - fusibles
 - bateria lipo
 - condensador
 - 6 sensores
  



Bitácora

17 de octubre de 2026 
- Creé el repositorio en GitHub.
- Pensé en cómo iba a conectar el robot a los sensores, al Arduino y al motor.

18 de octubre de 2026 
- Conecté 2 sensores LDR a Arduino UNO (A0 y A1)
- Probé lectura de umbral con indicadores LED en los pines 8 y 9.
- Código de prueba funcionando: detecta línea con umbral < 500.

- - **19  de octubre de 2026:**
- Creé diagrama de conexión completo en KiCad: Arduino UNO R3 + TB6612FNG + Batería 7.4V LiPo + Motores DC.
- Actualicé LÉAME.md y página del proyecto.



- 24 de octubre de 2026
-Diseñe la v2 del diagrama agregando 6 sensores y un swich
-publique el video de como lo hice


-26 de octubre de 2026
-Probe en wonwki el codigo y el diseño de el seguidor de linea
aunque se encontro ciertos errores en el codigo como el error de bucle infinito y una pequeña confusión con los operadores logicos
pero se arreglo

-27 de octubre de 2026
- Diseñe una parte de la v2 del diagrama agregando algunas mejoras como los 6 sensores y el stm32 blue pill y swich
- además publique un video de como lo hice

- 5 de noviembre de 20026
- empece con la v3 del diagrama del seguidor de linea añadi algunas cosas perfeccionando el diseño como la turbina de succión, algunas resistencias , regulador      conmutado,mosfet ,pulsadores y leds 

- Código - Prueba1 de Sensores
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




