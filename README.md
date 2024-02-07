# Quantum Machine Learning for Quantum Many-Body Systems
## Motivation

Traditional machine learning models have successfully learned from accurately calculated molecular properties, significantly advancing the exploration of chemical space. This involves systematically navigating potential chemical compounds based on desired characteristics and predicting properties of new molecules through structural features. The emergence of quantum machine learning is expected to enable exploration in a broader materials space, accelerating the discovery of compounds with desired properties for more sustainable and efficient technologies.

Many-body systems refer to physical systems composed of a large number of interacting elements, often particles such as atoms or molecules. The behavior of these systems is governed by the principles of quantum mechanics, where the interactions between individual particles give rise to collective phenomena that can be highly complex and challenging to predict. Large-scale neural networks, successful in solving complex problems like image recognition, have been applied to study quantum many-body systems. However, directly applying classical algorithms to inherently quantum problems, where quantum states or processes are inputs, is challenging due to the extensive many-body Hilbert space.

In the realm of condensed matter physics, understanding the diverse phases of matter is crucial. These phases, such as topological or superconducting states, emerge from the collective quantum behavior of particles at ultra-low temperatures. Traditional methods of classifying these phases involve measuring global properties, often challenging due to the complexities of quantum systems. Quantum machine learning, however, employs algorithms designed to operate on quantum computers, enabling efficient analysis of these systems. By utilizing quantum neural networks, it becomes feasible to learn and classify different quantum phases based on observable features like magnetic fields and chemical potentials. This approach holds promise for unraveling the mysteries of quantum matter and can potentially revolutionize our ability to predict and engineer materials with unique and desirable properties for technological applications.

## Classifying topological and trivial phases in a superconducting system

### Topological and trivial phases
In condensed matter physics, the topological phase refers to a unique state of matter that exhibits non-local and robust quantum properties. These properties are protected against small perturbations. Topological phases are often characterized by nontrivial global properties of the system, such as nontrivial topology of the electronic wavefunctions or the existence of edge states. In contrast, a trivial phase is a conventional state of matter that does not exhibit the non-local and robust quantum properties characteristic of topological phases.

### Majorana modes
Majorana modes are special quasiparticle excitations that exist in certain condensed matter systems. They are their own antiparticles, meaning a Majorana fermion is identical to its own conjugate. In the context of superconductors, Majorana modes can emerge at the ends of a one-dimensional superconducting wire which exhibits a topological phase.

### Topological phase in a real system
We need three key ingredients to obtain a topological phase in a real engineered system.  First, we need to have a superconductor. Let us assume that our system is composed of a gapped superconductor such as Aluminium. Second, we need to induce spin-orbit coupling which can be induced by proximity coupling the semiconductor nano-wire. An example of that is InAs. Third, we need to apply an external magnetic field to the system.

<img src="MZM.png" alt="drawing" width="200"/>

Our system has two tuning knobs. We can tune the chemical potential, $\mu$ of the system by gating. We can also change the magnitude of the magnetic field, $B_z$. At certain critical values of the magnetic field, the system undergoes a topological phase transition. In the topological phase, Majorana modes appear at the ends of the wire. These Majorana modes are robust against local perturbations, making them interesting for potential applications in quantum computing. The condition to obtain a topological phase is $$B_z^2>\mu^2+\Delta^2$$ where $\Delta$ is the superconducting energy gap (order parameter).

## Problem statement
Based on the parameters, $B_z$ and $\mu$, we can tune the system into topological and trivial phase. By normalizing these parameters with respect to the superconducting energy gap, as $B_z/\Delta \rightarrow B_z$ and $\mu/\Delta \rightarrow \mu$, we redefine our variables.  Therefore, we get the criterion for topological phase as $$B_z^2>\mu^2+1.$$

Our dataset is composed of values corresponding to $B_z$ and $\mu$, now redefined in terms of $\Delta$ as mentioned above. These data points, along with the condition $B_z^2 > \mu^2 + 1$, are utilized for training a quantum neural network. The primary objective is to enable the quantum neural network to predict whether the system will exhibit a topological or trivial phase based on the input values of $B_z$ and $\mu$.
