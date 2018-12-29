# MySensors LAN Gateway W5500
> from rhdw, Dez. 2018

Used parts:
* Arduino NANO
* WizNET W5500 Module
* NRF24L01+ Transceiver Module
***

Connection list:
( the wire color is only required for the breadboard )

| Arduino NANO | WizNET W5500 | NRF24L01+ | wire color |
| ----- | ----- | ----- | ----- |
| GND | GND | GND | sw |
| 3V3 | 3.3V | V+ | rt |
| 13 | SCLK | SCK | gn |
| 12 | MISO | MISO | vio | bl | or |
| 11 | MOSI | MOSI | bl | or |
| 10 | SCS |  | or |
| 6 |  | CSN | gr |
| 5 |  | CE | ge 
***

Compiled with Arduino 1.8.8
ProZessor: ATmega328P (Old Bootloader)
Library:
Ethernet2 by Various Version 1.0.4
MySensors by The MySensors Team Version 2.3.1

```ino
/*----------------------------------------------
  MySensors_EN_GW_W5500.ino
  ----------------------------------------------
  DESCRIPTION
  My Ethernet Gateway for Domoticz
  Arduino Nano + WitNET W5500 + NRF24L01+
  ----------------------------------------------
  REVISION HISTORY
  ----------------------------------------------
  v1.0 - 28.12.2018
*/

#define MY_DEBUG
#define MY_BAUD_RATE 9600

#define MY_RADIO_RF24
#define MY_RF24_PA_LEVEL RF24_PA_MAX
#define MY_RF24_DATARATE RF24_250KBPS
#define MY_RF24_CE_PIN 5
#define MY_RF24_CS_PIN 6

// Enable gateway ethernet module type
#define MY_GATEWAY_ENC28J60

#define MY_IP_ADDRESS 192,168,1,2
// Change the MAC Address to fit on your network
#define MY_MAC_ADDRESS 0xDE, 0xAD, 0xBE, 0xEF, 0xFE, 0xED

// If using static ip you can define Gateway and Subnet address as well
//#define MY_IP_GATEWAY_ADDRESS 192,168,1,1
//#define MY_IP_SUBNET_ADDRESS 255,255,255,0

#define MY_PORT 5003

// Enable inclusion mode
#define MY_INCLUSION_MODE_FEATURE
// Enable Inclusion mode button on gateway
//#define MY_INCLUSION_BUTTON_FEATURE
// Set inclusion mode duration (in seconds)
#define MY_INCLUSION_MODE_DURATION 60
// Digital pin used for inclusion mode button
//#define MY_INCLUSION_MODE_BUTTON_PIN  3

// Set blinking period
#define MY_DEFAULT_LED_BLINK_PERIOD 300

// Flash leds on rx/tx/err
// Uncomment to override default HW configurations
//#define MY_DEFAULT_ERR_LED_PIN 7  // Error led pin
//#define MY_DEFAULT_RX_LED_PIN  8  // Receive led pin
//#define MY_DEFAULT_TX_LED_PIN  9  // Transmit led pin

#include <SPI.h>
#include <Ethernet2.h>
#include <MySensors.h>

//----- Ethernet configuration
byte mac[] = { MY_MAC_ADDRESS };
byte ip[] = { MY_IP_ADDRESS };

//---------------------------------------------------------
void setup()
{
  Ethernet.begin(mac, ip);
}

//---------------------------------------------------------
void presentation()
{
}

//---------------------------------------------------------
void loop()
{
}
```

