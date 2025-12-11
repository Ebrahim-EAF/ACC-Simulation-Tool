[README.md](https://github.com/user-attachments/files/24091614/README.md)
Adaptive Cruise Control (ACC) – ECE515/SE522 Demo

This repository contains the implementation of an Adaptive Cruise Control (ACC) educational tool developed for UIUC ECE515/SE522 (Control System Theory & Design).
The tool allows users to:

* Run simulations of ego/lead vehicle dynamics

* Interactively explore ACC behaviour (speed mode & distance mode)

* Visualize velocity, distance, and acceleration profiles

* View the state-space representation, controllability, observability, and closed-loop eigenvalues

* Adjust ACC parameters, including the actuator time constant τ

The goal is to provide an intuitive demonstration of linear, nonlinear, mode-switching systems control under safety constraints.

Project Structure:

src/
└── ccsd/

    ├── ACC_Calc.py                         # Full ACC simulation engine (nonlinear, piecewise)
    ├── acc_server.py                       # Flask server handling API + analysis
    ├── main.py                             # Maestro orchestrating ACC, analysis, GUI data
    ├── Controllability_Calc.py             # Computes controllability matrix & rank
    ├── Observability_Calc.py               # Computes observability matrix & rank
    ├── Stability_Calc.py                   # Computes eigenvalues, stability
    ├── Detectability_Stabilizibility_Calc.py # Detectability / stabilizability checks
    ├── Data_Center.py                      # Shared datastore for GUI/server communication
    ├── Start-GUI.html                      # Frontend GUI (ACC dashboard + plots + math)

Features: 

* Nonlinear ACC with speed/distance mode switching

* Smooth acceleration behaviour using hysteresis + dwell time

* Dynamic safe-distance computation

* Customizable actuator time constant τ

* Lead-vehicle acceleration profiles (sine, sawtooth, step)

* Visualization via Chart.js

* Automatic updates (no need to press “Send config”)

* Structural analysis:

  *   Open-loop system matrices

  *   Closed-loop matrices for speed & distance modes

  *   Controllability / Observability

  *   Stability / eigenvalues

Running The Demo:

1-  Install dependencies

    pip install flask numpy

2- Start the backend server

inside the project root:

    python src/ccsd/acc_server.py

You should see:

    Running on http://127.0.0.1:5000

3- Open the GUI

Open in any web browser (or simply click on link in step 2 above):

    src/ccsd/Start-GUI.html

The GUI communicates with the backend automatically.


Documentation:

A full LaTeX technical manual (state-space modelling, ACC logic, switching behaviour, stability analysis, and educational notes) is provided in:

    docs/ACC_Manual.pdf

License
Educational use only (UIUC ECE515/SE522)

