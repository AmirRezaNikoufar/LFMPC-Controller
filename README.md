## **Model Predictive Controller based on Laguerre Functions for 2 DOF robot**  

This project focuses on controlling a 2-DOF rehabilitation robot designed for lower limb therapy using a Model Predictive Controller (MPC). The main goal is to track the robot’s joint angles accurately while considering input constraints through numerical optimization.

Methodology
1. Dynamic Modeling
The robot’s dynamic equations are derived using Newton’s method. These equations are then discretized using Taylor series expansion and represented in state-space form.
![image](https://github.com/user-attachments/assets/a2bbe037-c322-4fd5-9788-ca3e5a397c43)

2. State-Space Representation After Discretization
the continuous dynamic equations are discretized using a Taylor series expansion. This converts the system into a discrete-time state-space form, where the state represents the robot’s joint angles and velocities, and the input corresponds to the torques.

    ![image](https://github.com/user-attachments/assets/00bae44d-65b6-4997-b195-9d8270e18ca1)


4. Output Representation Using Recursive Relations
Next, the relationship between the current state and future outputs is expressed using recursive relations. By expanding the system behavior over multiple time steps, a prediction model is built, which is essential for implementing Model Predictive Control (MPC).

5. Control Law
To improve the efficiency of the optimization, the input signals (torques) are formulated using Lagrange basis functions. This approach reduces the number of optimization variables by representing the inputs as a combination of predefined basis functions, which accelerates the computation.
Tracking Problem Solution: Using the state-space equations, the joint angle tracking problem is solved. Lagrange functions are applied to accelerate the optimization process, and both analytical and numerical approaches are implemented.
![image](https://github.com/user-attachments/assets/7284d977-cf25-4a82-ab7d-549a508bd884)

6. Cost Function Definition and Analytical Solution
A cost function is defined to measure the tracking error between the desired and actual joint angles while penalizing excessive input usage. An analytical solution is derived for the unconstrained optimization problem to understand the system’s ideal behavior without input limitations.
![image](https://github.com/user-attachments/assets/e70f58e1-917c-406a-a674-114ba83d06f9)

7. Constrained Optimization Using Quadprog
Finally, input constraints are introduced to ensure that the robot operates within safe limits. The constrained optimization problem is solved using the Quadprog method, which efficiently handles quadratic optimization with linear constraints. This step ensures that the control inputs respect physical limits, such as maximum torque.
![image](https://github.com/user-attachments/assets/7a5dae1c-f71b-4f0d-885a-5642a84c3d6e)

The figures below illustrate the simulation results, showcasing the robot’s joint angle tracking performance and the effectiveness of the proposed Model Predictive Control (MPC) approach.
![image](https://github.com/user-attachments/assets/a271d5b7-452a-488a-b489-a0fc2b9a176d)

![image](https://github.com/user-attachments/assets/c002aba7-8667-4de7-b3f3-74b2a0db675a)
