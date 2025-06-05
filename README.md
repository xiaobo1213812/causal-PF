# From Causal Graphs to Problem Diagrams: Enhancing Safety Requirement Modeling with LLMs
## :blush: Declaration
This repository contains a summary overview of this paper, as well as 

1.The table of the basic causal graphs details of the GPS system.

2.The table between causal graph Variables and problem diagram domain in GPS system.

3.The table between causal graph relationship and problem diagram shared phenomena in GPS system.

4.The ‘json’ code for the problem diagram.

5.The detailed data of the two groups of problem diagrams.

## 📄Overview
🔍Objective: The purpose of this study is to integrate causal graph into the Problem Frames (PF) to enhance the semantic expressiveness and interpretability of PF,  and utilize Large Language Models (LLMs) to assist engineers in efficiently and accurately extracting causal relationships.

💡Method: In this paper, we propose a causally enhanced PF modelling approach. Firstly, a multi-stage LLM prompting strategy is designed to extract five variations of causality to structure causal graphs from natural language requirements and combined with artificial calibration to eliminate semantic ambiguity. Secondly, the mapping rules of causal graphs to problem diagrams are proposed, and the causal logic is embedded into PF as a semantic support layer to explicitly express the interaction of safety requirements between hardware-software-environment. Finally, a multi-rotor UAV GPS system is taken as an example to verify the feasibility of the method to generate fine-grained safety requirements.

✒Contribution:

1) Proposing a causality extraction method combining LLM and manual calibration, and constructing semantically clear causal graphs with five variations of causality.
   
2) Establishing a mapping mechanism from causal graphs to problem diagrams, and realising the integration of causal reasoning and formal modelling.
   
3) For the first time, using causal graphs as a semantic support layer for problem diagrams, to enhance their interpretability and value for engineering applications.
   
4) The feasibility of the method for fault analysis and safety analysis in complex systems is verified through practical examples.

## 💭Data

### 📊The table of the basic causal graphs details of the GPS system.

|ID| **Causality**               |
|-------------------------|-----------------------|
|1| Antenna damage→ GPS System |
| 2|Antenna damage→ Signal Quality Assessment System |
|3|Antenna damage→ Data Parsing System  | 
|4 |Signal Cable damage→ GPS System |
| 5|Signal Cable damage→ Signal Quality Assessment System  | 
| 6|Signal Cable damage→ Data Parsing System | 
|7|Power shortage→ GPS System |
|8|Power shortage→ Clock Synchronization System    |
|9|Power shortage→ Flight controller |
|10|Power shortage→ Accelerometer | 
|11|Power shortage→ Gyro|
|12|Power shortage→ Data Parsing System|
|13|Power shortage→ Redundancy and Switching Logic System |
|14|Power shortage→ Driver|                                      |
|15|Shielding Measures → GPS System |
|16| Shielding Measures → Signal Quality Assessment System |
|17|Accelerometer damage→ Flight controller|
|18|Gyro damage→ Flight controller|
|19|Driver failure→ Data Parsing System|
|20|Driver failure→ Flight controller|
|21|Driver failure→ Redundancy and Switching Logic System|
|22|Data Parsing System → Flight controller|
|23|Clock Synchronization System → Flight controller|
|24|Signal Quality Assessment System → Redundancy and Switching Logic System|
|25|Signal Quality Assessment System → Flight controller|
|26|Redundancy and Switching Logic System → Flight controller|
|27|Flight controller → Visual and Laser Ranging System|
|28|Visual and Laser Ranging System → Flight controller|
|29|Human factors → Driver|
|30|Human factors → Data Parsing System|
|31|Human factors → Redundancy and Switching Logic System|
|32|Human factors → Flight controller|
|33|Environmental factors → GPS System|
|34|Environmental factors → Signal Quality Assessment System|
|35|Environmental factors → Redundancy and Switching Logic System|
|36|Environmental factors → Flight controller|

### 🗞The table between causal graph Variables and problem diagram domain in GPS system.

| **causal graph Variables**               | **problem diagram domain**       |
|-------------------------|-----------------------|
| GPS System|Machine Domain|
|Data Parsing System |Designed Domain| 
|Signal Quality Assessment System  |Designed Domain|
|Shielding Measures | Designed Domain| 
|Clock Synchronization System|Designed Domain|
|Redundancy and Switching Logic System|Designed Domain|
|Driver|Designed Domain|
|Visual and Laser Ranging System|Designed Domain|
|Flight controller|Designed Domain|
|Signal Cable|Given Domain(X)|
|Antenna|Given Domain(X)|
|Gyro|Given Domain(X)|
|Accelerometer|Given Domain(X)|
|Power|Given Domain(C)|
|Environmental factors|Given Domain(C)|
|Human factors|Given Domain(B)|


### 📊 The table between causal graph relationship and problem diagram shared phenomena in GPS system.

| **Causality**               | **Variation**  |**Shared phenomena**       | **Description**                                                                 |
|------------------------|------------------------|-----------------------|-------------------------------------------------------------------------------------------------------------------|
| Antenna damage→ GPS System | ![image](https://github.com/user-attachments/assets/4320bcb3-0bfc-4093-a0dc-bff6315a1808) |Cause| Antenna damage directly cause GPS cannot resolve data.|
| Antenna damage→ Signal Quality Assessment System |![image](https://github.com/user-attachments/assets/df5c3162-2390-48db-b709-b98feda91253) |Cause   | Antenna damage directly cause the evaluation module to misjudge the signal state.                      |
| Antenna damage→ Data Parsing System  |![image](https://github.com/user-attachments/assets/3cb1fb63-1f75-4fbf-8464-4d0f6488056d) |Cause       | Antenna damage directly causes the resolver module output position to drift or jump. |
| Signal Cable damage→ GPS System | ![image](https://github.com/user-attachments/assets/e91b6e04-a10d-400e-b2c4-9698fe45bee5)|Cause      |  Poor or broken signal Cable directly causes the GPS module to drop out intermittently.            |
| Signal Cable damage→ Signal Quality Assessment System  |![image](https://github.com/user-attachments/assets/e68983bc-6e13-4aba-8bd4-e9cc29217d6b) |Cause | Signal Cable noise introduction directly causes the evaluation module to misjudge the evaluation result. |
| Signal Cable damage→ Data Parsing System | ![image](https://github.com/user-attachments/assets/73b9cd81-a24d-413c-b5c0-d7c1aab931a1)|Cause |  Signal Cable damage directly causes the output position of the resolution module to jump or lose points.                  |
|Power shortage→ GPS System |![image](https://github.com/user-attachments/assets/bc9da0c8-6193-4511-b70f-70e147c58e43)|Trigger |Unstable power supply immediately triggers to GPS chip reboot or failure. |
|Power shortage→ Clock Synchronization System   | ![image](https://github.com/user-attachments/assets/58d3136d-741d-45c4-a332-0b44ed14ce86)|Trigger| Abnormal power supply voltage immediately triggers clock drift leading to synchronisation failure.        |
|Power shortage→ Flight controller |![image](https://github.com/user-attachments/assets/0ae4414a-f82f-442d-a6d5-5230c36ff6d6)|Trigger|Power supply dropout immediately triggers flight control interruption.           |
|Power shortage→ Accelerometer| ![image](https://github.com/user-attachments/assets/0e833225-a7c3-4a16-a9bf-85ebd1914800)| Trigger| Insufficient power supply power supply immediately triggers to acceleration failure. |
|Power shortage→ Gyro|![image](https://github.com/user-attachments/assets/f4b456b2-e2b6-457e-86e1-28ca143033c9) |Trigger| Insufficient power supply power supply immediately triggers to gyroscope drift.                            |
|Power shortage→ Data Parsing System|![image](https://github.com/user-attachments/assets/61857b7c-84b8-4fd4-92c4-d05039dc0393) |Cause| Power supply instability directly causes data resolution error.|
|Power shortage→ Redundancy and Switching Logic System| ![image](https://github.com/user-attachments/assets/0ac91a53-fc89-4520-bf14-b604f3fcaaec)|Cause |Unstable power supply directly causes failure to switch between primary and backup systems.                   |
|Power shortage→ Driver|![image](https://github.com/user-attachments/assets/e50362e5-27f8-4096-8ef5-39b394639fd2) |Trigger| Unstable power supply immediately triggers to driver failure.                                       |
|Shielding Measures → GPS System|![image](https://github.com/user-attachments/assets/5967a414-3b6a-4152-aeb9-e87137fb1004) |Scenario Constraints|When shielding is poor, it leads to the system to misjudge signal blindness; When shielding is excessive, it leads to failure to receive signals.     |
| Shielding Measures → Signal Quality Assessment System|![image](https://github.com/user-attachments/assets/fa03f2a6-30f2-4dc0-ad9b-2bfe73670dd9)|Scenario Constraints|When poorly masked, it leads to parsing the wrong coordinates; When over-masked, it leads to receiving the coordinates.        |
|Accelerometer damage→ Flight controller|![image](https://github.com/user-attachments/assets/4995c857-cd9e-464c-8a85-d2699907bfc9) |Cause|Failure of the accelerometer axis directly causes to incorrect flight control commands.|
|Gyro damage→ Flight controller|![image](https://github.com/user-attachments/assets/9f30c1f3-725d-4391-bf49-cb4ec12e6609) |Cause|Failure of gyro directly causes to unstable flight or uncontrolled yaw.|
|Driver failure→ Data Parsing System|![image](https://github.com/user-attachments/assets/9d2c0828-f099-480a-8b91-fa604c7dc954)|Cause|Driver crash directly causes missing data or incorrect formatting of the parsing module.|
|Driver failure→ Flight controller|![image](https://github.com/user-attachments/assets/bb49da1a-9717-4209-bb9a-23d8873f3c2d) |Imply|Driver crash leads to sensor data loss, which leads to flight control decision errors.|
|Driver failure→ Redundancy and Switching Logic System|![image](https://github.com/user-attachments/assets/42a0c8df-891b-46ce-802d-ea809c02d4fa)|Cause|Driver crash directly causes redundancy and switching logic switching delays.|
|Data Parsing System → Flight controller|![image](https://github.com/user-attachments/assets/32b750b6-a972-40a9-9d81-4388b893ed69)|Imply|Data parsing module parsing error leads to positioning error, which leads to flight control navigation bias.|
|Clock Synchronization System → Flight controller|![image](https://github.com/user-attachments/assets/0baf8b53-828d-47ac-8355-b433b1b58131) |Trigger|Clock Synchronisation Module timestamps are messed up immediately triggering to incorrect trajectory calculation.|
|Signal Quality Assessment System → Redundancy and Switching Logic System|![image](https://github.com/user-attachments/assets/b23060d9-da46-4a2c-b6f6-57f54c3a6b2f) |Conflict|Signal Quality Assessment System and Redundancy and Switching Logic System are in conflict with each other, and the conflict between the two leads to GPS system failure.|
|Signal Quality Assessment System → Flight controller| ![image](https://github.com/user-attachments/assets/f1731dd8-93f8-47c6-88fd-ad99125522b6)|Imply|Wrong signal quality assessment leads to wrong positioning, which leads to abnormal flight control path planning.|
|Redundancy and Switching Logic System → Flight controller|![image](https://github.com/user-attachments/assets/357f13d3-af61-4f50-a90f-f64925a3bbec)|Imply|Confused redundancy and switching logic leads to positioning errors, which leads to abnormal flight control path planning.|
|Flight controller → Visual and Laser Ranging System|![image](https://github.com/user-attachments/assets/0d28720d-2c51-41ae-a8b7-bac88dd9d065) |Trigger|Flight controller command error immediately triggers range module operation.|
|Visual and Laser Ranging System → Flight controller|![image](https://github.com/user-attachments/assets/efa623fd-2ae9-4b98-b511-52b273dc4be5)|Imply|Vision/laser ranging error leads to wrong positioning data, which leads to flight controller problems.|
|Human factors → Driver|![image](https://github.com/user-attachments/assets/c8a79b87-cfe7-4482-bb18-9a462c07db64)|Cause|Human factor configuration error directly causes to abnormal driver driver parameters.|
|Human factors → Data Parsing System|![image](https://github.com/user-attachments/assets/d74565fc-ee15-422b-b8d2-e4f83d99864c)|Cause|Human factor improper maintenance directly causes to data parsing module firmware version conflict|
|Human factors → Redundancy and Switching Logic System|![image](https://github.com/user-attachments/assets/96d8bc76-fd03-4780-ab9b-d077a6ce4e8c)|Cause|Human factor setting error directly causes to redundancy not triggered as expected.|
|Human factors → Flight controller|![image](https://github.com/user-attachments/assets/f569066e-db86-4213-a675-435dd3ff978e)|Cause|Human factor misoperation directly causes uncontrolled manual intervention in flight control mode|
|Environmental factors → GPS System|![image](https://github.com/user-attachments/assets/b0d0e1a5-49f4-4c21-8d95-ad5387d69b21) |Scenario Constraints|When electromagnetic interference in environmental factors, Environmental factors lead to loss of satellite signals of GPS receiver module.|
|Environmental factors → Signal Quality Assessment System|![image](https://github.com/user-attachments/assets/806451e0-b25f-4ae9-b56d-fd4189c36d43) |Scenario Constraints|When the environmental factors in the extreme weather, environmental factors lead to signal quality assessment distortion.|
|Environmental factors → Redundancy and Switching Logic System|![image](https://github.com/user-attachments/assets/2ab0b268-0333-49a2-9c59-abee4373de56) |Scenario Constraints|When the environmental factors in extreme weather, environmental factors lead to redundancy system crash.|
|Environmental factors → Flight controller|![image](https://github.com/user-attachments/assets/92d085ba-3084-41d2-9f30-c40e474d5538) |Imply|Environmental factor strong wind interference leads to data processing error, which leads to flight controller attitude control overrun.|


### 🗞 The ‘json’ code for the problem diagram.
The ‘json’ code for the problem diagram is the file of "problem diagram. json".



### 🗞 The detailed data of the two groups of problem diagrams.
The data of problem diagrams is the file of "data.xls".
