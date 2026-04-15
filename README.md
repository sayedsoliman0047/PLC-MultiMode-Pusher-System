# PLC-MultiMode-Pusher-System
# Multi-Mode Industrial Pusher & Sorting System (TIA Portal & Factory I/O)

## 📌 Project Overview
This project demonstrates a flexible industrial automation system featuring a conveyor, pneumatic pusher, and a 3-position selector switch.  

The system supports multiple operation modes, allowing dynamic control strategies ranging from manual operation to fully automated sorting based on real-time sensor feedback.

---

## 🛠️ Technologies Used
- **PLC Programming:** Siemens TIA Portal (S7-1200)
- **Simulation:** Factory I/O
- **PLC Simulation:** Siemens S7-PLCSIM
- **Programming Language:** Ladder Diagram (LAD)

---

## ⚙️ Operating Modes
The system behavior is controlled using a **3-position selector switch**:

- **Mode 1 (State 1): Manual / Local Control**
  - Direct control over conveyor and pusher
  - Used for testing and troubleshooting

- **Mode 2 (Neutral State): Idle / Safe Mode**
  - System remains inactive
  - Ensures safe transitions between modes

- **Mode 3 (State 2): Automatic Mode**
  - Fully automated sorting process
  - Uses diffuse sensors to trigger pusher operations

---

## 🧠 Control Logic Highlights
The control logic is designed using industrial-grade practices:

- **State-Based Logic:**
  - Selector switch determines system behavior using dedicated state bits

- **Pusher Sequence Control:**
  - Activated based on sensor detection (%I0.6, %I0.7)
  - Controlled via output (%Q0.1)

- **Position Feedback System:**
  - Back Limit (%I0.4) and Front Limit (%I0.5)
  - Ensures safe and complete pusher cycles

- **Safety Interlocks:**
  - NC Stop button priority
  - Prevents actuation if unsafe conditions are detected

---

## 🔌 I/O Configuration

| Inputs (Sensors)        | Address | Outputs (Actuators)      | Address |
|------------------------|--------|--------------------------|--------|
| Start Button           | %I0.0  | Conveyor Belt (4m)       | %Q0.0  |
| Stop Button            | %I0.1  | Pusher (Extend)          | %Q0.1  |
| Selector State 1       | %I0.2  | Start Indicator Light    | %Q0.2  |
| Selector State 2       | %I0.3  | Stop Indicator Light     | %Q0.3  |
| Pusher Back Limit      | %I0.4  |                          |        |
| Pusher Front Limit     | %I0.5  |                          |        |
| Diffuse Sensors (1/2)  | %I0.6/7|                          |        |

---

## 📸 Project Preview

### 🔹 Driver & I/O Configuration
![Driver Setup](0.jpg)

### 🔹 Ladder Logic Implementation
![Network 1-2](1.png)  
![Network 3](2.png)

### 🔹 Factory I/O Scene
![Factory Scene](factory_scene.jpg)

---

## 🎥 Demo Video
👉 [Watch the system in action](PUT_YOUR_VIDEO_LINK_HERE)

---

## 📂 Project Files Included
- TIA Portal Project File  
- Factory I/O Scene File  
- PLC Logic Screenshots  
- Full Simulation Video  

---

## 🚀 How to Run the Project
1. Open the project in **TIA Portal**
2. Start **S7-PLCSIM**
3. Open the scene in **Factory I/O**
4. Connect using `S7-PLCSIM Driver` (ensure status is green)
5. Select operation mode using the **Selector Switch**
6. Press **Start** to run the system

---

## 💡 Engineering Notes
- System designed with modular and scalable logic structure  
- Clear separation between manual and automatic control paths  
- Reliable operation ensured using feedback-based actuation  
- Suitable for real industrial adaptation with minor modifications  
