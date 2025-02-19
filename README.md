# Real-Time Flood Monitoring and Alert System for Colombian Rivers

## Abstract
Colombia’s rich topography and diverse climate create both breathtaking landscapes and challenging hydrological conditions. With frequent river floods—especially during the rainy season and climatic events like La Niña—communities face significant risks to infrastructure and public safety. 

This project introduces an innovative **Internet of Things (IoT)** solution designed to monitor river water levels and environmental conditions in real-time. By integrating a suite of sensors and an intelligent alert mechanism, the system provides early detection of flood events and instant notifications to local authorities, aiming to mitigate disaster impacts and safeguard communities.

---

## 📌 Introduction
Flooding is a recurring and often devastating natural hazard in Colombia. where even normally benign rivers can transform into life-threatening torrents in a matter of hours. In November 2024, heavy rains led to severe flooding along major roadways in Bogotá—stranding vehicles, disrupting daily life, and endangering thousands of residents.The need for a rapid, reliable, and cost-effective flood monitoring system has never been greater.

Our Our project harnesses the power of IoT to create a proactive flood detection system that continuously monitors key environmental parameters. Through the use of multi-sensor technology and smart alert mechanisms, the system not only detects rising water levels but also assesses wind, temperature, humidity, and precipitation to determine the overall risk level. This approach provides a comprehensive view of the evolving environmental conditions, enabling prompt and informed decision-making


---

## 🎯 Motivation and Impact

**Imagine a world where communities and emergency responders receive real-time flood alerts—allowing them to evacuate in time.** 

Our system is designed with this vision in mind. By deploying an array of sensors along critical river points, we aim to:

✅ **Enhance Public Safety** – Early warnings can save lives and reduce injuries by giving communities more time to respond.  
✅ **Protect Infrastructure** – Timely notifications help minimize damage to roads, bridges, and public utilities.  
✅ **Support Emergency Management** – Real-time data feeds into centralized command centers, improving coordination during crises. 
✅ **Promote Sustainable Urban Planning** – Long-term monitoring data can inform better infrastructure design and zoning decisions. 

This project is a **step forward** in leveraging modern technology to tackle **natural disaster challenges**.

---

## 🏗 System Architecture Overview

Our flood monitoring solution is built on an IoT framework that integrates seamlessly into existing infrastructure, integrating four main modules:

### 1️⃣ Sensing
The system uses a **variety of sensors** to capture real-time environmental data:

- **Tilt Switch (within a Windsock)** – Measures wind conditions by detecting the direction and intensity of airflow.
- **DHT11 Temperature & Humidity Sensor** – Records ambient temperature and humidity, factors that can affect water evaporation and local weather dynamics.
- **Ultrasonic Sensor** – Precisely measures the distance from the sensor to the water surface, providing continuous updates on water level changes.
- **Raindrop Sensor** – Detects the presence of rain, delivering a Boolean signal to indicate precipitation events.
- **BMP180 Barometer** *(Future Upgrade)* – Although not active in the current prototype, this sensor is reserved for future storm intensity assessments by monitoring atmospheric pressure changes.

### 2️⃣ Data Processing & Aggregation
Sensor data is processed by an **Arduino Nano**, performing:

🔹 **Signal Conditioning** – Filtering and calibration ensure accurate measurements. 
🔹 **Risk Evaluation** – Custom algorithms analyze the sensor data against predefined thresholds to classify conditions into one of four risk states:  
   - **CALM (No Risk)**
   - **LOW RISK (Wind or Rain Only)**
   - **OVERFLOW RISK (Wind + Rain = Storm)**
   - **HIGH RISK (Active Flooding)**  

### 3️⃣ Alert & Notification System
To ensure **immediate alerts**, the system includes:

- **LCD Display** – Provides real-time status updates and risk levels.  
- **Active Buzzer** – Emits audible alerts when dangerous conditions are detected. 
- **LED Indicators** – Visual signals that change color based on the severity of the risk, ensuring clarity even from a distance.  

### 4️⃣ Communication Module *(Future Upgrade)*
While the prototype currently operates in a standalone mode, planned upgrades include:
- **Wireless Data Transmission** – Sends data to a centralized server.  
- **Cloud Integration** – Enables remote monitoring & advanced analytics.

![Diagrama de bloques del sistema ](https://github.com/Edwinguty2/Challenge-1/blob/main/Diagrama%20de%20bloques.jpeg)

![Esquema del sistema](https://github.com/Edwinguty2/Challenge-1/blob/main/ARQUITECTURA.jpeg)

---

## 🔧 Hardware Components

 ### 🔹**Tilt Switch in a Windsock** 
Installed within a windsock, the tilt switch reliably determines wind conditions by switching its state when wind speed makes the windsock rise. This binary output (true/false) is crucial for determining whether wind conditions contribute to the flood risk.
 ### 🔹 **DHT11 Temperature and Humidity Sensor** 
The DHT11 sensor continuously measures environmental temperature and humidity. Fluctuations in these parameters can indicate changes in weather conditions, providing early clues to the onset of heavy rainfall
 ### 🔹**SUltrasonic Sensor**
Operating within a range optimized for the prototype (approximately 2–7 cm in the model), the ultrasonic sensor accurately measures water levels. Its high resolution ensures that even small changes in river height are detected, enabling a timely response to sudden increases.
 ### 🔹**Raindrop Sensor** 
This sensor provides an immediate Boolean signal when raindrop patterns are detected, serving as a direct trigger for potential flood conditions when combined with other sensor inputs.
**BMP180 Barometer** 
Though not currently active, the BMP180 barometer is included in the design to enhance future iterations. Monitoring atmospheric pressure, this sensor can help predict the intensity of upcoming storms, offering an additional layer of precaution.

-----

## 🖥 Software Design & Implementation

### 🔹 Data Acquisition & Calibration
Sensor data is continuously sampled at high frequencies, with real-time calibration routines **ensuring accuracy**. The software accounts for environmental noise and sensor drift through adaptive filtering techniques.

### 🔹 Risk Evaluation Algorithm
A robust set of algorithms processes the multi-sensor data to evaluate flood risk. By cross-referencing sensor readings against established thresholds, the system dynamically assigns a risk level. For example:
- **CALM** – Normal water levels, low wind/rain.
- **LOW RISK** – Minor wind or slight rainfall.
- **OVERFLOW RISK** – Combined wind and rain conditions hinting at an impending storm.
- **HIGH RISK** – Significant water level increases accompanied by high winds and heavy rainfall signal an active flood.

### 🔹 User Interface & Alert System
✔ **Real-time Feedback** – The LCD continuously updates with current sensor readings and risk status.
✔ **Audible Alerts** – The active buzzer sounds distinct patterns to warn of escalating conditions.  
✔ **Visual Indicators** – LED indicators change colors according to the risk level, offering quick visual confirmation even from a distance.

### 🔹 Future Software Enhancements
Planned improvements include wireless communication protocols for remote monitoring, integration with cloud-based analytics platforms, and the application of advanced filtering algorithms to further improve data accuracy


![Esquema UML del modelo ](https://github.com/Edwinguty2/Challenge-1/blob/main/Drawing%20UML.png)

---

## 🔮 Potential Impact & Future Directions

Our **IoT-based flood monitoring system** holds the potential to transform disaster management in flood-prone regions:

✅ **Community Resilience** – Empowering communities with real-time information enables more proactive and informed responses to emerging flood threats.
✅ **Emergency Services Optimization** – Enhanced data sharing and early alerts can significantly improve the coordination and effectiveness of emergency response teams.  
✅ **Urban Infrastructure Planning** – Long-term data trends can guide future infrastructure investments and urban development plans, ensuring that new projects are resilient against flood risks.
✅ **Scalability** – TThe modular design of the system makes it adaptable to various geographical regions and scalable for broader implementation—from rural riverbanks to urban flood control systems.

By merging **cutting-edge sensor technology** with **robust software analytics**, this project is poised to make a lasting impact on **public safety and environmental monitoring**.

---

## 📜 Conclusion
This **Real-Time Flood Monitoring System** is a **game-changer** for Colombia’s flood-prone regions. With **affordable hardware** and **scalable technology**, we can **prevent disasters, protect lives, and safeguard infrastructure**.

🌊 **Flood prevention starts with early detection.** This project is the **first step** in achieving a **safer future** for all.

---

## 💡 Contributors
- **[Edwin Alejandro Gutierrez Rodriguez]**
**[Nicolas Stiven Ortiz Cortes]**
  **[Juan Díego Lemus Rey]**
- **[Universidad de La Sabana]**

---


