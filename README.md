# Projeto de Controle Térmico para Estufa

![Imagem Ilustrativa](https://github.com/ArthurDuarteBolivar/Projeto-circuitos-eletronicos/assets/106353901/31a749a6-71c6-4e94-88ec-99d0f5e2e610)

Este projeto visa controlar a temperatura em uma estufa utilizando um Arduino. Quando a temperatura ultrapassa os 30°C, o exaustor é ligado. Se a temperatura atingir os 50°C, um LED é aceso e uma sirene é ativada.


 link: https://www.tinkercad.com/things/6rLt3xg5RgI-glorious-uusam-leelo/editel?returnTo=%2Fdashboard&sharecode=gD2122Dzg5rQ0e-1LftIqRmWDZIGQ5jFlsPoLB8Fkso


## Código em C++
```cpp
int sensor;

void setup() {
  pinMode(A0, INPUT);
  pinMode(2, OUTPUT);
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  sensor = analogRead(A0);

  // 164 = 30ºC
  // 205 = 50ºC
  if (sensor >= 164) {
    Serial.println("Mais de 30ºC");
    digitalWrite(2, HIGH);
  } else {
    digitalWrite(2, LOW);
  }

  if (sensor >= 205) {
    digitalWrite(13, HIGH);
    digitalWrite(12, HIGH);
  } else {
    digitalWrite(13, LOW);
    digitalWrite(12, LOW);
  }
}
