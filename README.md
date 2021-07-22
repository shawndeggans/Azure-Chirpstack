# Azrue-Chirpstack
Chirpstack. On Azure. With integration for IoT Hub and IoT Central.

## About this project (WIP 06/25/2021)
This is a build based on the `chirpstack-docker` solution.
The goal is to integrate this with other Azure backend solutions like IoT Hub and IoT Central. 

## Notes from Chirpstack Docker Example

**Notes:** I've added a `/chirpstack-docker` folder to keep my docker compose and configuration information. I'm keeping parameter values and configuration values outside of this project. 

I want this to be parameter-driven, so I'm focused on using the `docker-compose-env.yml`, but I'm just naming mine `docker-compose.yml`

## Azure Services

You can create a complete setup of Chirpstack on a single VM. However, this isn't ideal for a production deployment. To build out a production level system, I want to build out all the various systems on Azure.

* **IoT Hub** is used to connect the LoRa gateway with Azure.
* **Service Bus** is used for messaging between IoT Hub and ChirpStack Network Server (uplink).
* **PostgreSQL** is the hosted database server for the two databases.
* **Cache for Redis** is used for the hosted Redis solution.
* **Virtual Machine** is used for hosting the ChirpStack stack

The goal is to Use IoT Central, as well, but for now I'm focused on getting IoT working. 

---
Simulation: To create simulation devices for this set up, I'll use the [Chirpstack Simulator](https://github.com/brocaar/chirpstack-simulator)

---
## Create Service Bus
One of the more complex pieces is the Service Bus. We need to create:

--Namespace
--Basic pricing tier
--Location
