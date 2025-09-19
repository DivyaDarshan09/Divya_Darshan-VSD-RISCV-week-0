# 🛠️ Task 2 - Tool Installation and Setup  

## 🌐 Oracle Virtual Machine  
Download Link: [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)  

---

## 🖥️ System Check  

| **Requirement** | **Specification** |
|------------------|--------------------|
| RAM              | 6 GB              |
| HDD              | 50 GB             |
| OS               | Ubuntu 20.04+     |
| CPU              | 4 vCPU            |

---

## 🎯 Objective  
To install and verify the essential tools required for the **RISC-V SoC Tapeout project**:  
- **Icarus Verilog (iverilog)**  
- **GTKWave**  
- **Yosys**  

---

## 1️⃣ Installing Icarus Verilog (iverilog)  

### 🔹 Installation Steps  
```bash
sudo apt-get update
sudo apt-get install iverilog
```
---
### 🔹 Terminal Output 
![alt text](<WhatsApp Image 2025-09-19 at 17.35.52_cb282210.jpg>)

## 2️⃣ Installing GTKWave  

### 🔹 Installation Steps  
```bash
sudo apt-get update
sudo apt install gtkwave 
```
---
### 🔹 Terminal Output
![alt text](<WhatsApp Image 2025-09-19 at 17.35.59_98968142.jpg>)

## 3️⃣ Installing Yosys  

### 🔹 Installation Steps  
```bash
$ sudo apt-get update
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys
$ sudo apt install make (If make is not installed please install it)
$ sudo apt-get install build-essential clang bison flex \
 libreadline-dev gawk tcl-dev libffi-dev git \
 graphviz xdot pkg-config python3 libboost-system-dev \
 libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
$ make
$ sudo make install 
```
---
### 🔹 Terminal Output
![alt text](<WhatsApp Image 2025-09-19 at 18.09.10_8b7fe480.jpg>)




## ✅ Outcome  
- Installed and verified: **Icarus Verilog**, **GTKWave**, and **Yosys**.  
- Tools are ready for **simulation, waveform analysis, and synthesis**.  
