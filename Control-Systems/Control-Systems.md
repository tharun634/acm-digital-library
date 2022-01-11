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
   
   * Signal Flow Graphs : While block diagram reduction is the excellent method for determining the transfer function of the control system. However, in a complicated system, it is very difficult and time-consuming process that is why an alternate method, i.e., SFG was developed by S.J Mason which relates the input and output system variables graphically. In the signal flow graph, the transfer function is referred to as transmittance.
   SFG is a graphical representation of the relationship between the variables of a set of linear algebraic equations. It doesn't require any reduction technique or process.\
   ![image](https://user-images.githubusercontent.com/72137415/148914805-039d2996-958f-478f-a005-e6a2a7a80e89.png) \
   The transfer function and overall gain of the system represented using a signal flow diagram is calculated using Mason's Gain Formula. It may appear slightly complicated to look at but with a few examples it is possible to understand it easily. Both the formula and an example explaining how to use it, are given in the link here : https://www.tutorialspoint.com/control_systems/control_systems_masons_gain_formula.htm 
   
   More on signal flow graphs can be found here:  
   https://www.tutorialspoint.com/control_systems/control_systems_signal_flow_graphs.htm


### Order of a system
The order of the system is defined by the number of independent energy storage elements in the system, and intuitively by the highest order of the linear differential equation that describes the system. In a transfer function representation, the order is the highest exponent in the transfer function. \
In simpler terms, when the input, output and gain of a system are represented in the LaPlace domain (i.e. the s domain), the order of the system is given by the highest power of s in the denominator of the transfer function in fractional form.
The order of the system decides the type of response it will have to various inputs, such as impulse, step, ramp and parabolic inputs.

### Time Domain Analysis
Time domain analysis of a system aims to evaluate a system's response with respect to time. There are two components of this response:
* Transient response : The response of the system immediately after the input is applied, i.e. within a short time frame is called the transient response.
* Steady state response : The response of the system a long time after the input is applied, is called the steady state response.
![image](https://user-images.githubusercontent.com/72137415/148953526-b94e549d-60ef-48ce-9737-3ae3987fdd47.png)

The response of first-order systems to various inputs is discussed in this link: https://www.tutorialspoint.com/control_systems/control_systems_response_first_order.htm \
Similarly, for second-order systems, the responses to various inputs are discussed here: https://www.tutorialspoint.com/control_systems/control_systems_response_second_order.htm


### Stability Analysis
The essential requirement for the control system is that it should be stable. It means that the output of the system should follow the input. If the input is finite, the output also needs to be finite in order to satisfy the stability condition.

An LTI (Linear Time-Invariant) system should be stable under the following conditions:
* BIBO (Bounded Input Bounded Output)
   It means that under any initial conditions, the system responds to the bounded input signal with the bounded output signal. If such a condition is satisfied, the system is said to be BIBO. It is commonly used for signal processing systems.
* Linear input and output irrespective of the initial conditions
   It means that if the input is zero, the output should also be zero irrespective of any initial conditions.

### Stability with respect to the location of poles and zeroes
In terms of poles and zeroes, we can represent the transfer function as:\
![image](https://user-images.githubusercontent.com/72137415/148955203-7e4609f7-9794-4a02-b990-dea9aef9d002.png)\
Here, z represents zeroes, and p represents poles. The value of s for which the numerator of the given transfer function is equated to zero is known as zeroes of the system. Similarly, the value of s for which the denominator of the given transfer function is equated to zero is known as the system's pole.\
The roots of the numerator can be represented as -z1, -z2, -z3... -zm, which are known as zeroes.
The poles with the negative real part on the left half of the s-plane are considered poles of a stable system. Thus, we can say that a stable system has a closed-loop transfer function with poles lying only in the left half of the s-plane.
A system is unstable if a pole or more than one pole is present on the right half of the s-plane or poles lying on the imaginary axis.
### Routh Harwitz Criteria for stability of a system
Routh Hurwitz criterion states that any system can be stable if and only if all the roots of the first column have the same sign and if it does not has the same sign or there is a sign change then the number of sign changes in the first column is equal to the number of roots of the characteristic equation in the right half of the s-plane i.e. equals to the number of roots with positive real parts.
The demonstration of the criterion along with an example is given in the following link: https://www.javatpoint.com/control-system-routh-hurwitz-stability-criterion

### Frequency Analysis
The response of a system can be partitioned into both the transient response and the steady state response. We can find the transient response by using Fourier integrals. The steady state response of a system for an input sinusoidal signal is known as the frequency response.\
If a sinusoidal signal is applied as an input to a Linear Time-Invariant (LTI) system, then it produces the steady state output, which is also a sinusoidal signal. The input and output sinusoidal signals have the same frequency, but different amplitudes and phase angles.
The frequency response of a system can be understood using various different tools which are given below. Click on the links to find out in detail about each tool.
   * Bode Plots :  https://www.tutorialspoint.com/control_systems/control_systems_bode_plots.htm
   * Polar Plots : https://www.tutorialspoint.com/control_systems/control_systems_polar_plots.htm
   * Nyquist Plots : https://www.tutorialspoint.com/control_systems/control_systems_nyquist_plots.htm

### Root Locus Plots 
The root locus method was introduced by W.R Evans in 1948. Root locus is a graphical method in which the movement of poles in the s-plane can be located when a specific parameter is varied from 0 to infinity. The parameter assumed to be varied is generally the gain of the system.
Root locus plots are plots that are created when the locus of the roots of the characteristic equation by varying system gain K from zero to infinity are plotted on a polar plot.
Root locus is used to calculate the damping ratio, natural frequency of a system as well as design PID controllers and lead and lag compensators. 
More about root locus plots and plotting them can be seen in the following link:
https://www.tutorialspoint.com/control_systems/control_systems_root_locus.htm

# Resources can be found here:
  * https://www.tutorialspoint.com/control_systems/control_systems_introduction.htm
  * https://www.javatpoint.com/control-system-tutorial
