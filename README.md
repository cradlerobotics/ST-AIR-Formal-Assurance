ST-AIR Formal Assurance Artefacts

This repository contains the formal models and property specifications developed for the Subterranean Tunnel Autonomous Inspection Robot (ST-AIR) case study, as presented in the FormaliSE 2026 paper:
Model-Driven Assurance for Robotic Controllers:
A Subterranean Tunnel Inspection Case Study

The artefacts support design-time assurance of supervisory mission and safety control logic, using a model-driven workflow based on RoboChart, RoboCert, and FDR.


ST-AIR-Formal-Assurance/

├── models/

│   ├── ST_AIR.rct

│   ├── SafetySM.rct

│   ├── MissionData.rct

│   ├── MissionHoldObserver.rct

│   ├── ST_AIR_Integrated.rct

│   └── Definitions.rct

│

├── properties/

│   └── requirements.rcert
│


├── README.md


└── .gitignore


models/
Contains the RoboChart (.rct) models defining the supervisory control logic for ST-AIR, including:

--Safety supervisory logic (hazard detection and mitigation),

--Mission supervisory logic (navigation, visibility, logging),

--Hold/observer logic enforcing safety–mission precedence,

--Integrated harness models used for compositional verification.


These models abstract away low-level sensing, actuation, and continuous dynamics, focusing instead on discrete, hazard-driven decision-making at the architectural level.

properties/
Contains RoboCert (.rcert) specifications formalising the behavioural requirements derived from hazard analysis.
The properties are expressed as sequence-based assertions over observable interactions and capture:

--hazard detection and mitigation,

--safety-mission precedence,

--blocking of mission commands under safety holds,

--recovery and abort behaviour.


All properties are verified against the models using trace refinement checking. 

*********************************************************************************************************************************

Toolchain and Requirements

The artefacts are intended to be used with the RoboStar toolchain:

--RoboTool (Eclipse-based modelling environment)
--RoboChart – modelling language for robotic controllers
--RoboCert – property specification language
--FDR – Failures–Divergence Refinement model checker

Required Software

--RoboTool (with RoboChart and RoboCert support)
--FDR4

Installation instructions and binaries are available from:

https://robostar.cs.york.ac.uk/

https://www.cs.ox.ac.uk/projects/fdr/


*********************************************************************************************************************************

How to Run the Verification

1. Open RoboTool and import this repository as an Eclipse project.

2. Load the .rct models from the models/ directory.

3. Load the RoboCert specifications from properties/requirements.rcert.

4. Use RoboTool to generate CSP and invoke FDR.

4. Verify that all assertions hold in the traces model.

All properties reported in the paper were discharged automatically, without manual intervention.

*********************************************************************************************************************************

Scope and Limitations

These artefacts support design-time assurance of supervisory control logic.
They intentionally abstract from:

--continuous control dynamics,
--sensor noise and timing jitter,
--probabilistic or quantitative performance measures.

The focus is on worst-case behavioural correctness of hazard mitigation and mission coordination logic. Probabilistic and runtime extensions are discussed as future work in the paper.

*********************************************************************************************************************************

Industrial Context

The ST-AIR case study is industrially inspired, grounded in domain knowledge from multiple real-world subterranean tunnel inspection projects contributed by industrial partners.

To respect commercial sensitivity, the models represent a representative and anonymised abstraction of current practice, rather than a digital replica of any single deployed system.


*********************************************************************************************************************************
Contact

For questions about the artefacts or the case study, please contact:

Yasmeen Rafiq
University of Manchester
CRADLE Project



*********************************************************************************************************************************
Reference

These artefacts accompany the following paper, accepted for publication at **FormaliSE 2026**:

Model-Driven Assurance for Robotic Controllers:  A Subterranean Tunnel Inspection Case Study 
Yasmeen Rafiq et al.  
To appear in: FormaliSE 2026 (co-located with ICSE 2026)

A full citation will be added once the final camera-ready version is published.
