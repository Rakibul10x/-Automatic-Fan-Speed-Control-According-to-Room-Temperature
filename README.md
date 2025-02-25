<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Automatic Fan Speed Control</title>
</head>
<body>

<h1 align="center">🌡️ Automatic Fan Speed Control According to Room Temperature</h1>
<h2 align="center">🚀 A Smart Way to Stay Cool Without Wasting Energy</h2>

<hr>

<h2>🏡 The Problem</h2>

<p>Imagine a hot summer day—you're sitting comfortably in your room, but as the temperature fluctuates, you constantly need to adjust the fan speed manually.</p>

<p>Either it's too slow and you're sweating, or it's too fast, wasting unnecessary energy. This not only causes discomfort but also increases electricity bills.</p>

<p>But what if your fan <b>knew</b> exactly when to speed up or slow down <b>automatically</b> based on the room temperature? 🤔</p>

<hr>

<h2>💡 The Smart Solution</h2>

<p>Welcome to the future of home automation! This project introduces an <b>Automatic Fan Speed Controller</b> that dynamically adjusts the fan speed based on <b>real-time temperature and humidity levels</b>. It’s a simple yet powerful way to <b>increase comfort, save energy, and make your home smarter</b>.</p>

<hr>

<h2>🚀 Features</h2>

<ul>
    <li>✅ <b>Automatic Fan Speed Control</b> – No manual adjustments needed!</li>
    <li>✅ <b>Real-time Temperature Monitoring</b> – Uses a DHT11 sensor to measure room temperature.</li>
    <li>✅ <b>Energy Efficient</b> – Reduces unnecessary power consumption.</li>
    <li>✅ <b>Smart Control</b> – Works seamlessly without human intervention.</li>
    <li>✅ <b>DIY Friendly</b> – Simple and easy to build for home automation enthusiasts.</li>
</ul>

<hr>

<h2>🛠️ How It Works</h2>

<ul>
    <li>🔹 A <b>DHT11 Sensor</b> that continuously measures temperature and humidity.</li>
    <li>🔹 An <b>ESP8266 (NodeMCU)</b> that processes sensor data and determines the optimal fan speed.</li>
    <li>🔹 A <b>TRIAC circuit</b> that controls the AC fan speed based on PWM signals.</li>
    <li>🔹 A <b>Relay Module</b> to manage the fan’s power state.</li>
</ul>

<hr>

<h2>✨ Key Process Flow</h2>
<ol>
    <li>The <b>DHT11 sensor</b> captures the room temperature.</li>
    <li>The <b>ESP8266</b> reads the data and calculates the required fan speed.</li>
    <li>The fan <b>automatically</b> adjusts its speed using a <b>voltage regulator and TRIAC circuit</b>.</li>
    <li>If the temperature drops, the fan slows down, conserving energy.</li>
    <li>If it rises, the fan speeds up—keeping you cool without manual effort!</li>
</ol>

<hr>

<h2>🌍 Why This Project Matters for the Future?</h2>

<ul>
    <li>✅ <b>Energy Efficiency</b> – Reducing unnecessary power consumption lowers electricity costs.</li>
    <li>✅ <b>Home Automation</b> – A step towards a fully automated and <b>IoT-enabled</b> smart home.</li>
    <li>✅ <b>Sustainability</b> – Small optimizations in energy usage contribute to a greener planet.</li>
</ul>

<hr>

<h2>🔮 Future Enhancements</h2>

<ul>
    <li>🚀 <b>Manual Speed Control</b> – Adding a <b>potentiometer</b> for manual adjustments.</li>
    <li>📶 <b>Bluetooth & Wi-Fi Integration</b> – Controlling fan speed remotely via a mobile app.</li>
    <li>🌐 <b>IoT Connectivity</b> – Integrating with <b>Google Assistant or Alexa</b> for voice control.</li>
</ul>

<hr>

<h2>📜 Project Components</h2>

<ul>
    <li><b>ESP8266 (NodeMCU)</b></li>
    <li><b>DHT11 Temperature & Humidity Sensor</b></li>
    <li><b>4-Channel Relay Module</b></li>
    <li><b>BT136 TRIAC</b></li>
    <li><b>Resistor Network (10K, 100K, 300K, 600K)</b></li>
</ul>

<hr>

<h2>🖥️ Arduino Code</h2>

<pre>
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
    pinMode(D_1, OUTPUT);
    pinMode(D_2, OUTPUT);
    pinMode(D_3, OUTPUT);
    pinMode(D_4, OUTPUT);
    dht.begin();
}

void loop() {
    delay(1000);
    float h = dht.readHumidity();
    float t = dht.readTemperature();
    float f = dht.readTemperature(true);

    if (isnan(h) || isnan(t) || isnan(f)) {
        Serial.println(F("Failed to read from DHT sensor!"));
        return;
    }

    if (t < 35.0) {
        digitalWrite(D_1, LOW);
        digitalWrite(D_2, LOW);
        digitalWrite(D_3, LOW);
        digitalWrite(D_4, LOW);
        Serial.println("Fan is off");
    }
    if (t > 35.0 && t <= 45.0) {
        digitalWrite(D_1, HIGH);
        digitalWrite(D_2, LOW);
        digitalWrite(D_3, LOW);
        digitalWrite(D_4, LOW);
        Serial.println("Fan speed is 25%");
    }
    if (t > 45.0 && t <= 50.0) {
        digitalWrite(D_1, LOW);
        digitalWrite(D_2, HIGH);
        digitalWrite(D_3, LOW);
        digitalWrite(D_4, LOW);
        Serial.println("Fan speed is 50%");
    }
    if (t > 50.0 && t <= 55.0) {
        digitalWrite(D_1, LOW);
        digitalWrite(D_2, LOW);
        digitalWrite(D_3, HIGH);
        digitalWrite(D_4, LOW);
        Serial.println("Fan speed is 75%");
    }
    if (t > 55.0 && t <= 60.0) {
        digitalWrite(D_1, LOW);
        digitalWrite(D_2, LOW);
        digitalWrite(D_3, LOW);
        digitalWrite(D_4, HIGH);
        Serial.println("Fan speed is 100%");
    }

    Serial.print(F("Temperature: "));
    Serial.print(t);
    Serial.print("\n");
}
</pre>

<hr>

<h2>📌 Contribution & Support</h2>

<p>If you love this project, consider giving it a ⭐ and contributing to its future enhancements!</p>

<p>📩 Feel free to <b>fork</b>, <b>improve</b>, and <b>submit a pull request</b> to add new features.</p>

<p>For any queries or suggestions, reach out to <b><a href="mailto:YourEmail@example.com">YourEmail@example.com</a></b>.</p>

<hr>

<h2>🔗 Let's Build the Future Together! 🌍✨</h2>

<p>🚀 <b>Clone the Repository & Start Building:</b></p>

<pre>
git clone https://github.com/YourUsername/Auto-Fan-Speed-Control.git
</pre>

</body>
</html>
