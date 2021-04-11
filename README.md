In this work, we would like to use quantum random walk to study phase interference, and a complete description and main result of this work can be found in "phase_interference_in_QRK.jpynb".

(The evolution of quantum random walk with Hadamard coin in 1D)

![mygif](https://user-images.githubusercontent.com/29524895/114307270-df84b200-9aac-11eb-9a89-21b3595e8328.gif)

# QCHack_Quantum walk with phase kickback

One distinct feature in quantum random walk to its classical counterpart is that this coin register will continue interfere with its position state until it is measured, after all intermediate steps. The results are very different from classical random walks as it doesn’t converge to a Gaussian distribution, but rather evolves into an asymmetric probability distribution.

![CvQ](https://user-images.githubusercontent.com/29524895/114307395-6cc80680-9aad-11eb-8b76-9422735df91b.png)

In addition to the deviation from Gaussian, in this work we focus more on the asymmetric distribution in the quantum random walk where we see in above graph. As indicated in ref 3, such asymmetry arises because the Hadamard coin operator treats each basis vectors, |↑> and |↓> , differently by observing the phase difference.

In the Hadamard coin operator, the rightwards path interferes more destructively as it is multiplied by -1, however, the leftwards path undergoes more constructive interference and the system tends to take steps towards the left. To reach symmetric results, both base vectors will start in a superposition of states (between |↑> and |↓>). Another way to reach symmetry is use a different coin operator which doesn’t bias the coin towards a certain base vector.

The entire effect is similar to the idea of phase kickback [ref 5]

The circuit representation of this Y circuit seems to be straightforward, but as we will show in this work some other careful treatment (in addition to converting H to Y) should be done to fully employ the symmetric treatment in terms of phase on the Bloch sphere.

This constitutes out motivation to use Qiskit to study interference effects in the phase of a quantum circuit.

In this hackathon, it is proposed that in quantum circuits, the "correct" answer may cause constructive interference due to the phase, while the "wrong" answer will cause destructive interference. Therefore, we use the random walk of the toe to explain the phase. First of all, quantum random walk is a mathematical statistical model that uses the properties of quantum mechanics to generate random processes. In the experiment, we simulated classical random walk and quantum random walk and made a comparison between the two, but quantum random walk Because of phase interference, the result of walking is not fair but tends to be biased to a certain side. In order to solve the problem of phase interference, we proposed the concept of phase kickback and made the Y-gate coin and Hadamard coin to explain that phase interference will affect the result of quantum random walk.

## Phase kickbback

When we use control gate,there will be a problem called Phase kickback.Such as :
[![Build Status](https://miro.medium.com/max/875/1*XbUpprATbTvB_nGyZfcU1A.png)

