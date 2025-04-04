# Azure AI Integration Overview

> **Note:**  
> Recent AI-related developments can currently be found in the `backendMap` API repository and the `coco-device-behavior` branch of the IoT repository.  
> For easier tracking and to build a Terraform-based deployment pipeline, all AI-related code will be separated and migrated into this repository (`azure-ai`) over time.

---

### How Azure AI is Used in This Project

- A custom machine learning model predicts optimal light levels based on healthy-condition sensor data.
- The model will be deployed to Azure AI Studio and integrated with the IoT Function App through a Private API Gateway.
- IoT devices (ESP32) already automate Ring-LED lighting based on server-assigned C2D MQTT messages.
- Full AI API deployment and Azure integration are in progress as of April 4.
- OpenAI-based chatbot features are actively considered for future expansion.

*(Related Image: Azure AI Studio-based deployment plan, IoT-AI integration flow, and automated Ring-LED control examples are attached.)*

---

### Detailed Context

This project focuses on integrating Azure AI services into an IoT-based smart farming system.

A custom machine learning prediction model was developed using Python and a local dataset, designed to recommend optimal light levels for plant growth based on environmental sensor data (temperature, humidity, light).  
The model filters data from **Cosmos DB**, selecting only records labeled as "Healthy" conditions, to predict the appropriate light level for current environmental states.

The plan is to deploy the finalized model on **Azure AI Studio** to serve it as an Azure-native API.  
This API will be securely accessed through a **Private API Gateway** by the **IoT Function App** (Node.js) to automate light control operations.

As of April 4, the model code is complete, while deployment through Azure AI Studio and full backend integration are still in progress.

Currently, IoT devices (ESP32) automate **Ring-LED** lighting based on light settings assigned by server-side C2D MQTT messages.  
This validates the core IoT workflow, and future extensions will allow similar automation for other environmental factors using the same AI-driven approach.

Additionally, **OpenAI-based services** (via Azure OpenAI) are under consideration for future chatbot features, such as delivering dynamic tips (e.g., "Top 5% most active users"), but priority was given to numerical prediction models first to enable precise IoT control.

