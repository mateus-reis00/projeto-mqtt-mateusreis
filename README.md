# projeto-mqtt-mateusreis
projeto MQTT

" INICIO DO CODIGOS MQTT"


#include <PubSubClient.h
#include <UIPEthernet.h>
#include <utility/logging.h>
#include <SPI.h>
int pino2 = 2; //Cria uma variável para o Pino 2
bool estado_sensor; //Cria uma variável para Armazenar o estado do sensor

//Define o endereço MAC que será utilizado
byte mac[] = {0x68, 0x08, 0x2F, 0xA1, 0x77, 0x25};

bool mensagem;

//Inicia o cliente Ethernet
EthernetClient client;

PubSubClient mqttClient(client); 

void setup() {

   pinMode(pino2,INPUT_PULLUP); //Coloca o Pino 2 como Entrada
  Serial.begin(9600); //Inicia o Monitor Serial
  
    //Inicia o controlador Ethernet e solicita um IP para o servidor de DHCP
    Ethernet.begin(mac);

    //Inicia o monitor Serial
    Serial.begin(9600);

    mqttClient.setServer ("54.174.235.157",1883);

    //Exibe no Monitor Serial as informações sobre o IP do Arduino
    Serial.print("O IP do Arduino e: ");
    Serial.println(Ethernet.localIP());

    //Exibe no Monitor Serial as informações sobre a Máscara de Rede do Arduino
    Serial.print("A Mascara de Rede do Arduino e: ");
    Serial.println(Ethernet.subnetMask());

    //Exibe no Monitor Serial as informações sobre o Gateway do Arduino
    Serial.print("O Gateway do Arduino e: ");
    Serial.println(Ethernet.gatewayIP());

    //Exibe uma linha em branco
    Serial.println("");

   
}

void loop() { 

   estado_sensor = digitalRead(pino2); 
   
  mqttClient.connect("danielbrito");

 
   if(estado_sensor == 1){
   mensagem = mqttClient.publish("danielbrito-t","aberto!");
   }

   else{

    mensagem = mqttClient.publish("danielbrito-t","fechado!");
   }

   

  Serial.println(mensagem);
  delay(500);

  mqttClient.loop();
    

}#include <PubSubClient.h>
#include <UIPEthernet.h>
#include <utility/logging.h>
#include <SPI.h>
int pino2 = 2; //Cria uma variável para o Pino 2
bool estado_sensor; //Cria uma variável para Armazenar o estado do sensor

//Define o endereço MAC que será utilizado
byte mac[] = {0x68, 0x08, 0x2F, 0xA1, 0x77, 0x25};

bool mensagem;

//Inicia o cliente Ethernet
EthernetClient client;

PubSubClient mqttClient(client); 

void setup() {

   pinMode(pino2,INPUT_PULLUP); //Coloca o Pino 2 como Entrada
  Serial.begin(9600); //Inicia o Monitor Serial
  
    //Inicia o controlador Ethernet e solicita um IP para o servidor de DHCP
    Ethernet.begin(mac);

    //Inicia o monitor Serial
    Serial.begin(9600);

    mqttClient.setServer ("54.174.235.157",1883);

    //Exibe no Monitor Serial as informações sobre o IP do Arduino
    Serial.print("O IP do Arduino e: ");
    Serial.println(Ethernet.localIP());

    //Exibe no Monitor Serial as informações sobre a Máscara de Rede do Arduino
    Serial.print("A Mascara de Rede do Arduino e: ");
    Serial.println(Ethernet.subnetMask());

    //Exibe no Monitor Serial as informações sobre o Gateway do Arduino
    Serial.print("O Gateway do Arduino e: ");
    Serial.println(Ethernet.gatewayIP());

    //Exibe uma linha em branco
    Serial.println("");

   
}

void loop() { 

   estado_sensor = digitalRead(pino2); 
   
  mqttClient.connect("danielbrito");

 
   if(estado_sensor == 1){
   mensagem = mqttClient.publish("danielbrito-t","aberto!");
   }

   else{

    mensagem = mqttClient.publish("danielbrito-t","fechado!");
   }

   

  Serial.println(mensagem);
  delay(500);

  mqttClient.loop();
    
}

IMAGE
