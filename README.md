# MQTTS_broker_app
Arduino IDE ESP32 all-in-one WIFI NAT, MQTTs Broker and client app

ESP32/Arduino sketch to combine some code fragments from other PlatformIO/ESPIDF sources.
Background: I wanted to have a combined solution in one ESP32 for a control app and found different pieces of code for PlatformIO and ESPIDF which I tried
to combine in one Arduino IDE sketch for simplicity. I also wanted a secure MQTT broker in the core and easy configuration and OTA update via web page.
The web page is password protected.

# NAT Router
ESP32 NAT code inspired by https://github.com/paclema/esp32_lwip_nat_example
!Needs either ESP32 Arduino core 2.05 plus liblwip.a and libvfs.a update or an ESP32 Arduino core with NAPT compiled in 
Includes a modified version of a configuration web interface including OTA support

# TinyMqttSecure
TinyMqtt broker code modified for use of ESP32_HTTPS_Server library for a simple MQTT broker with TLS.
Based on TinyMqtt https://github.com/hsaturn/TinyMqtt and ESP32_HTTPS_Server https://github.com/fhessel/esp32_https_server libraries.
Just for my application needs I modified the TinyMqtt code and combined it with slightly adapted HTTPSServer and HTTPSConnection classes 
as link to the ESP32_HTTPS_Server library to make use of HTTPSConnections instead of WiFiClient on the transport level.
Password check, QoS, retained messages etc. not checked/finished!

# MQTT client app
Plus an example app which for simplicity connects locally to the MQTT broker as subroutine.

   Essential function tested:
    Sketch for WIFI NAT plus simple MQTTS broker allowing communication of several MQTTS clients via e.g. port 8883 with TLS with a local client app.

## Provided as is.
