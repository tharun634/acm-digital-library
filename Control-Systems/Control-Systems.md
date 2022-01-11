# Control Systems
A control system is defined as a system of devices that manages, commands, directs, or regulates the behavior of other devices or systems to achieve a desired result.
It achieves this through control loops, which are a process designed to maintain a process variable at a desired set point.
The three basic parts of a control system are:  
  * The error detector
  * The controller 
  * The output element

### Open and Closed Loop Control Systems
Control Systems can be divided into Open-loop and Closed-loop control systems. 
In open loop control systems, output is not fed-back to the input. So, the control action is independent of the desired output. These systems are easier to design but have less accuracy because there is no feedback from the output.
Examples of open loop control systems include traffic lights, immersion water heaters etc.
![image](https://user-images.githubusercontent.com/72137415/148272259-407e6466-83d0-4a4a-bd96-34cf7c0c47fc.png)

In closed loop control systems, output is fed back to the input. So, the control action is dependent on the desired output. These systems are more complex and difficult to design but have better control over the output because of the feedback and hence the output is accurate. 
Examples of such systems include air conditioner, pressure control system etc. 
![image](https://user-images.githubusercontent.com/72137415/148272214-2af134d9-4b9e-4313-8c27-539c8486f78f.png)

### Transfer Function
A transfer function represents the relationship between the output signal of a control system and the input signal, for all possible input values.
In a Laplace Transform, if the input is represented by R(s) and the output is represented by C(s), then the transfer function will be: 
![image](https://user-images.githubusercontent.com/72137415/148949693-fe4092f8-df35-4be8-a756-7f940c17aa7b.png)

### Representation of Control Systems
Control systems are represented in two main ways, which are as follows:
   * Block Diagrams : Here, a control system is represented by blocks to depict it pictorially. Block diagrams contain blocks (which represent the transfer function and have one input and one output), take-off point (representing branching of signals) and summation points (which depict an algebraic summation of two or more input signals to one output signal).
   ![image](https://user-images.githubusercontent.com/72137415/148892599-cfa0f187-9c33-4378-ac39-333fe9a0d379.png) \
   More on block diagrams can be read here:
   https://www.javatpoint.com/control-system-block-diagram \
   The link above also provides a detailed discussion on block diagram reduction methods. This is essential when the system is big and the overall transfer function has to be calculated, or the system has to be simplified.
   
   * Signal Flow Graphs : While block diagram reduction is the excellent method for determining the transfer function of the control system. However, in a complicated system, it is very difficult and time-consuming process that is why an alternate method, i.e., SFG was developed by S.J Mason which relates the input and output system variables graphically. In the signal flow graph, the transfer function is referred to as transmittance. \ 
   SFG is a graphical representation of the relationship between the variables of a set of linear algebraic equations. It doesn't require any reduction technique or process.\
   ![image](https://user-images.githubusercontent.com/72137415/148914805-039d2996-958f-478f-a005-e6a2a7a80e89.png) \
   The transfer function and overall gain of the system represented using a signal flow diagram is calculated using Mason's Gain Formula. It may appear slightly complicated to look at but with a few examples it is possible to understand it easily. Both the formula and an example explaining how to use it, are given in the link here : https://www.tutorialspoint.com/control_systems/control_systems_masons_gain_formula.htm \
   
   More on signal flow graphs can be found here:  
   https://www.tutorialspoint.com/control_systems/control_systems_signal_flow_graphs.htm

### Time Domain Analysis:


### Stability Analysis:

### Frequency Analysis:
   * Bode Plots : https://www.tutorialspoint.com/control_systems/control_systems_bode_plots.htm
   * Polar Plots : https://www.tutorialspoint.com/control_systems/control_systems_polar_plots.htm
   * Nyquist Plots : https://www.tutorialspoint.com/control_systems/control_systems_nyquist_plots.htm

### Root Locus Plots : 
https://www.tutorialspoint.com/control_systems/control_systems_root_locus.htm

Resources can be found here:
  * https://www.tutorialspoint.com/control_systems/control_systems_introduction.htm
  * https://www.javatpoint.com/control-system-tutorial
