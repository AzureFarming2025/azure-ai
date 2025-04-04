

Smart Agriculture IoT System

Project Overview

This project is a Smart Agriculture IoT System designed to monitor and optimize farming conditions using ESP32 and various sensors. The system collects real-time environmental data, processes it, and predicts soil moisture levels using Machine Learning (Random Forest Model) deployed on Azure.

Features

Real-time Data Collection: Temperature, humidity, sunlight, and soil moisture sensors integrated with ESP32.

AI-based Predictions: Machine learning model predicts soil moisture to optimize irrigation.

Cloud Integration: Sensor data sent to Microsoft Azure for AI processing.

Custom Web Dashboard: Displays real-time sensor readings and AI predictions.

MQTT & HTTP API: Communication between ESP32, cloud, and web dashboard.


My Contributions (Peegan Dourado)

I was responsible for the following tasks in this project:

Electronics & Hardware Integration

Connected and tested temperature, humidity, sunlight, and soil moisture sensors with ESP32.

Configured OLED display (SSD1306) via I2C for real-time sensor data display.

Integrated relay module for automated irrigation control.

Ensured stable power supply and wiring for all components.


Machine Learning Model

Developed Random Forest Model to predict soil moisture based on sensor data.

Preprocessed data and trained the model using Python (pandas, scikit-learn).

Evaluated model accuracy and optimized hyperparameters.


Azure Cloud Integration

Configured Microsoft Azure to process AI tasks remotely (ESP32 does not run AI locally).

Deployed the machine learning model in the cloud and integrated it with the system.


Web Dashboard & API Integration

Implemented MQTT & HTTP API for data transmission between ESP32 and the dashboard.

Developed a custom dashboard to visualize sensor readings and AI predictions.



How to Set Up the System

1. Hardware Setup

1. Connect temperature, humidity, sunlight, and soil moisture sensors to ESP32.


2. Connect OLED display via I2C and relay module for irrigation control.


3. Power the ESP32 with a stable external power source.



2. Software & AI Model

1. Install required Python libraries:

pip install pandas numpy scikit-learn matplotlib paho-mqtt


2. Train the Random Forest Model:

python train_rf.py


3. Deploy the model on Microsoft Azure.



3. IoT & Cloud Communication

1. Upload ESP32 firmware to send sensor data via MQTT & HTTP API.


2. Configure Azure to receive data, run predictions, and send results back.


3. Use the web dashboard to monitor live sensor readings and AI predictions.



Future Improvements

Optimize power management for long-term deployment.

Improve AI model accuracy with more training data.

Add automated anomaly detection for better system performance.
