# Quantum Walks and Monte Carlo
**Global Quantum Program 2025**

### Project Description:
  - Click [here](https://www.thewiser.org/quantum-walks-monte-carlo) to view the project description.


### Team Name

### Team Size:
  - Team size = 3

---

### Team Members
- Mrunal Arun Kumavat (gst-5xQeln6sCF0kYi6)
- Ritisha Katiyar (gst-BlDqzagDwOqhxW3)
- Viraj Daniel Dsouza (gst-XsbkDJWSAD37VOk)

---

### Project Summary
This project repository explores the **Universal Statistical Simulator** by implementing a Quantum Galton Board (QGB), a quantum analogue of the classic Plinko game. The Galton board serves as a physical realization of a Monte Carlo simulation, a powerful method for solving complex, high-dimensional problems in fields like particle transport and quantum physics. Our work focuses on developing and optimizing quantum circuits that generate various statistical distributions.

Initially, we developed a general algorithm to construct a QGB circuit for an arbitrary number of layers, building upon a 1, 2, 3 and 4-layer model. We successfully verified that the output of our noiseless circuit adheres to a Gaussian distribution, consistent with the classical Galton board's behavior. We then adapted this core functionality to produce other, non-Gaussian distributions, specifically the **Exponential distribution** and the **Hadamard quantum walk**. For all implementations, we provided good fits between the observed results and the theoretical forms of each distribution.

The next phase of the project involved simulating these circuits on a **noisy model** of a quantum hardware. Recognizing that gate errors and decoherence significantly impact circuit fidelity, we focused on quantifying these errors for the circuits of interest and developing optimized implementations wherever possible. This involved creating custom transpiler pass managers to mitigate noise, specifically by optimizing qubit layout, routing, etc. Through a systematic search for the best transpiler pass manager, we aimed to maximize the accuracy and the number of layers achievable before noise completely dominates the signal. This part of the project highlights the critical role of appropriate transpilation and noise mitigation in practical quantum computing.

Finally, we also conducted an analysis of the results by computing the statistical distance between our simulated distributions and the ideal target distributions. This allowed us to quantify the impact of noise and the effectiveness of the strategies used, providing a comprehensive evaluation of our implementation's performance. The project demonstrates a full cycle of quantum algorithm development, from theoretical implementation to practical optimization on a noisy hardware model.

---

## Project outcomes

#### Task 1: 2-Pager Summary of QGBs
A well-structured 2-pager document summarizing the implementation of QGBs based on a review of the paper can be found [here](). 


#### Task 2: Universal Galton Board Algorithm
* **Implementation**: We started with a QGB circuit with small number of layers to observe the pattern to help us generalize the circuit for arbitrary number of layers. Refer [here]() for the implementation. We then developed a general-purpose algorithm capable of generating a QGB circuit for any number of layers. The algorithm was verified using a noiseless simulator, confirming that the output distribution for the measured samples is Gaussian, matching the expected behavior of a classical Galton board. Refer [here]() for the detailed implementation and verification of the generalized QGB.


#### Task 3: Implementing Alternative Distributions
* **Exponential Distribution**: By using a row-dependent `Ry` rotation gate in the 'peg' construction, we  generated an exponentially decaying distribution. The rotation angle was carefully chosen to decrease the probability of a "right" movement with each subsequent layer. Additionally, we explored another possible implementation with more control possible over the exponential decay rate. 
* **Hadamard Quantum Walk**: 

Refer [here]() for the implementation. 

#### Task 4: Optimized Implementation on Noisy Hardware
* **Pass Managers**: We utilized IBM qiskit's custom `PassManager` to optimize the circuits for a real hardware noise model. 
* **Maximizing Accuracy**: We benchmarked different transpiler settings and seeds to find the optimal configuration that minimizes the total accumulated error, allowing for a greater number of layers to give reliable results on the noisy simulator.

#### Task 5: Distance Computation and Uncertainty
* **Statistical Analysis**: We computed the distances between the distributions obtained from the noisy simulations and the ideal distributions. (TODO)

---

### Result Plots
(TODO)

---

### Project Presentation Deck
(Link to Project Presentation Deck- TODO)

### Installation and Usage Tips

Please fork the repository and clone the fork to your local device. Certain files use modules that contain helper functions. 

Install all the necessary packages using the `requirements.txt` file. 

You can use `pip install -r requirements.txt` to install all the packages needed.

Please create your ibm `api-token` from [upgraded IBM Quantum&reg; Platform](https://quantum.cloud.ibm.com/). Then create your instance and copy its CRN code. Save the details using the code below to run the codes on real hardwares and/or noise simulators. 


'QiskitRuntimeService.save_account(
    channel="ibm_quantum_platform",
    token=your_api_key,
    instance=your_crn,
    name="any_name",
    overwrite=True,
)'

### Contributing

If you wish to contribute to this repository, please fork the repository, make your contributions in your fork, and submit a pull request


### License

This project is licensed under the MIT License - see the [LICENSE](MIT-LICENSE.txt) file for details.