🌡️ Automatic Fan Speed Control According to Room Temperature
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
🖥️ Code & Setup
The full project source code and setup guide are available in the repository. Just clone, upload, and automate your fan!

sh
Copy
Edit
git clone https://github.com/YourUsername/Auto-Fan-Speed-Control.git
🚀 Join the revolution in smart home automation! If you love this project, give it a ⭐️ and contribute to making home automation smarter and more accessible!

🔗 Let's build the future together! 🌍✨
