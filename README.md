# Ponderada semáforo

&nbsp;&nbsp;&nbsp;&nbsp; O presente ponderada tem como objetivo apresentar o processo de construção de um semáforo de leds com o arduino.

## Parte 1: Montagem Física do Semáforo

&nbsp;&nbsp;&nbsp;&nbsp; Na figura abaixo, é apresentada a montagem dos LEDs, assim como a de um buzzer que emitirá um som de alerta enquanto a luz estiver vermelha. Além disso, na página *assets* contém o video do funcionamento do semáfora.

&nbsp;&nbsp;&nbsp;&nbsp; Componentes utilizados:

- Fios jumpers;
- Estrutura para representar o semáforo;
- Arduino UN0;
- Resistores;
- Leds vermelho, amarelo e verde;
- Buzzer.

<br>

<div align="center">

   <img src="assets/ponderada_foto.jpg" width="100%"> 

</div>

&nbsp;&nbsp;&nbsp;&nbsp; Para maior clareza, segue abaixo o tinkercad do circuito mencionado.

<div align="center">

   <img src="assets\Terrific Kasi.png" width="100%"> 

</div>

## Parte 2: Programação e Lógica do Semáforo

&nbsp;&nbsp;&nbsp;&nbsp; Segue abaixo, o código para lógica do semáforo solicitado.

```cpp
#define LED_VERMELHO 8
#define LED_AMARELO 7
#define LED_VERDE 9
#define BUZZER_PIN 10

void setup() {
  pinMode(LED_VERMELHO, OUTPUT);
  pinMode(LED_AMARELO, OUTPUT);
  pinMode(LED_VERDE, OUTPUT);
  pinMode(BUZZER_PIN, OUTPUT);
}

void loop() {

  digitalWrite(LED_VERMELHO, HIGH);
  for (int i = 0; i < 7; i++) {
    tone(BUZZER_PIN, 1000);
    delay(428.57);
    noTone(BUZZER_PIN);
    delay(428.57);
  }
  digitalWrite(LED_VERMELHO, LOW);
  
  
  digitalWrite(LED_AMARELO, HIGH);
  delay(2000); 
  digitalWrite(LED_AMARELO, LOW);
  
  digitalWrite(LED_VERDE, HIGH);
  delay(2000); 
  digitalWrite(LED_VERDE, LOW);
  delay(1000);
  
  digitalWrite(LED_VERDE, HIGH);
  delay(2000); 
  digitalWrite(LED_VERDE, LOW);
  
  digitalWrite(LED_AMARELO, HIGH);
  delay(2000); 
  digitalWrite(LED_AMARELO, LOW);
}

```

## Parte 3: Avaliação de Pares