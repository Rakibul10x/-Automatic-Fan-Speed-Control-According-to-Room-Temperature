🌡️ Automatic Fan Speed Control According to Room Temperature
![Automatic fan control according to room temperature](https://github.com/user-attachments/assets/d7975d7b-eca6-4a61-b453-9240df32ef7c)

A Smart Way to Stay Cool Without Wasting Energy!

🚀 The Problem: A Common Household Dilemma

Imagine a hot summer day—you're sitting comfortably in your room, but as the temperature fluctuates, you constantly need to adjust the fan speed manually. Either it's too slow and you're sweating, or it's too fast, wasting unnecessary energy. This not only causes discomfort but also increases electricity bills.


But what if your fan knew exactly when to speed up or slow down automatically based on the room temperature? 🤔

💡 The Smart Solution: Our Intelligent Fan Controller
Welcome to the future of home automation! This project introduces an Automatic Fan Speed Controller that dynamically adjusts the fan speed based on real-time temperature and humidity levels. It’s a simple yet powerful way to increase comfort, save energy, and make your home smarter.

🛠️ How It Works
Our system consists of:
🔹 A DHT11 Sensor that continuously measures temperature and humidity.
🔹 An ESP8266 (NodeMCU) that processes sensor data and determines the optimal fan speed.
🔹 A TRIAC circuit that controls the AC fan speed based on PWM signals.
🔹 A Relay Module to manage the fan’s power state.

✨ Key Process Flow:
1️⃣ The DHT11 sensor captures the room temperature.
2️⃣ The ESP8266 reads the data and calculates the required fan speed.
3️⃣ The fan automatically adjusts its speed using a voltage regulator and TRIAC circuit.
4️⃣ If the temperature drops, the fan slows down, conserving energy.
5️⃣ If it rises, the fan speeds up—keeping you cool without manual effort!

🌍 Why This Project Matters for the Future?
💚 Energy Efficiency – Reducing unnecessary power consumption lowers electricity costs.
🏡 Home Automation – A step towards a fully automated and IoT-enabled smart home.
🌱 Sustainability – Small optimizations in energy usage contribute to a greener planet.
🛠️ DIY-Friendly – A perfect project for makers and tech enthusiasts to learn about IoT, PWM, and smart control systems.

🔮 Future Enhancements
🚀 Manual Speed Control – Adding a potentiometer for manual adjustments.
📶 Bluetooth & Wi-Fi Integration – Controlling fan speed remotely via a mobile app.
🌐 IoT Connectivity – Integrating with Google Assistant or Alexa for voice control.
🕹️ Compact Design – Using a smaller microcontroller like ATTiny85 for cost-effective solutions.

📜 Project Components
ESP8266 (NodeMCU)
DHT11 Temperature & Humidity Sensor
4-Channel Relay Module
BT136 TRIAC
Resistor Network (10K, 100K, 300K, 600K)
DIAC DB3
AC 220V Ceiling Fan
Voltage Regulator
5V DC Power Supply
![list (3)](https://github.com/user-attachments/assets/1fb0888d-7614-4cef-ab22-2b991c8a1525)

🖥️ Code & Setup
[Uplo 
#include "DHT.h"
#define DHTPIN D7     // Digital pin connected to the DHT sensor
#define DHTTYPE DHT11   // DHT 11
DHT dht(DHTPIN, DHTTYPE);
int D_1 = D1;
int D_2 = D2;
int D_3 = D3;
int D_4 = D4;


void setup() {
  Serial.begin(9600);
  Serial.println(F("DHTxx test!"));
  pinMode(D_1,OUTPUT);
   pinMode(D_2,OUTPUT);
    pinMode(D_3,OUTPUT);
    pinMode(D_4,OUTPUT);

  dht.begin();
}

void loop() {
  delay(1000);
  float h = dht.readHumidity();
  float t = dht.readTemperature();
  float f = dht.readTemperature(true);
  if (isnan(h) || isnan(t) || isnan(f))
  {
    Serial.println(F("Failed to read from DHT sensor!"));
    return;
  }
 // float hif = dht.computeHeatIndex(f, h);
 // float hic = dht.computeHeatIndex(t, h, false);
  if(t<35.0 ){
    digitalWrite(D_1,LOW);
    digitalWrite(D_3,LOW);
    digitalWrite(D_3,LOW);
    digitalWrite(D_4,LOW);
    Serial.print("Fan is off");
  }
    if(t>35.0 && t<=45.0){
   digitalWrite(D_1,HIGH);
    digitalWrite(D_2,LOW);
    digitalWrite(D_3,LOW);
    digitalWrite(D_4,LOW);
    Serial.print("Fan speed is 25%");
  }
    if(t>45.0 && t<=50.0){
    digitalWrite(D_1,LOW);
    digitalWrite(D_2,HIGH);
    digitalWrite(D_3,LOW);
    digitalWrite(D_4,LOW);
    Serial.print("Fan speed is 50%");
  }
     if(t>50.0 && t<=55.0){
    digitalWrite(D_1,LOW);
    digitalWrite(D_2,LOW);
    digitalWrite(D_3,HIGH);
    digitalWrite(D_4,LOW);
    Serial.print("Fan speed is 75%");
  }
 if(t>55.0 && t<=60.0){
    digitalWrite(D_1,LOW);
    digitalWrite(D_2,LOW);
    digitalWrite(D_3,LOW);
    digitalWrite(D_4,HIGH);
    Serial.print("Fan speed is 100%");
  }
  Serial.print(F("  Temperature: "));
  Serial.print(t);
  Serial.print("\n");
    

}
ading smart_regulator.ino…]()

🚀 Join the revolution in smart home automation! If you love this project, give it a ⭐️ and contribute to making home automation smarter and more accessible!

🔗 Let's build the future together! 🌍✨
