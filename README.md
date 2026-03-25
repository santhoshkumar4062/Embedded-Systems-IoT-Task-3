# SMART TEMPERATURE CONTROL SYSTEM

📌 Overview

- This project is a Smart Automation System built using Arduino. It reads temperature data and   automatically controls an output device like a fan or LED based on predefined conditions.

🎯 Objective

- Learn embedded decision-making (IF/ELSE)
- Implement automation logic
- Display real-time sensor data
- Understand basic IoT system behavior

🧰 Components Used

- Arduino UNO
- LM35 Temperature Sensor
- LED / Buzzer
- 220Ω Resistor
- Breadboard & Jumper wires

🔌 Circuit Diagram

- Connections:
 - LM35 Sensor
 - VCC → 5V
 - GND → GND
 - OUT → A0
- LED
  - Anode → Pin 8 (via resistor)
  - Cathode → GND

<img width="1536" height="1024" alt="Smart Temp Control System" src="https://github.com/user-attachments/assets/d8df4a8b-121a-440f-9ef9-2ec84b9a9523" />

💻 Arduino Code

- int sensorPin = A0;
- int ledPin = 8;

- float temperature;

- void setup() {
  - pinMode(ledPin, OUTPUT);
  - Serial.begin(9600);
- }

- void loop() {

  - int sensorValue = analogRead(sensorPin);

  - // Convert to voltage
  - float voltage = sensorValue * (5.0 / 1023.0);

  - // Convert to temperature (LM35)
  - temperature = voltage * 100;

  - Serial.print("Temperature: ");
  - Serial.print(temperature);
  - Serial.println(" °C");

  - // Automation Logic (IF/ELSE)
  - if (temperature > 30) {
    - digitalWrite(ledPin, HIGH);
    - Serial.println("Fan ON / Alert ON");
  - } else {
    - digitalWrite(ledPin, LOW);
    - Serial.println("Fan OFF");
  - }

  - delay(1000);
- }


⚙️ Working Principal

- Sensor reads temperature
- Arduino processes data
- If temperature exceeds threshold → Output ON
- Else → Output OFF

  
📊 Output (Serial Monitor)

- Temperature: 29°C → Fan OFF
- Temperature: 31°C → Fan ON


🚀 Future Improvements

- Add LCD Display
- Use Relay for real fan control
- Connect to IoT (ThingSpeak/Blynk)
- Mobile App Monitoring


🏁 Conclusion

- This project demonstrates how embedded systems make decisions and automate real-world tasks, forming the foundation for IoT-based smart systems.
