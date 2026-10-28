# Fast-line-follower
High-speed line follower robot using Arduino Nano, QTR-8A sensor array and TB6612FNG driver. Goal: fastest lap with PID control. Low-cost build under $50 for Nivel 4.

Componentes:
- **Controlador:** Arduino Uno R3 
- **Driver Motores:** TB6612FNG (STBY, PWMA, PWMB, A01/A02, B01/B02)
- **Sensores:** 2x TCRT5000 infrarrojos (V1) -> 5x TCRT5000 (V2 - J3 a J7)
- **Motores:** 2x Motor DC (M2 Izquierdo, M4 Derecho)
- **Alimentación:** Batería LiPo 7.4V (J2 +6V / J5 GND) + Regulador AMS1117 5V
- **Control:** Switch SPST SW1 para encendido



#### Bitácora

**17 de octubre de 2026 - Inicio del Proyecto**
- Creé el repositorio en GitHub.
- Pensé en cómo iba a conectar el robot a los sensores, al Arduino y al motor.

**18 de octubre de 2026 - Pruebas Iniciales**
- Conecté 2 sensores LDR a Arduino UNO (A0 y A1)
- Probé lectura de umbral con indicadores LED en los pines 8 y 9.
- Código de prueba funcionando: detecta línea con umbral < 500.
- 
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


**19 de octubre de 2026 - Diagrama y Documentación**
- Creé diagrama de conexión completo en KiCad: Arduino UNO R3 + TB6612FNG + Batería 7.4V LiPo + Motores DC.
- Actualicé LÉAME.md y página del proyecto.


<img width="1600" height="867" alt="d83395de-fa15-4b91-86f0-ad65f1c6ef37" src="https://github.com/user-attachments/assets/46b5b4f7-f1d6-4248-92ea-a02ed9f4fb42" />

24 de octubre de 2026
-Diseñe la v2 del diagrama agregando 6 sensores y un swich
-publique el video de como lo hice

<img width="1599" height="899" alt="ac260d0e-dc6a-477a-b5e9-326e4cbdf5f0" src="https://github.com/user-attachments/assets/2080e773-54a2-4a00-9498-a26b72936697" />

26 de octubre de 2026
Probe en wonwki el codigo y el diseño de el seguidor de linea
aunque se encontro ciertos errores en el codigo como el error de bucle infinito y una pequeña confusión con los operadores logicos
pero se arreglo

<img width="1599" height="899" alt="56dc51f9-6c23-4122-b0e5-be63713acfc6" src="https://github.com/user-attachments/assets/5c360464-a4d1-4588-957a-0f3a334a4440" />

27 de octubre de 2026
- Diseñe una parte de la v2 del diagrama unque falta terminar
<img width="1599" height="899" alt="fc816a9e-a1cb-469b-92a0-cb0e0468cf39" src="https://github.com/user-attachments/assets/f0031c76-d52d-4d59-8273-c37de59c2dd2" />
