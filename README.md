<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Automatic Fan Speed Control</title>
</head>
<body>

<h1>🌡️ Automatic Fan Speed Control According to Room Temperature</h1>

<h2>🚀 A Smart Way to Stay Cool Without Wasting Energy</h2>

<h3>🏡 The Problem: A Common Household Dilemma</h3>

<p>Imagine a hot summer day—you're sitting comfortably in your room, but as the temperature fluctuates, you constantly need to adjust the fan speed manually.</p>

<p>Either it's too slow and you're sweating, or it's too fast, wasting unnecessary energy. This not only causes discomfort but also increases electricity bills.</p>

<p>But what if your fan <b>knew</b> exactly when to speed up or slow down <b>automatically</b> based on the room temperature? 🤔</p>

<h3>💡 The Smart Solution: Our Intelligent Fan Controller</h3>

<p>Welcome to the future of home automation! This project introduces an <b>Automatic Fan Speed Controller</b> that dynamically adjusts the fan speed based on <b>real-time temperature and humidity levels</b>. It’s a simple yet powerful way to <b>increase comfort, save energy, and make your home smarter</b>.</p>

<hr>

<h2>🛠️ How It Works</h2>

<ul>
    <li>🔹 A <b>DHT11 Sensor</b> that continuously measures temperature and humidity.</li>
    <li>🔹 An <b>ESP8266 (NodeMCU)</b> that processes sensor data and determines the optimal fan speed.</li>
    <li>🔹 A <b>TRIAC circuit</b> that controls the AC fan speed based on PWM signals.</li>
    <li>🔹 A <b>Relay Module</b> to manage the fan’s power state.</li>
</ul>

<p><b>✨ Key Process Flow:</b></p>
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
    <li>✅ <b>DIY-Friendly</b> – A perfect project for makers and tech enthusiasts to learn about IoT, PWM, and smart control systems.</li>
</ul>

<hr>

<h2>🔮 Future Enhancements</h2>

<ul>
    <li>🚀 <b>Manual Speed Control</b> – Adding a <b>potentiometer</b> for manual adjustments.</li>
    <li>📶 <b>Bluetooth & Wi-Fi Integration</b> – Controlling fan speed remotely via a mobile app.</li>
    <li>🌐 <b>IoT Connectivity</b> – Integrating with <b>Google Assistant or Alexa</b> for voice control.</li>
    <li>🕹️ <b>Compact Design</b> – Using a <b>smaller microcontroller like ATTiny85</b> for cost-effective solutions.</li>
</ul>

<hr>

<h2>📜 Project Components</h2>

<ul>
    <li><b>ESP8266 (NodeMCU)</b></li>
    <li><b>DHT11 Temperature & Humidity Sensor</b></li>
    <li><b>4-Channel Relay Module</b></li>
    <li><b>BT136 TRIAC</b></li>
    <li><b>Resistor Network (10K, 100K, 300K, 600K)</b></li>
    <li><b>DIAC DB3</b></li>
    <li><b>AC 220V Ceiling Fan</b></li>
    <li><b>Voltage Regulator</b></li>
    <li><b>5V DC Power Supply</b></li>
</ul>

<hr>

<h2>🖥️ Arduino Code</h2>

<pre>
#include &lt;DHT.h&gt;

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
</pre>

<hr>

<h2>🏆 Project Outcomes</h2>

<ul>
    <li>🌡️ The fan <b>automatically adjusts its speed</b> according to temperature changes, improving comfort and energy efficiency.</li>
    <li>💰 Users experience a seamless, hands-free cooling solution, reducing <b>electricity costs</b> and enhancing sustainability.</li>
    <li>🏡 This project paves the way for <b>smart home automation</b>, offering a practical and scalable solution for modern households.</li>
</ul>

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
