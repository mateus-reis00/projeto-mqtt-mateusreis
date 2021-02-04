INICIO DO PROJETO MQTT


Esse projto tem como desenvolfimento MQTT para monitoramento do rack ultiluzando ARDUINO e aplicativo de celular para monitamento das portas do rack
avisando quando estiver ABERTA e FECHADO mandando uma mensagem para o servidor AWS que repassa o avsio para o aplicativo de celular (https://play.google.com/store/apps/details?id=net.routix.mqttdash&hl=en&gl=US)


![imagem](https://camo.githubusercontent.com/7beef2d4780d87a603d7de49b2da0467c8537dff96575b628a04bd4010ebb1cc/68747470733a2f2f692e696d6775722e636f6d2f4d576870586b562e706e67)

foram utilizadas as seguintes blibiotecas
* [UIPEthernet](https://github.com/UIPEthernet/UIPEthernet)
* [PubSubClient](https://github.com/knolleary/pubsubclient)

# MATERIAIS

* arduino uno
* modulo Ethernet (ENC28J60)
* sensor Magnético (MC-38)
* jumpers
