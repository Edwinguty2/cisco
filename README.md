# IoT for Smart Ventilation - Smart Ventilation Project for Rose Cultivation in Colombia

## Project Description
This project aims to implement a smart ventilation system for the floriculture industry in Colombia, specifically for rose cultivation. By leveraging the Internet of Things (IoT) and Artificial Intelligence (AI), it plans to optimize climate control, specifically ventilation, through the use of data from environmental sensors (temperature, humidity, and energy consumption). This system will enable automation of air control, reducing energy consumption and improving operational efficiency in rural areas with limited connectivity.

## Objectives

**General Objective:** Design and develop an IoT infrastructure pilot that integrates sensor data, AI-based automation, and real-time remote monitoring to improve energy efficiency in ventilation for rose cultivation in Colombia.

**Specific Objectives:**
1. Implement a remote monitoring platform to ensure a theoretical 99% data availability in real-time through a web/mobile application.
2. Collect feedback from stakeholders during the final phase of the project to ensure satisfaction regarding energy efficiency and usability.

## Use of MQTT in the Project

**What is MQTT?**

MQTT (Message Queuing Telemetry Transport) is a lightweight and efficient messaging protocol, ideal for IoT applications due to its low bandwidth consumption and ability to operate on networks with low connectivity. Thanks to its publish/subscribe architecture, it is widely used for transmitting data between connected devices reliably and securely, even in unstable network environments.

**Why was MQTT used?**

In this project, MQTT was used for transmitting data between environmental monitoring sensors (temperature, humidity, voltage, current) and the centralized control system. The sensors collect data from the environment and send it through an MQTT client to the central gateway, which retransmits it to the final servers for storage and analysis.

**Why was MQTT used?**

MQTT's efficiency makes it an ideal option for networks with limited capacity, such as those in rural areas of Colombia. Its low energy consumption makes it the perfect solution for IoT devices powered by batteries. Additionally, it allows for real-time data transmission, which is essential for ventilation control that needs to quickly adapt to changing environmental conditions. Its publish/subscribe model ensures reliable and efficient communication, and it is easily scalable, making it easier to integrate more sensors and devices as the system grows.

## Project Infrastructure

> ![Infrastructure in Cisco Packet Tracer](https://github.com/Edwinguty2/cisco/blob/main/infra.png)

The network was designed using Cisco Packet Tracer, simulating a complete infrastructure for transmitting data between sensors and servers via MQTT.

### Network Type and Topology:
The network is hybrid, combining elements of local area network (LAN) and wide area network (WAN). The IoT sensors are connected to a central device (SBC) that transmits data through a gateway to the local network. This local network connects to the internet via a cable modem, allowing remote devices such as smartphones to access the data through Wi-Fi or mobile networks (cell tower). Routers and servers manage the transmission and storage of data, enabling both local monitoring and remote access. The network type is hybrid, and as seen in the image, the topology is also hybrid, as one end is star-shaped and connects to other branches that are generated after going out to the internet. It integrates local and remote communications for real-time visualization and control of the sensors.

### Communication Infrastructure Details
Below are the key components in the data flow:
- **Sensors:** Capture temperature, humidity, and energy consumption data. These sensors send the information via MQTT to the central gateway.
- **Single Board Computer (SBC):** Acts as the intermediary between the sensors and the MQTT Client, simulating a Raspberry Pi in the network and processing the sensor data to start the transmission.
- **MQTT Client:** This client is responsible for publishing the sensor data to the subscribed MQTT server. The publish/subscribe model ensures that only the necessary devices receive the data, allowing for efficient local and remote control.
- **Gateway:** In addition to transmitting data to the router, the gateway allows direct connection to local devices (temperature and humidity monitors, and mobile devices) to view and control the data.
- **Server:** The server receives the data transmitted by MQTT and stores it for analysis, using the MQTT Broker. Users can monitor and control the system in near real-time via this, with remote access to the information and control over the ventilation system. Furthermore, all clients can be controlled from here, demonstrating security in the control of the devices that should have that information.

## System Validation

The system was validated through a practical demonstration in a video. In the video, it is shown that the devices connected to the MQTT Client receive data in real-time. It is demonstrated that on different devices (such as monitors and mobile devices), the subscribed MQTT client is correctly configured and can receive the data sent by the sensors. Additionally, the server's functionality is validated by showing how it recognizes the connected devices and confirms the arrival of data.  
A connection test was also conducted, showing how a monitor, upon entering the gateway's password, correctly connects and begins receiving data instantly. This demonstration ensures that the infrastructure works correctly, validating both data transmission and remote/local control capability.

## References:
"Internet of Things (IoT)", HexHub, 2025. Available at: https://www.youtube.com/playlist?list=PLmolNWplRhQS1r5PdbInurvoX0MdQ7U2F. [Accessed: Mar 28, 2025].

## Contributors
- **Edwin Alejandro Gutierrez Rodriguez**  
- **Nicolas Stiven Ortiz Cortes**  
- **Juan Diego Lemus Rey**  
- **Universidad de La Sabana**
