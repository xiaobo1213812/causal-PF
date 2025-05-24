# From Causal Graphs to Problem Diagrams: Enhancing Safety Requirement Modeling with LLMs
## :blush: Declaration
This repository contains a summary overview of this paper, as well as 

1.The table of the basic causal graphs details of the GPS system.

2.The table between causal graph Variables and problem diagram domain in GPS system.

3.The table between causal graph relationship and problem diagram shared phenomena in GPS system.

4.The ‘json’ code for the problem diagram.

## 📄Overview
🔍Objective: The purpose of this study is to integrate causal graph into the Problem Frames (PF) to enhance the semantic expressiveness and interpretability of PF,  and utilize Large Language Models (LLMs) to assist engineers in efficiently and accurately extracting causal relationships.

💡Method: In this paper, we propose a causally enhanced PF modelling approach. Firstly, a multi-stage LLM prompting strategy is designed to extract six types of structured causal graphs from natural language requirements and combined with artificial calibration to eliminate semantic ambiguity. Secondly, the mapping rules of causal graphs to problem diagrams are proposed, and the causal logic is embedded into PF as a semantic support layer to explicitly express the interaction of safety requirements between hardware-software-environment. Finally, a multi-rotor UAV GPS system is taken as an example to verify the feasibility of the method to generate fine-grained safety requirements.

✒Contribution:

1) Proposing a causality extraction method combining LLM and manual calibration, and constructing semantically clear causal graphs with six types of causality.
   
2) Establishing a mapping mechanism from causal graphs to problem diagrams, and realising the integration of causal reasoning and formal modelling.
   
3) For the first time, using causal graphs as a semantic support layer for problem diagrams, to enhance their interpretability and value for engineering applications.
   
4) The feasibility of the method for fault analysis and safety analysis in complex systems is verified through practical examples.

## 💭Data

### 📊The table of the basic causal graphs details of the GPS system.

| **Causality**               | **Shared phenomena**       | **Description**                                                                 |
|-------------------------|-----------------------|-------------------------------------------------------------------------------------------------------------------|
| Antenna → GPS System | Cause | Antenna damage directly cause GPS cannot resolve data.|
| Antenna → Signal Quality Assessment System | Cause   | Antenna damage directly cause the evaluation module to misjudge the signal state.                      |
| Antenna → Data Parsing System  | Cause       | Antenna damage directly causes the resolver module output position to drift or jump. |
| Signal Cable → GPS System | Cause      |  Poor or broken signal Cable directly causes the GPS module to drop out intermittently.            |
| Signal Cable → Signal Quality Assessment System  | Cause | Signal Cable noise introduction directly causes the evaluation module to misjudge the evaluation result. |
| Signal Cable → Data Parsing System | Cause |  Signal Cable damage directly causes the output position of the resolution module to jump or lose points.                  |
|Power → GPS System |Trigger |Unstable power supply immediately triggers to GPS chip reboot or failure. |
|Power → Clock Synchronization System    |Trigger| Abnormal power supply voltage immediately triggers clock drift leading to synchronisation failure.        |
|Power → Flight controller |Trigger|Power supply dropout immediately triggers flight control interruption.           |
|Power → Accelerometer | Trigger| Insufficient power supply power supply immediately triggers to acceleration failure. |
|Power → Gyro|Trigger| Insufficient power supply power supply immediately triggers to gyroscope drift.                            |
|Power → Data Parsing System|Cause| Power supply instability directly causes data resolution error.|
|Power → Redundancy and Switching Logic System |Cause |Unstable power supply directly causes failure to switch between primary and backup systems.                   |
|Power → Driver|Trigger| Unstable power supply immediately triggers to driver failure.                                       |
|Shielding Measures → GPS System |Scenario Constraints|When shielding is poor, it leads to the system to misjudge signal blindness; When shielding is excessive, it leads to failure to receive signals.     |
| Shielding Measures → Signal Quality Assessment System |Scenario Constraints|When poorly masked, it leads to parsing the wrong coordinates; When over-masked, it leads to receiving the coordinates.        |
