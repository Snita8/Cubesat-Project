![WhatsApp GIF 2024-07-10 at 19 51 30](https://github.com/Snita8/Cubesat-Project/assets/173747602/97d2f2c5-ab83-4b52-8983-9048ef419886)

# Cubesat-Project 🛰️📡

# **ABSTRACT🪄**



This summer internship explores CubeSat satellite communication, aiming to enhance capabilities through innovative antenna design, signal processing, and ground station integration. Participants will gain hands-on experience in designing and optimizing communication systems, with a focus on practical applications and advancing space technology.


https://github.com/Snita8/Cubesat-Project/tree/main

# **INTRODCTION** 🗣️
[introSlideDrChinmoy (1).pdf](https://github.com/user-attachments/files/16154197/introSlideDrChinmoy.1.pdf)

[introSlideAdnaan.pdf](https://github.com/user-attachments/files/16154198/introSlideAdnaan.pdf)

## Learning ESP32 Embedded System

### 1. Getting started with ESP32 :



 
The ESP32 is a 2.4 GHz Wi-Fi and Bluetooth chip designed using low-power technology. It offers excellent power and performance for various applications. The ESP32 series includes several models: ESP32-DOWD-V3, ESP32-DOWDR2-V3, ESP32-U4WDH, ESP32-SOWD (NRND), ESP32-DOWDQ6-V3 (NRND), ESP32-DOWD (NRND), and ESP32-DOWDQ6 (NRND). The ESP32-SOWD (NRND), ESP32-DOWD (NRND), and ESP32-DOWDQ6 (NRND) use chip revision V1 or V1.1. The ESP32-DOWD-V3, ESP32-DOWDR2-V3, ESP32-U4WDH, and ESP32-DOWDG6



![WhatsApp Image 2024-07-10 at 07 48 31](https://github.com/Snita8/Cubesat-Project/assets/173747602/cf0a576b-a53d-4b55-bd92-c9fae077f7d0)


📍 [diagram for ESP32-WROOM-32E & ESP32-WROOM-32UE] 

![WhatsApp Image 2024-07-10 at 08 02 43](https://github.com/Snita8/Cubesat-Project/assets/173747602/2ffc09ab-0c0a-4ccb-bb21-ae222548dc4b)


### 2. Development Environment Setup :

 ### ✶ Arduino IDE setup :
 Download and Install Arduino IDE : from official website
[Uploading Arduino IDE.webloc…]()<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>URL</key>
	<string>https://www.arduino.cc/en/software</string>
</dict>
</plist>

 ### ✶ Configure Arduino IDE ESP32 :

 -> Open the Arduino IDE , go to the file > Preference .
 
 -> Add this URL to the additional board manager URLs :
 

[https://dl.espressif.com/dl/package_esp32_index.json]

-> Go to Tools > Board > Boards Manager .
search for "esp32"  and install it.


### 3.First Program :

✶ Hardware setup:
 Connect the ESP32 to your computer via USB.
 
✶ Select Board and port :
In the Arduino IDE, select your ESP32  board model and the correct COM port under Tools > Board and Tools > Port .

✶ write and upload a simple LED Blink Program :

![WhatsApp GIF 2024-07-11 at 00 43 42](https://github.com/Snita8/Cubesat-Project/assets/173747602/694488c3-d8a5-41fa-8766-afc81cf83901)




```cpp

void setup() {
  pinMode(2, OUTPUT); // Initialize GPIO2 as an output pin
}

void loop() {
  digitalWrite(2, HIGH); // Turn the LED on
  delay(1000);           // Wait for a second
  digitalWrite(2, LOW);  // Turn the LED off
  delay(1000);           // Wait for a second
}
```

✶ write and upload double LED Blink Program :

![WhatsApp GIF 2024-07-11 at 00 40 29](https://github.com/Snita8/Cubesat-Project/assets/173747602/76809baa-3f62-4767-9ea7-07e67b0a2644)


```cpp
// Define the LED pins
const int ledPin1 = 2;
const int ledPin2 = 4;

void setup() {
  // Initialize the LED pins as outputs
  pinMode(ledPin1, OUTPUT);
  pinMode(ledPin2, OUTPUT);
}

void loop() {
  // Turn the first LED on
  digitalWrite(ledPin1, HIGH);
  // Turn the second LED off
  digitalWrite(ledPin2, LOW);
  // Wait for 500 milliseconds
  delay(500);

  // Turn the first LED off
  digitalWrite(ledPin1, LOW);
  // Turn the second LED on
  digitalWrite(ledPin2, HIGH);
  // Wait for 500 milliseconds
  delay(500);
}

```

✶ write and upload multiple LED Blink program :

![WhatsApp GIF 2024-07-11 at 00 34 59](https://github.com/Snita8/Cubesat-Project/assets/173747602/99ddce25-3adb-48e2-94c1-8919d9503590)




```cpp
  // Define the LED pins
const int ledPin1 = 2;
const int ledPin2 = 4;
const int ledPin3 = 5;

void setup() {
  // Initialize the LED pins as outputs
  pinMode(ledPin1, OUTPUT);
  pinMode(ledPin2, OUTPUT);
  pinMode(ledPin3, OUTPUT);
}

void loop() {
  // Turn the first LED on
  digitalWrite(ledPin1, HIGH);
  // Turn the other LEDs off
  digitalWrite(ledPin2, LOW);
  digitalWrite(ledPin3, LOW);
  // Wait for 500 milliseconds
  delay(500);

  // Turn the second LED on
  digitalWrite(ledPin1, LOW);
  digitalWrite(ledPin2, HIGH);
  digitalWrite(ledPin3, LOW);
  // Wait for 500 milliseconds
  delay(500);

  // Turn the third LED on
  digitalWrite(ledPin1, LOW);
  digitalWrite(ledPin2, LOW);
  digitalWrite(ledPin3, HIGH);
  // Wait for 500 milliseconds
  delay(500);

  // Turn all LEDs off
  digitalWrite(ledPin1, LOW);
  digitalWrite(ledPin2, LOW);
  digitalWrite(ledPin3, LOW);
  // Wait for 500 milliseconds
  delay(500);
}
```

## serial monitor

```cpp

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  Serial.println("^-^");
  delay(1000);
}
```
## OLED 

![WhatsApp Image 2024-07-11 at 00 32 41](https://github.com/Snita8/Cubesat-Project/assets/173747602/b7d6f9bf-d757-477c-ada5-a8d88f582883)


```cpp
#include<SPI.h>
#include<Wire.h>
#include<Adafruit_GFX.h>
#include<Adafruit_SSD1306.h>
#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
#define OLED_RESET 4
#define SCREEN_ADDRESS 0x3C
Adafruit_SSD1306 display(SCREEN_WIDTH,SCREEN_HEIGHT,&Wire,OLED_RESET);
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  if(!display.begin(SSD1306_SWITCHCAPVCC,SCREEN_ADDRESS))
  {
    Serial.println(F("SSD1306 allocation  failed"));
    for(;;);
  }
  delay(2000);
  display.clearDisplay();
  display.setTextSize(1);
  display.setTextColor(SSD1306_WHITE);
  display.setCursor(0,0);
  display.println(F("Hello"));
  display.display();

}

void loop() {
  // put your main code here, to run repeatedly:
  display.startscrollright(0x00,0x0F);
  delay(2000);
  display.stopscroll();
  delay(1000);
  display.startscrollleft(0x00,0x0F);
  delay(2000);
  display.stopscroll();
  delay(1000);

}
```
## 1. DHT  sensor using serial monitor

![WhatsApp Image 2024-07-11 at 00 29 09](https://github.com/Snita8/Cubesat-Project/assets/173747602/12d983dc-6e62-4b04-b174-234de6094166)


```cpp
#include "DHT.h"
#define DHT11PIN 23
DHT dht(DHT11PIN, DHT11);
void setup() {
  // put your setup code here, to run once:
  Serial.begin(115200);
  dht.begin();
}

void loop() {
  // put your main code here, to run repeatedly:
  float humi = dht.readHumidity();
  float temp= dht.readTemperature();
  Serial.print("Temperature: ");
  Serial.print(temp);
  Serial.println("ōC");
  Serial.println("Humidity:");
  Serial.print(humi);
  delay(1000);
}
```

![WhatsApp Image 2024-07-11 at 00 28 58](https://github.com/Snita8/Cubesat-Project/assets/173747602/24ba2b02-48ae-4a00-9fc6-345781e9fd80)



## 2. DHT sensor using OLED

![WhatsApp Image 2024-07-11 at 00 23 47](https://github.com/Snita8/Cubesat-Project/assets/173747602/71633aa4-b5df-4eac-a2a7-00d2455b7d91)


```cpp


  
#include <Adafruit_Sensor.h>
#include <DHT.h>
#include <DHT_U.h>
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
#define OLED_RESET -1
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);

#define DHTPIN 2     // Digital pin connected to the DHT sensor
#define DHTTYPE DHT22   // DHT 22 (AM2302)

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  // Initialize the OLED display
  if (!display.begin(SSD1306_SWITCHCAPVCC, 0x3C)) {
    Serial.println(F("SSD1306 allocation failed"));
    for (;;);
  }
  display.display();
  delay(2000); // Pause for 2 seconds

  display.clearDisplay();

  // Initialize the DHT sensor
  dht.begin();
}

void loop() {
  // Reading temperature or humidity takes about 250 milliseconds!
  float humidity = dht.readHumidity();
  float temperature = dht.readTemperature();

  // Check if any reads failed and exit early (to try again).
  if (isnan(humidity) || isnan(temperature)) {
    Serial.println(F("Failed to read from DHT sensor!"));
    return;
  }

  // Clear the buffer
  display.clearDisplay();

  // Display temperature
  display.setTextSize(1);
  display.setTextColor(SSD1306_WHITE);
  display.setCursor(0, 0);
  display.print(F("Temperature: "));
  display.print(temperature);
  display.print(F(" *C"));

  // Display humidity
  display.setCursor(0, 10);
  display.print(F("Humidity: "));
  display.print(humidity);
  display.print(F(" %"));

  // Display all the information
  display.display();

  // Delay between updates
  delay(2000);
}
  
```
*Undertanding ESP32 Basics*

Pin Configuration: Familiarize yourself with the ESP32 pinout diagram. Each pin can serve multiple functions such as digital I/O, analog input, PWM output, etc.

Peripherals: ESP32 has various peripherals like ADCs, DACs, PWM, and communication interfaces (UART, I2C, SPI).

Example: Reading an Analog Sensor Value: 

```cpp
void setup() {
  Serial.begin(115200); // Start serial communication
}

void loop() {
  int sensorValue = analogRead(34); // Read analog value from GPIO34
  Serial.println(sensorValue);      // Print the value to the Serial Monitor
  delay(1000);                      // Wait for a second
}
```


## 📻 Learning Basics of Communication Systems 

**Introduction to Communication Systems**


### Analog vs. Digital Communication

#### Analog Communication

1. **Nature of Signals**: 
   - Analog signals are continuous waveforms that vary smoothly over time. 
   - These signals represent data using continuous variations in amplitude, frequency, or phase.

2. **Examples**:
   
   - Audio signals (e.g., voice over a telephone line).
   - Video signals (e.g., analog TV broadcasts).

3. **Modulation**:
   - **Amplitude Modulation (AM)**: The amplitude of the carrier signal varies in proportion to the information signal.
   - **Frequency Modulation (FM)**: The frequency of the carrier signal varies according to the information signal.

4. **Advantages**:
   - Simple to process and understand.
   - Can represent a wide range of values.

5. **Disadvantages**:
   - Susceptible to noise and interference.
   - Signal quality degrades over long distances.

#### Digital Communication

1. **Nature of Signals**: 
   - Digital signals are discrete waveforms that represent data as a sequence of binary values (0s and 1s).
   - These signals change in distinct steps or levels.

2. **Examples**:
   - Computer data transfer.
   - Digital telephony (e.g., VoIP).

3. **Modulation**:
   - **Amplitude Shift Keying (ASK)**: Digital data modulates the amplitude of the carrier signal.
   - **Frequency Shift Keying (FSK)**: Digital data modulates the frequency of the carrier signal.
   - **Phase Shift Keying (PSK)**: Digital data modulates the phase of the carrier signal.

4. **Advantages**:
   - Robust against noise and interference.
   - Easier to multiplex and encrypt.
   - Signal quality can be maintained over long distances using repeaters.

5. **Disadvantages**:
   - Requires more bandwidth compared to analog signals.
   - More complex processing and equipment.

### Modulation and Demodulation

#### Modulation

1. **Definition**:
   - Modulation is the process of varying one or more properties of a carrier signal (usually a sine wave) in accordance with a data signal.

2. **Purpose**:
   - To adapt the data signal to be transmitted over a specific medium (e.g., air, cable).
   - To enable the transmission of the signal over long distances.

3. **Types of Modulation**:
   - **Analog Modulation**:
     - **Amplitude Modulation (AM)**:
       ```text
       S(t) = A(t) * cos(2πf_ct)
       ```
       Where \( S(t) \) is the modulated signal, \( A(t) \) is the amplitude of the information signal, and \( f_c \) is the carrier frequency.
     - **Frequency Modulation (FM)**:
       ```text
       S(t) = A_c * cos(2πf_c t + 2πΔf \int_{0}^{t} m(τ) dτ)
       ```
       Where \( Δf \) is the frequency deviation and \( m(t) \) is the information signal.

   - **Digital Modulation**:
  
![WhatsApp Image 2024-07-10 at 23 06 52](https://github.com/Snita8/Cubesat-Project/assets/173747602/deaf0714-3be7-4b39-b58d-5948878256f5)

   
     - **Amplitude Shift Keying (ASK)**:
       ```text
       S(t) = A(t) * cos(2πf_ct)
       ```
       Where \( A(t) \) is a function of the binary data.
     - **Frequency Shift Keying (FSK)**:
       ```text
       S(t) = A_c * cos(2πf_1t) \quad \text{for binary 1}
       S(t) = A_c * cos(2πf_2t) \quad \text{for binary 0}
       ```
       Where \( f_1 \) and \( f_2 \) are two different carrier frequencies.
     - **Phase Shift Keying (PSK)**:
       ```text
       S(t) = A_c * cos(2πf_ct + θ_i)
       ```
       Where \( θ_i \) is the phase change corresponding to the binary data.

#### Demodulation

1. **Definition**:
   - Demodulation is the process of extracting the original information-bearing signal from a modulated carrier wave.

2. **Purpose**:
   - To recover the transmitted data at the receiver end.

3. **Types of Demodulation**:
   - **Analog Demodulation**:
     - **AM Demodulation**: Envelope detector or synchronous demodulation.
     - **FM Demodulation**: Frequency discriminator or phase-locked loop (PLL).
   
   - **Digital Demodulation**:
     - **ASK Demodulation**: Envelope detector followed by a comparator.
     - **FSK Demodulation**: Frequency discriminator or PLL.
     - **PSK Demodulation**: Coherent detector using phase comparison.

### Examples

#### Example of AM Modulation

1. **Modulation (AM)**:
   ```text
   Carrier Signal: C(t) = A_c * cos(2πf_c t)
   Information Signal: m(t)
   Modulated Signal: S(t) = [A_c + m(t)] * cos(2πf_c t)
   ```

2. **Demodulation (AM)**:
   - Use an envelope detector to extract the amplitude variations from the received signal.

#### Example of FSK Modulation

1. **Modulation (FSK)**:
   ```text
   Binary Data: 101
   S(t) = A_c * cos(2πf_1t) for binary 1
   S(t) = A_c * cos(2πf_2t) for binary 0
   ```

2. **Demodulation (FSK)**:
 - Use a frequency discriminator to separate the frequencies and determine the binary data.
     
#### Components:

 -> Transmitter: Converts data into signals.
 
 -> Receiver: Converts signals back into data.
 
 -> Channel: Medium through which signals travel (e.g., air, cables).Noise: Unwanted disturbances that affect the signals.


### Signal Processing

✶ Modulation Techniques:Amplitude Modulation (AM): Varies the amplitude of the carrier signal.

✶ Frequency Modulation (FM): Varies the frequency of the carrier signal.

✶ Digital Modulation: Techniques like Amplitude Shift Keying (ASK), Frequency Shift Keying (FSK), and Phase Shift Keying (PSK).

**Error Detection and Correction:**
Parity Check: Adds a parity bit to ensure the number of 1's is even or odd.
Hamming Code: Detects and corrects single-bit errors.

### Practical Applications 

Simulations: Use software like MATLAB or GNU Radio to simulate communication systems.

Hands-On Projects: Build simple communication systems using microcontrollers and RF modules.

(ANALOG COMMUNICATION)

![WhatsApp Image 2024-07-10 at 13 54 33](https://github.com/Snita8/Cubesat-Project/assets/173747602/740b17eb-d05c-4ace-ab17-df642660d408)





(DIGITAL COMMUNICATION)

![WhatsApp Image 2024-07-10 at 13 54 34](https://github.com/Snita8/Cubesat-Project/assets/173747602/c9c18002-f232-44a6-bd7d-6ed411e1adf7)

#### Electromagnetic Spectrum :
✶ *The electromagnetic spectrum encompasses all wavelengths of electromagnetic radiation, from radio waves to gamma rays.*


For communication, different parts of the spectrum are used:

Radio Waves: Used for wireless communication, including AM/FM radio, television, and mobile phones.

Microwaves: Used for satellite communication, WiFi, and radar.

Infrared: Used for remote controls and some communication systems.

Visible Light: Not typically used for data communication.

Ultraviolet, X-rays, Gamma Rays: Not used for communication due to their high energy and potential harm.


#### Carrier Frequency Selection
*Carrier frequency selection is crucial for avoiding interference and ensuring efficient communication.*

 ##### Factors influencing the choice include:

 ✶ Bandwidth Requirements: Higher frequencies typically allow for higher data rates.
✶ Propagation Characteristics: Lower frequencies (below 30 MHz) can travel long distances and penetrate obstacles better than higher frequencies.
✶ Regulations: Regulatory bodies allocate different frequency bands for specific uses to minimize interference.

#### Satellite Orbital Fundamentals 
*Satellite orbits are paths that satellites follow around the Earth.*

##### Key concepts include:
✶ Low Earth Orbit (LEO): 160 to 2,000 km above Earth. Used for Earth observation and some communication satellites.
✶ Medium Earth Orbit (MEO): 2,000 to 35,786 km above Earth. Used for navigation satellites like GPS.
✶ Geostationary Orbit (GEO): 35,786 km above Earth. Satellites here remain stationary relative to a point on Earth, used for communication and weather monitoring.
✶ Inclination: The angle between the satellite's orbital plane and the equatorial plane.
✶ Eccentricity: Describes the shape of the orbit; a measure of how much it deviates from a perfect circle.



![WhatsApp Image 2024-07-10 at 20 02 35](https://github.com/Snita8/Cubesat-Project/assets/173747602/d1fa63f8-84ca-454f-8cab-a3353030c3af)




##  Learning LoRa Basics

### Introduction to LoRa

Basics:

LoRa (Long Range) is a spread spectrum modulation technique derived from chirp spread spectrum (CSS) technology. It enables long-range communication with low power consumption.

Specifications:

LoRaWAN: Protocol built on top of LoRa for IoT networks.

Frequency Bands: Operates in unlicensed ISM bands (e.g., 433 MHz, 868 MHz, 915 MHz).

Modulation: Uses CSS modulation which makes it robust against interference.

### LoRa Communication Modules

1.Hardware: Use modules like SX1276 or SX1278. These modules are compatible with Arduino and ESP32.

2.Libraries: Use the Arduino LoRa library to facilitate communication.
```cpp
#include <SPI.h>
#include <LoRa.h>

void setup() {
  Serial.begin(115200);
  while (!Serial);

  if (!LoRa.begin(915E6)) {
    Serial.println("Starting LoRa failed!");
    while (1);
  }
}

void loop() {
  LoRa.beginPacket();
  LoRa.print("Hello, LoRa!");
  LoRa.endPacket();

  delay(1000);
}
```

| Product Specifications | |
|------------------------|--|
| **Module Model** | Ra-02 |
| **Package** | SMD-16 |
| **Size** | 17*16 (3.2±0.1) mm |
| **Interface** | SPI |
| **Programmable bit rate** | UP to 300Kbps |
| **Frequency Range** | 410-525 MHz |
| **Antenna** | IPEX |
| **Max Transmit Power** | 18±1 dBm |
| **Power (Typical Values)** | |
| **Power Supply** | 2.5~3.7V, Typical 3.3V |
| **433MHz** | |
| TX | 93mA |
| RX | 12.15mA |
| Standby | 1.6mA |
| **470MHz** | |
| TX | 97mA |
| RX | 12.15mA |
| Standby | 1.5mA |
| **Operating Temperature** | -30℃~85℃ |
| **Storage Environment** | -40℃~90℃, <90%RH |
| **Weight** | 0.45g |

| **Receive Sensitivity** | **Frequency** | **Spread Factor** | **SNR** | **Sensitivity** |
|-------------------------|---------------|-------------------|---------|-----------------|
| | 433MHz | 7 | -7 | -125 |
| | 433MHz | 10 | -15 | -134 |
| | 433MHz | 12 | -20 | -141 |
| | 470MHz | 7 | -7 | -126 |
| | 470MHz | 10 | -15 | -135 |
| | 470MHz | 12 | -20 | -141 |

### Applications :

Range Testing: Test the range of LoRa modules in various environments (urban, rural, indoors).

Projects: Build sensor nodes for environmental monitoring, smart agriculture, etc.

## Communicating Between Two ESp32 + LoRa

### Setting Up Hardware 

##### Connection : Connect LoRa module to ESP32 via SPI.

MISO -> GPIO1

9MOSI -> GPIO27

SCK -> GPIO5

NSS -> GPIO18

DIO0 -> GPIO26

GND -> GND

VCC -> 3.3V

*Writing the Code

Transmitter Code:
```cpp
#include <SPI.h>
#include <LoRa.h>

void setup() {
  Serial.begin(115200);
  while (!Serial);

  if (!LoRa.begin(915E6)) {
    Serial.println("Starting LoRa failed!");
    while (1);
  }
}

void loop() {
  LoRa.beginPacket();
  LoRa.print("Hello, LoRa!");
  LoRa.endPacket();

  delay(1000);
}
```
Receiver Code :

```cpp
#include <SPI.h>
#include <LoRa.h>

void setup() {
  Serial.begin(115200);
  while (!Serial);

  if (!LoRa.begin(915E6)) {
    Serial.println("Starting LoRa failed!");
    while (1);
  }
}

void loop() {
  int packetSize = LoRa.parsePacket();
  if (packetSize) {
    while (LoRa.available()) {
      String incoming = LoRa.readString();
      Serial.print("Received: ");
      Serial.println(incoming);
    }
  }
}
```
for more details : https://randomnerdtutorials.com/esp32-lora-rfm95-transceiver-arduino-ide/


## Learning Antennas (Basics, Simulation, and Design)

![WhatsApp Image 2024-07-10 at 14 46 40](https://github.com/Snita8/Cubesat-Project/assets/173747602/d2e82d9b-e603-4179-adbc-86560820acef)


[2024-0703-Antenna.pdf](https://github.com/user-attachments/files/16158642/2024-0703-Antenna.pdf)



##### Simulation using 4NECE2


Download and install 4NEC2 from [here](http://www.qsl.net/4nec2/).

##Antenna Making 




