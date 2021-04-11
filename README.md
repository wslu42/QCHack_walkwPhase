The description and main result of this work can be found in "phase_interference_in_QRK.jpynb".

# QCHack_Quantum walk with phase kickback
Use quantum random walk to study phase interference
## Introduction
In this hackathon, it is proposed that in quantum circuits, the "correct" answer may cause constructive interference due to the phase, while the "wrong" answer will cause destructive interference. Therefore, we use the random walk of the toe to explain the phase. First of all, quantum random walk is a mathematical statistical model that uses the properties of quantum mechanics to generate random processes. In the experiment, we simulated classical random walk and quantum random walk and made a comparison between the two, but quantum random walk Because of phase interference, the result of walking is not fair but tends to be biased to a certain side. In order to solve the problem of phase interference, we proposed the concept of phase kickback and made the Y-gate coin and Hadamard coin to explain that phase interference will affect the result of quantum random walk.

## Random walk

The figure below shows a simple random walk type
[![Build Status](https://i.ibb.co/2NC2pvd/Random-Walk.png)

The dynamics can be regarded as a simple algorithm:

There is a  𝑛 -dimensional space (in this case, one for simplicity) and a walker which starts at the point  𝑥=0 
The walker then takes a step either forwards (towards  +𝑥 ) or backwards (towards  −𝑥 )
In the second step, the choice is made randomly (eg. a coin-flip). We can call this the "Coin Operator".

For this system:  𝑝+𝑞=1 .


## Quantum Walk

[![Build Status](https://i.ibb.co/3Ry0hXs/image.png)
A quantum walk is the "quantum version" of a classical random walk. This means the coin function will be a Unitary gate ( 𝑈(2) ) which is non-random and reversible:

                                                                
In this notebook, we use a Hadamard gate for executing the coin function since it puts our qubits in a state of superposition, allowing for the simulation of a coin based probability:

[![Build Status](https://i.ibb.co/yQv7k3L/image.png)



## The Coin Operator
The first operation in a quantum random walk is the coin operator. The operator works by performing an arbitrary unitary transformation in the coin space which creates a rotation similar to “coin-flip” in random walk. This is namely the Hadamard gate, which models a balanced unitary coin.

The coin register will continue interfering with its position state until it is measured, after all intermediate steps. The results are very different from random walks as it doesn’t converge to a Gaussian distribution, but rather evolves into an asymmetric probability distribution. This happens because the Hadamard coin operator treats each basis vectors, |↑> and |↓> , differently.

The rightwards path interferes more destructively as it is multiplied by -1, however, the leftwards path undergoes more constructive interference and the system tends to take steps towards the left. To reach symmetric results, both base vectors will start in a superposition of states (between |↑> and |↓>). Another way to reach symmetry is use a different coin operator which doesn’t bias the coin towards a certain base vector, such as the Y gate:

[![Build Status](https://i.ibb.co/Jd1L9yF/image.png)

## Phase kickbback

When we use control gate,there will be a problem called Phase kickback.Such as :
[![Build Status](https://miro.medium.com/max/875/1*XbUpprATbTvB_nGyZfcU1A.png)

