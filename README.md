# Festo MPS Station Control Panel Programming Using Ladder Logic

## Overview
Development of the **Control Panel logic** for the *Festo MPS Sorting Station* using **Siemens TIA Portal** and **S7-1500 PLC**.  
This project focuses on programming the station’s control panel entirely in **Ladder Logic (LAD)** to manage manual/automatic operation modes and state transitions based on the control panel inputs.

<p align="center">
  <img src="https://github.com/user-attachments/assets/74da6927-5a5f-4ce1-8a6b-320cef0c41d9" width="1000" alt="Control Panel">
</p>

## Features

- Complete **control panel logic** implementation using Ladder Logic.  
- Handles **manual/automatic** mode switching, **start/stop/reset** operations, and LED indicators.  
- Systematic design using a **state machine** ro model the logic used in control panel.  
- Modular program using a **Function Block (FB)** with its own variable database.  
- Smooth integration into the main **OB1** block for runtime execution.  

## System Architecture

- **PLC Platform:** Siemens S7-1500  
- **Programming Environment:** Siemens TIA Portal (Step 7)  
- **Programming Language:** Ladder Logic (LAD)  
- **Main Components:**  
  - Start, Stop, and Reset buttons  
  - Manual/Auto key switch  
  - Indicator LEDs  

## Implementation Details

### Function Block: `controlPanel`
- Encapsulates all control panel logic.  
- Automatically generates an instance data block (`ControlPanel_DB`) containing all internal variables and states.  

### OB1 (Main Program)
- Imports `controlPanel` and executes it cyclically.  
- Handles input/output mapping and runtime execution.  

### Program Structure by Networks
- **Network 1:** Detects changes in Auto/Manual key switch position.  
- **Network 2:** Defines transition conditions between states (based on start, stop, and mode signals).  
- **Network 3:** Manages logic for entering specific states.  
- **Network 4:** Executes commands and outputs associated with each active state (e.g., LEDs, conveyors).  

## State Machine Overview
The control logic is designed according to the following **state machine**:
<p align="center">
  <img src="https://github.com/user-attachments/assets/f5603df8-80e9-46e9-bfce-e69cb0346a40" width="600" alt="State Machine Diagram">
</p>

### States and Transitions:
- **State 1:** Reset LED  
- **State 2:** Start LED  
- **State 3:** Manual Conveyor Operation  
- **State 4:** Automatic Conveyor Operation  

Key transitions handle mode changes, start/stop commands, and reset actions as illustrated in the diagram.

## Documentation
Official reference:  
🔗 [Festo MPS Sorting Station Documentation](https://ip.festo-didactic.com/Infoportal/MPS/Overview/EN/index.html)

## Program Structure
**1. Auto/Manual**
<p align="center"> 
  <img src="https://github.com/user-attachments/assets/aaae4946-b01b-4cae-9374-a5cdf4ec1bbc" width="600">
</p>

**2. Transitions**
<p align="center">
<img src="https://github.com/user-attachments/assets/3b28c0a9-162b-4f64-bd5e-3466ef15b162" width="600">
</p>

**3. States**
<p align="center">
<img src="https://github.com/user-attachments/assets/5183374e-1f90-4d24-ac29-7869fa23a01f" width="600">
</p>

**4. Commands**
<p align="center">
<img src="https://github.com/user-attachments/assets/76e69e21-6d09-4e0f-815b-7b2c23dafa66" width="600">
</p>

## Results
- Implemented a robust **state-based control system** using pure Ladder Logic.  
- Achieved reliable operation of manual and automatic modes via control panel inputs.  
- Validated proper state transitions and visual indicators based on real hardware tests.

**Demo Video**

<p align="center">
    <video src="https://github.com/user-attachments/assets/66cb3d59-c536-487b-8956-e95ed776789a" width="400" controls></video>

</p>

> *Click the image above to watch the demo video.*

## 📞 Contact
If you have any questions, feedback, or suggestions regarding this project, feel free to reach out:

- **Name:** Mark Lari  
- **Email:** [mark.lari.work@gmail.com](mailto:mark.lari.work@gmail.com)  
- **GitHub:** [AminLari](https://github.com/aminlari)

You are welcome to create issues or pull requests to improve this project. Contributions are highly appreciated!  
