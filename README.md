# Dynamic Analysis of Gough-Stewart Parallel Manipulators in a Serial Configuration

This repository contains the code, models, and documentation for my Bachelor's thesis project in Mechanical Engineering at the University of Tehran. The project focuses on the dynamic analysis of hyper-redundant hybrid serial-parallel robots based on the Gough-Stewart platform, configured in a stacked serial arrangement. These robots are inspired by natural structures like elephant trunks or octopus arms, offering high redundancy for applications in humanoid legs, robotic manipulators, and bio-inspired systems.

![Gough-Stewart](https://github.com/alirezakamali80/repository/Dynamic-Modeling-of-Hybrid-Robots/images/N3.jpg)
## My Bachelor Thesis Overview
- **Title**: Dynamic Analysis of Gough-Stewart Parallel Robots in Serial Configuration
- **Author**: Alireza Kamali Ardekani
- **Supervisors**:
  - Dr. Arash Bahrami (School of Mechanical Engineering, University of Tehran)
  - Dr. Mehdi Tale Masouleh (Human-Robot Interaction Laboratory, School of Electrical and Computer Engineering, University of Tehran)
- **Date**: Summer 2024 (1403 in Persian calendar)
- **Objective**: Develop a general dynamic model for an arbitrary number of serially stacked Gough-Stewart platforms using the principle of virtual work. This includes inverse kinematics, inverse dynamics, and validation against simulations.

The robot structure consists of multiple 6-DOF Gough-Stewart segments connected in series, each with 6 prismatic actuators (cylinder-piston pairs) and joints (universal-prismatic-spherical). The model accounts for fictitious wrenches to handle dynamics recursively from the end-effector to the base.

## Key Contributions
- **Kinematic Modeling**: Built upon prior work [5] for inverse kinematics and Jacobian matrices, relating task-space velocities to joint-space velocities. Updated relations for universal joints at the base instead of spherical ones.
- **Dynamic Modeling (Novelty)**: Derived inverse dynamics equations using the virtual work principle. The model is recursive, solving from the top segment downward, incorporating end-effector wrenches, cylinder/piston dynamics, and transferred wrenches between segments.
- **Validation**: Compared actuator forces from the analytical model against SimScape Multibody simulations for spiral and circular end-effector paths. Tested on robots with 2, 6, and 10 segments.
  - Minimum error: 0.00% (vertical motion, 2-segment robot)
  - Maximum error: 11.29% (circular motion, 10-segment robot)
  - Errors attributed to cumulative numerical derivatives, recursive solving, and end-effector motion effects.
- **Case Studies**: Analyzed forces in actuators for various configurations and motions.

## Methodology
1. **Inverse Kinematics**: Optimized using weighted Jacobian matrices to resolve redundancy.
2. **Inverse Dynamics**: Formulated as:
   \[
   \mathbf{f}_p = -{}^{p-1}\mathbf{J}_p^{-T} (\mathbf{W}'_{p,e} + \mathbf{W}'_{p,cyl} + \mathbf{W}'_{p,pis} + \mathbf{W}'_{p,Tr})
   \]
   Where \(\mathbf{f}_p\) are actuator forces for segment \(p\), and wrenches include end-effector, inertial, gravitational, and transferred terms.
3. **Simulation**: Used MATLAB/SimScape for multi-body dynamics verification.

## Results
- Derived a flexible equation of motion for any number of segments.
- Validated model shows good agreement with simulations, with errors increasing for more complex motions and higher redundancy.
- Published as a conference paper at the International Conference on Robotics and Mechatronics (ICROM 2024).

## Future Work
This work is part of ongoing research at the Human-Robot Interaction Lab (TaarLab):
- Kinematic sensitivity indices (Niusha Zand)
- Model-based control design (Parya Rozbahani)
- Reinforcement learning modeling (Amirhossein Nourian)
- Deep learning modeling (Mohammad Montazeri)
- Stabilization (Taravat Yazdani)
- Workspace analysis (Mohammad Ghaibi, Hedyeh Moghimi)
- Reduced-order modeling and practical implementation considering environmental factors.

## References
1. P. Namazian, M. T. Masouleh, and M. R. Zakerzadeh, “SPAR-Leg,” IEEE, 2023.
2. Hannan, Michael W. and Walker, Ian D. "Kinematics and the Implementation of an Elephant's Trunk Manipulator and Other Continuum Style Robots." Journal of Robotic Systems, 2003.
4. M. B. M. Damnab, M. T. Masouleh and M. R. H. Yazdi, "Designing and Developing a 6-DOF Calibration Setup Based on the Gough-Stewart Platform Equipped by Potentiometer Sensors," ICROM 2023.
5. P. Namazian, M. T. Masouleh, and M. R. Zakerzadeh, "A general formulation for kinematic analysis and redundancy resolution of hyper-redundant Gough-Stewart hybrid platforms," 2023.
6. Taghirad, Hamid D. "Parallel Robots." CRC Press, 2013.

For more details, see the presentation PDF in this repository. Feel free to contact me for collaborations or questions!
