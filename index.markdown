---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: single
---

<div style="text-align: center;">
  <h1>Robotic System for Chemical Experiment Automation with Dual Demonstration of End-effector and Jig Operations</h1>
  <p>
    Hikaru Sasaki, Naoto Komeno, Takumi Hachimine, Kei Takahashi, Yu-ya Ohnishi, Tetsunori Sugawara,
    Araki Wakiuchi, Miho Hatanaka, Tomoyuki Miyao, Hiroharu Ajiro, Mikiya Fujii, and Takamitsu Matsubara
  </p>
  [<a href="https://arxiv.org/abs/2506.11384" target="_blank" rel="noopener">arXiv</a>]
</div>




## abstact
<div class="notice--primary">
While robotic automation has demonstrated remarkable performance, such as executing hundreds of experiments continuously over several days, designing synchronized motions between the robot and experimental jigs remains challenging, especially for flexible experimental automation.
This challenge stems from the fact that even minor changes in experimental conditions often require extensive reprogramming of both robot motions and jig control commands.
Previous systems lack the flexibility to accommodate frequent updates, limiting their practical utility in actual laboratories.
To update robotic automation systems flexibly by chemists, we propose a concept that enables the automation of experiments by utilizing dual demonstrations of robot motions and jig operations by chemists.
To verify this concept, we developed a chemical-experiment-automation system consisting of jigs to assist the robot in experiments, a motion-demonstration interface, a jig-control interface, and a mobile manipulator.
We validate the concept through polymer-synthesis experiments, focusing on critical liquid-handling tasks such as pipetting and dilution.
The experimental results indicate high reproducibility of the demonstrated motions and robust task-success rates.
This comprehensive concept not only simplifies the robot programming process for chemists but also provides a flexible and efficient solution to accommodate a wide range of experimental conditions, providing a practical framework for intuitive and adaptable robotic laboratory automation.
</div>


---

## Overview
This paper proposes a dual demonstration-based robotic system for automating chemical experiments. Instead of manually programming robot motions and jig operations, chemists demonstrate the actions using an intuitive interface and jig controller. The robot then reproduces the task precisely, streamlining automation for complex lab workflows.
Concept of dual demonstration: (a) chemist demonstrates using the interface and jigs, (b) robot executes the task.


<figure style="text-align: center;">
  <div style="display: flex; gap: 20px; justify-content: center;">
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/concept_demo.png' | relative_url }}" alt="Image 1" width="300">
      <div style="font-size: 0.9em; margin-top: 5px;">(a) Demonstration</div>
    </div>
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/concept_exec.png' | relative_url }}" alt="Image 2" width="300">
      <div style="font-size: 0.9em; margin-top: 5px;">(b) Execution</div>
    </div>
  </div>
  <div style="font-size: 0.9em; margin-top: 5px;">Fig. 1: Proposed concept of dual demonstration of end-effector and jig operations for robotic-laboratory automation. (a) The system during a demonstration. A chemist conducts an experiment using jigs through a motion-demonstration interface. (b) The system is in execution. Mobile manipulator executes an experiment on a demonstration. </div>
</figure>

---

## System Architecture

The developed system integrates four main components:
- A motion-demonstration interface that mimics the robot's gripper
- Specialized experimental jigs for tasks such as pipetting and bottle handling
- A mobile manipulator (UR5e on MiR200)
- A motion-capture system for recording demonstrations
The demonstration phase and execution phase are connected through a time-synchronized data logging and control pipeline.
System overview is shown in Fig. 4.

<figure style="text-align: center;">
  <div style="display: flex; gap: 20px; justify-content: center;">
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/robot_system_demo.png' | relative_url }}" alt="Image 1" width="300">
      <div style="font-size: 0.9em; margin-top: 5px;">(a) Demonstration</div>
    </div>
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/robot_system_exe.png' | relative_url }}" alt="Image 2" width="300">
      <div style="font-size: 0.9em; margin-top: 5px;">(b) Execution</div>
    </div>
  </div>
  <div style="font-size: 0.9em; margin-top: 5px;"> Fig. 4: Overview of developed chemical-experiment-automation system. (a) Demonstration phase. Demonstrator conducts an experiment using a demonstration interface and jigs, and the interface's motions are collected using a motion-capture system. (b) Execution phase. Mobile manipulator executes an experiment based on a demonstration.</div>
</figure>


---

## Experiments 

### Settings
To validate the system, a simulated polymer synthesis workflow was designed. It consisted of three workspaces:
- Polymer sampling
- Bottle manipulation for dilution
- Pipetting operation

To evaluate the proposed dual demonstration system, we conducted a full-cycle experiment simulating a polymer synthesis workflow.
In each task, a chemsit demonstrated a motion once and then the motions are autonomously executed by the mobile manipulator.
Experimental environment layout with three workstations (Fig. 18).

<figure style="text-align: center;">
  <div style="display: flex; gap: 20px; justify-content: center;">
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/robot_exp_env2.png' | relative_url }}" alt="Image 1" width="300">
      <div style="font-size: 0.9em; margin-top: 5px;">(a)</div>
    </div>
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/pipetting_env.png' | relative_url }}" alt="Image 2" width="300">
      <div style="font-size: 0.9em; margin-top: 5px;">(b)</div>
    </div>
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/polymerization_env.png' | relative_url }}" alt="Image 2" width="300">
      <div style="font-size: 0.9em; margin-top: 5px;">(c)</div>
    </div>
  </div>
  <div style="font-size: 0.9em; margin-top: 5px;"> Fig. 18: Overview of experimental environment. (a) Layout of the experimental system with three designated workspaces: polymer sampling, bottle manipulation, and pipetting. (b) Environment for bottle manipulation and pipetting. (c) Environment for polymer sampling.  </div>
</figure>


### Results
The robot performed all actions based on a single human demonstration, including bottle manipulation, polymer sampling, and dilution.
The results confirm the system's precision, synchronization, and reliability across complex, multi-step tasks.

#### Task 1: Polymer Sampling
At Workspace 1, the robot:
- Retrieves a bottle from the case
- Opens the cap
- Samples polymer (colored water)
- Closes the cap and returns the bottle

Robot-executed actions for polymer sampling.

<figure style="text-align: center;">
  <div style="display: flex; gap: 20px; justify-content: center;">
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/robot_exp_sampling2.png' | relative_url }}" alt="Image 2" width="300">
    </div>
  </div>
  <div style="font-size: 0.9em; margin-top: 5px;"> Fig. 19: Robot-executed motion for sampling on workspace 1</div>
</figure>


#### Task 2: Bottle Manipulation for Dilution
At Workspace 2, the robot:
- Places the bottles for dilution
- Opens the lids
- Moves bottles onto the balance for precise pipetting

Bottle manipulation task for dilution setup.


<figure style="text-align: center;">
  <div style="display: flex; gap: 20px; justify-content: center;">
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/robot_exp_bottle2.png' | relative_url }}" alt="Image 2" width="300">
    </div>
  </div>
  <div style="font-size: 0.9em; margin-top: 5px;">
    Fig. 20: Robot-executed motion for bottle manipulation on workspace 2
  </div>
</figure>


#### Task 3: Pipetting for Dilution
At Workspace 3, the robot:
- Picks up small and large pipettes
- Aspirates and dispenses polymer and solvent
- Returns pipettes and closes bottle lids

<figure style="text-align: center;">
  <div style="display: flex; gap: 20px; justify-content: center;">
    <div style="text-align: center;">
      <img src="{{ '/assets/figure/robot_exp_pipette2.png' | relative_url }}" alt="Image 2" width="300">
    </div>
  </div>
  <div style="font-size: 0.9em; margin-top: 5px;">
    Fig. 21: Robot-executed motion for pipetting on workspace 3
  </div>
</figure>
	
#### Summary of Results
- 100% task success rate over all trials
- High reproducibility of human-demonstrated motions
- Accurate pipetting volumes, with low deviation from targets

This system shows that complex chemical procedures can be automated without manual programming, making robotic lab automation more accessible to chemists without robotics expertise.

---

## Open-Source Resources
To promote reproducibility and facilitate future research, we provide open-source implementations of both the hardware designs and software components used in our system.

### Software
GitHub Repository – Robot Automation System

###  Hardware Design
We provide 3D CAD files and mechanical design specifications for all jigs.

[<a href="https://drive.google.com/drive/folders/1MhjS7Oeb_IeSksfQzN8WtS2Ldvuo__-u?usp=sharing" target="_blank" rel="noopener">Hardware Design Files</a>]

All parts were designed using Fusion 360 and printed with a FLASHFORGE Creator3 Pro using PLA filament.


