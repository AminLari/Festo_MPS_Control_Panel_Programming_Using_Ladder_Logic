# Festo MPS Control Panel Automation (Ladder Logic)

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

## Results
- Implemented a robust **state-based control system** using pure Ladder Logic.  
- Achieved reliable operation of manual and automatic modes via control panel inputs.  
- Validated proper state transitions and visual indicators based on real hardware tests.

## Demo
<p align="center">
  <a href="https://www.youtube.com/watch?v=YOUR_VIDEO_ID" target="_blank">
    <img src="https://img.youtube.com/vi/YOUR_VIDEO_ID/0.jpg" 
         alt="Control Panel Ladder Logic Demo" 
         width="800">
  </a>
</p>

> *Click the image above to watch the demo video.*

## 📞 Contact
If you have any questions, feedback, or suggestions regarding this project, feel free to reach out:

- **Name:** Mark Lari  
- **Email:** [mark.lari.work@gmail.com](mailto:mark.lari.work@gmail.com)  
- **GitHub:** [AminLari](https://github.com/aminlari)

You are welcome to create issues or pull requests to improve this project. Contributions are highly appreciated!  
