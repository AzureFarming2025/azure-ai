Smart Agriculture IoT System with Machine Learning

Overview

This project implements a Smart Agriculture IoT System using an ESP32 microcontroller, various sensors, and Machine Learning (Random Forest Regression) to predict soil moisture levels. The system also integrates with Microsoft Azure for cloud-based data processing and visualization.

Features

Real-time monitoring of temperature, humidity, sunlight, and soil moisture.

Automated decision-making for irrigation using ML models.

Wireless data transmission via MQTT and HTTP API.

Custom web dashboard for sensor data visualization.

Local and cloud-based AI models for predictive analytics.



---

Hardware Components

ESP32 microcontroller

Temperature & Humidity Sensor (DHT11/DHT22)

Soil Moisture Sensor

Sunlight Sensor

OLED Display (SSD1306) - I2C Interface

Relay Module (for controlling water pump)

Power Supply (5V/12V as required)

Jumper Wires & Breadboard



---

Software & Libraries

Arduino IDE for ESP32 programming

VS Code for Python ML development

Python Libraries: Pandas, NumPy, Matplotlib, Scikit-learn

IoT Communication: MQTT, HTTP API

Azure IoT Hub for cloud integration



---

Circuit Connections

DHT Sensor: Data pin to GPIO

Soil Moisture Sensor: Analog output to ADC pin

Sunlight Sensor: Analog output to ADC pin

OLED Display (SSD1306): SDA to GPIO21, SCL to GPIO22

Relay Module: IN pin to GPIO



---

Machine Learning Model (Random Forest Regression)

Steps:

1. Collect Sensor Data and save it as a CSV file.


2. Preprocess Data: Normalize values using MinMaxScaler.


3. Train Model: Random Forest Regressor to predict soil moisture.


4. Evaluate Model: Calculate Mean Absolute Error (MAE) and Mean Squared Error (MSE).


5. Deploy Model: Use the trained model in the ESP32 system for real-time predictions.



from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_absolute_error, mean_squared_error

# Train Model
model = RandomForestRegressor(n_estimators=100, random_state=42)
model.fit(X_train, y_train)

# Evaluate Model
predictions = model.predict(X_test)
mae = mean_absolute_error(y_test, predictions)
mse = mean_squared_error(y_test, predictions)
print(f"MAE: {mae}, MSE: {mse}")


---

IoT Integration

MQTT Protocol: Used for sending real-time sensor data to the cloud.

HTTP API: Allows external applications to request sensor data.

Azure Integration: Data stored in Azure IoT Hub for analysis and dashboard visualization.



---

Deployment

Running the ML Model in VS Code:

1. Install dependencies: pip install pandas numpy scikit-learn matplotlib


2. Run the script: python train_rf.py



Flashing ESP32 Code:

1. Open the ESP32 Arduino Code in Arduino IDE.


2. Select ESP32 Board and correct COM Port.


3. Upload the code.



Running the Web Dashboard:

1. Start the MQTT broker.


2. Run the Python Flask/Node.js server.


3. Open the dashboard in a browser.




---

Future Enhancements

AI-based Anomaly Detection using deep learning.

Camera Integration for plant health monitoring.

Edge AI Optimization for ESP32 inference.



---

Author & Credits

Developed by Peegan Dourado. Contributions are welcome!