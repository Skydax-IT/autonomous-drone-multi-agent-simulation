# Autonomous Drone Multi-Agent Simulation

A **3D autonomous drone simulation** built with **SARL**, **Microsoft AirSim** and **Unreal Engine**.

The project implements a **multi-agent system (MAS)** in which autonomous drone agents interact with a simulated 3D environment through AirSim.

## Overview

The objective of this project was to explore the use of **agent-oriented programming** for autonomous systems.

Drone behaviors are implemented using **SARL agents** and executed with the **Janus runtime**, while **Microsoft AirSim** provides the interface with drones simulated inside an **Unreal Engine 4** environment.

The project also integrates a JVM-compatible AirSim API to allow communication between the SARL application and the simulator.

## Tech Stack

* **SARL 0.10.1** — agent-oriented programming
* **Janus** — multi-agent runtime
* **Java / JDK 11**
* **Maven** — dependency and project management
* **Microsoft AirSim** — drone simulation
* **Unreal Engine 4.25** — 3D simulation environment
* **Kotlin / JVM AirSim API** — communication layer between the agents and AirSim

## Architecture

```text
SARL Agents
     │
     ▼
Janus Runtime
     │
     ▼
AirSim JVM API
     │
     ▼
Microsoft AirSim
     │
     ▼
Unreal Engine 4.25
```

This architecture separates the **agent behavior layer** from the **physical simulation layer**, allowing autonomous logic to be developed independently from the Unreal Engine environment.

## Repository Structure

```text
.
├── src/main/sarl/          # SARL agents and simulation logic
├── src/main/resources/     # Application resources
├── Project Reports/        # Academic project documentation
├── MultirotorClient.kt     # AirSim JVM API adaptation
├── RpcLibAdaptorsBase.kt   # AirSim RPC adaptation
├── executable.jar          # Pre-built application
└── pom.xml                 # Maven configuration
```

## Getting Started

### Prerequisites

The project was developed with the following environment:

* **JDK 11**
* **SARL 0.10.1**
* **Unreal Engine 4.25**
* **Microsoft AirSim**
* **Maven**
* A compatible AirSim environment such as the default **Blocks** environment

> This is an academic project built against these specific dependency versions. Newer versions of SARL, AirSim or Unreal Engine may require additional changes.

### 1. Configure AirSim

Install Microsoft AirSim and configure an Unreal Engine 4.25 environment.

The default AirSim **Blocks** environment can be used for testing.

Start the Unreal/AirSim simulation before launching the multi-agent application.

### 2. Install the AirSim JVM API

Clone the JVM API used by the project:

```bash
git clone https://github.com/alexandrelombard/airsim-jvm-api.git
```

Copy the following files from this repository:

```text
MultirotorClient.kt
RpcLibAdaptorsBase.kt
```

into:

```text
airsim-jvm-api/src/main/kotlin/fr/utbm/airsim/api/
```

Then build and install the library:

```bash
./gradlew build install
```

On Windows:

```bash
gradlew.bat build install
```

### 3. Import the SARL Project

Import this repository into the **SARL IDE** as a:

```text
SARL Maven Project
```

If dependencies are not resolved correctly, force a Maven project update.

### 4. Run the Simulation

Once the Unreal Engine environment and AirSim are running, the pre-built application can be launched with:

```bash
java -jar executable.jar
```

Alternatively, the project can be built and executed directly from the SARL development environment.

## Academic Context

**Institution:** UTBM — University of Technology of Belfort-Montbéliard
**Course:** IA51 — Multi-Agent Systems
**Semester:** Spring 2020

The project was developed as an introduction to **multi-agent systems, autonomous behaviors and distributed agent-based simulation** applied to drones.

## Authors

* **M003T
* **Skydax-IT**
* **Tyriaax**

## Acknowledgements

Special thanks to **Alexandre Lombard** for his work on the JVM integration with Microsoft AirSim.

## Project Status

This repository is preserved as an **academic project and technical demonstration**. It reflects the software ecosystem and dependency versions used during its development in 2020.

