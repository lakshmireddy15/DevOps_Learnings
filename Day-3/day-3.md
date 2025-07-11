# 🖥️ Virtual Machine

There are a lot of servers we have created, but we haven't used 100% of CPU and RAM.  
Here, a lot of data is wasted, so this is called **inefficiency**.

With the concept of **virtualization**, we install a **hypervisor**.

- **Hypervisor** is a software that can be installed on a physical machine (not inside the VM).
- Here we can do **logical isolation**.
- In AWS, you don’t see the physical machine, but behind the scenes
- We add **efficiency** using the hypervisor by logically separating resources.
- There is **no dependency** between all VMs — every VM has its own CPU, RAM, and all other components.

---

# 🐧 LINUX OS

**Operating System** means it is the **bridge between software and hardware components**.

### Example:

When we use a program (browser or any app), it doesn't talk to hardware components like CPU, memory, or disk directly.  
Instead, it uses the **Operating System (OS)**.


---

## 🔧 Key components between software and hardware:

### ✅ System Software
- Software that runs the system and helps work with hardware (e.g., **libraries**, **drivers**)

### ✅ User Process
- A program started by the user (e.g., **Chrome**, **a Python script**, etc.)

### ✅ System Libraries

- Ready-made code that both apps and the OS can use (e.g., **math functions**, **file handling**)
- System libraries are responsible for performing tasks like calculations, file handling, etc., so that applications don't have to write those from scratch.


### ✅ Kernel
- This is the **main part of the OS** that talks to hardware and controls everything.
- Kernel is responsible for communication between software and hardware.

#### Kernel Responsibilities:
- Device Management  
- Memory Management  
- Process Management  
- Handling Management  

### ✅ OS
- Software that **manages hardware** and lets applications run.

---
# 🖥️ Physical Machine vs Virtual Machine

## What is a Physical Machine?
- A **physical machine** is a real, tangible computer or server.
- It contains actual **hardware components** such as:
  - **CPU (Central Processing Unit)**
  - **RAM (Memory)**
  - **Storage** (Hard disk or SSD)
  - **Network interfaces** (LAN/Wi-Fi)
- Requires **physical access** for:
  - Maintenance
  - Hardware upgrades
  - Troubleshooting
- **Example:** Personal desktop computer, on-premise server.

---

## 💻 What is a Virtual Machine (VM)?
- A **virtual machine** is a software-based emulation of a computer.
- It runs on a **physical machine** using a **hypervisor** (e.g., VMware, VirtualBox, KVM).
- Allows **multiple VMs to run on a single physical server**.
- Each VM has:
  - Its own virtual CPU
  - Virtual RAM
  - Virtual storage
  - Separate operating system (OS)
- Provides **isolation**: Each VM operates independently.
- Common uses:
  - **Cloud platforms** (AWS, Azure, GCP)
  - **Development and testing**
  - **Running different operating systems**

---

# 🧩 Hardware and Software Components

## 🔧 Hardware Components
These are the **physical parts** of a computer system:
- **CPU** – Central Processing Unit
- **RAM** – Random Access Memory
- **Input devices** – Mouse, keyboard, microphone
- **Output devices** – Monitor, printer, speakers
- **Storage devices** – Hard drive, SSD

## 💾 Software Components
- Software is a **collection of instructions and data** that tells the hardware what to do.
- Types of software:
  - **Operating System** (e.g., Windows, Linux, macOS)
  - **Application Software** (e.g., browsers, games, text editors)
  - **Device Drivers** (to control hardware devices)

---



## 🔄 System Architecture

[User Process / App]
↓
[System Libraries]
↓
[Operating System]
↳ Shell / UI (what you see)
↳ Kernel (core manager)
↳ Drivers (to talk to devices)
↓
[Hardware]
