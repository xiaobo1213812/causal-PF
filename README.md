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
