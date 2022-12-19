char inputByte; //variavel para armazenar o que é lido no serial
int sensorValue; //variavel para armazenar as leituras do potenciometro
int sensorDigital; //variavel para armazenar as leituras do sensor de luminosidade

void setup() {
  Serial.begin(9600); //inicia a comunicação serial
  pinMode(8, OUTPUT); //define o pin 8 como saida (LED verde)
  pinMode(10, OUTPUT);//define o pin 10 como saida (LED vermelho)

}

void loop() {
  while(Serial.available()>0){ //enquanto existirem dados para receber
    inputByte = Serial.read();
    if(inputByte=='A'){ //se o arduino receber a letra 'A', acende o LED verde
      digitalWrite(8,HIGH);
    }
    else if(inputByte=='a'){ //se o arduino receber a letra 'a', apaga o LED verde
      digitalWrite(8,LOW);
    }
    if(inputByte=='V'){ //se o arduino receber a letra 'V', acende o LED vermelho
      digitalWrite(10,HIGH);
    }
    else if(inputByte=='v'){ //se o arduino receber a letra 'v', apaga o LED vermelho
      digitalWrite(10,LOW);
    }
    if(inputByte=='I'){ //se o arduino receber a letra 'I', mostra as leituras do potenciometro e sensor de luminosidade
      sensorDigital = digitalRead(6); //define a variavel para receber os valores da porta digital do sensor de luminosidade
      sensorValue = analogRead(A0); //define a variavel para receber os valores da porta analogica do sensor de potenciometro
      
      Serial.println("P"); //quando o arduino for enviar a leitura do potenciometro, envia um 'P'antes para diferenciar
      Serial.println(sensorValue);
      delay(1000);
      Serial.println("L");//quando o arduino for enviar a leitura do sensor de luminosidade, envia um 'L'antes para diferenciar
      Serial.println(sensorDigital);
      delay(1000);
    }

  }
}
