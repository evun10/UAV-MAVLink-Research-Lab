# UAV-MAVLink-Research-Lab
SITL (Software in the Loop) environment for testing MAVLink protocol vulnerabilities.
# UAV MAVLink Security Research Sandbox 🚁

### Project Overview
This project establishes a **Software-in-the-Loop (SITL)** research environment to analyze vulnerabilities in the MAVLink protocol used by autonomous aerial systems. The goal is to demonstrate how unencrypted telemetry data can be intercepted and manipulated in a controlled environment.

**Status:** 🟢 Active (Phase 1: Environment Build)

### 🛠 Technical Stack
* **OS:** Fedora Linux 42 (Workstation)
* **Autopilot:** ArduPilot (Copter 4.7-dev) compiled from source
* **Protocol:** MAVLink v2
* **Ground Station:** MAVProxy / Mission Planner
* **Language:** Python 3, Bash, C++

### ⚙️ Installation & Setup
*Documenting the build process for Fedora Linux:*

```bash
# 1. Install Dependencies
sudo dnf groupinstall "Development Tools" -y
sudo dnf install python3-pip python3-devel python3-wxPython python3-opencv -y

# 2. Clone ArduPilot
git clone --recursive [https://github.com/ArduPilot/ardupilot.git](https://github.com/ArduPilot/ardupilot.git)
cd ardupilot

# 3. Install Environment Scripts
Tools/environment_install/install-prereqs-fedora.sh -y

# 4. Launch Simulation
cd ArduCopter
../Tools/autotest/sim_vehicle.py -w
