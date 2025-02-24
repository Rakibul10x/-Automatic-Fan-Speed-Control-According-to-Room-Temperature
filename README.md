🌡️ Automatic Fan Speed Control According to Room Temperature
🚀 A Smart Way to Stay Cool Without Wasting Energy
🏡 The Problem: A Common Household Dilemma
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
✅ Energy Efficiency – Reducing unnecessary power consumption lowers electricity costs.
✅ Home Automation – A step towards a fully automated and IoT-enabled smart home.
✅ Sustainability – Small optimizations in energy usage contribute to a greener planet.
✅ DIY-Friendly – A perfect project for makers and tech enthusiasts to learn about IoT, PWM, and smart control systems.

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
![list (3)](https://github.com/user-attachments/assets/2ef2140a-e0dc-45bc-812d-d79848e21df1)

🖥️ Arduino Code
This code reads temperature data from the DHT11 sensor and adjusts the fan speed accordingly using PWM control via a relay and TRIAC circuit.

#include <DHT.h>

#define DHTPIN D4          // DHT11 sensor pin
#define DHTTYPE DHT11      // DHT Sensor Type
#define FAN_PIN D1         // Relay or TRIAC control pin

DHT dht(DHTPIN, DHTTYPE);
int temperature = 0;

void setup() {
    Serial.begin(115200);
    dht.begin();
    pinMode(FAN_PIN, OUTPUT);
    digitalWrite(FAN_PIN, LOW); // Fan initially OFF
}

void loop() {
    temperature = dht.readTemperature(); // Read temperature
    Serial.print("Temperature: ");
    Serial.print(temperature);
    Serial.println("°C");

    if (temperature >= 30) {
        analogWrite(FAN_PIN, 255); // Full speed
    } else if (temperature >= 25) {
        analogWrite(FAN_PIN, 180); // Medium speed
    } else if (temperature >= 20) {
        analogWrite(FAN_PIN, 100); // Low speed
    } else {
        analogWrite(FAN_PIN, 0); // Fan OFF
    }

    delay(2000); // Update every 2 seconds
}
![Automatic fan control according to room temperature](https://github.com/user-attachments/assets/4c84abc6-b178-4460-a208-6991e5c417f0)

⚙️ Setup Process
1️⃣ Connect the Hardware:
Connect DHT11 sensor → VCC to 3.3V, GND to GND, Data to D4 (GPIO2).
Connect Fan Relay Module → VCC to 5V, GND to GND, IN1 to D1 (GPIO5).
Connect TRIAC Circuit → Fan load controlled by the relay and TRIAC combination.
2️⃣ Upload the Code:
Install the DHT library from the Arduino Library Manager.
Select NodeMCU 1.0 (ESP-12E) as the board in Arduino IDE.
Connect your ESP8266 via USB, select the right COM port, and upload the code.
3️⃣ Testing & Adjustments:
Open the Serial Monitor (115200 baud) to view temperature readings.
Adjust temperature thresholds in the code for precise fan speed control.
For manual adjustments, a potentiometer can be added to override automatic control.
🚀 Now your fan is fully automated, adjusting speed based on room temperature!

🏆 Project Outcomes
🌡️ The fan automatically adjusts its speed according to temperature changes, improving comfort and energy efficiency.
💰 Users experience a seamless, hands-free cooling solution, reducing electricity costs and enhancing sustainability.
🏡 This project paves the way for smart home automation, offering a practical and scalable solution for modern households.

📌 Contribution & Support
If you love this project, consider giving it a ⭐ and contributing to its future enhancements!

📩 Feel free to fork, improve, and submit a pull request to add new features.

For any queries or suggestions, reach out to YourEmail@example.com.

🔗 Let's Build the Future Together! 🌍✨
