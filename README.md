# Energy-Efficient-Analog-Compute-in-Memory-Architecture


## Overview
This project explores architectural and circuit-level techniques to improve the energy efficiency of **Analog Compute-in-Memory (CIM)** neural accelerators. While crossbar arrays perform multiply–accumulate (MAC) operations efficiently in the analog domain, overall system energy is often dominated by repeated **Analog-to-Digital Converter (ADC)** operations between neural network layers.

The goal of this project is to **reduce ADC usage while maintaining computational precision**, enabling more efficient on-device AI hardware.

## Key Ideas

### 1. Statistical Conductance Splitting
Each synaptic weight is implemented using multiple parallel devices instead of a single device.  
This reduces device variability through statistical averaging and improves effective precision.

### 2. Analog Layer Cascading
Instead of digitizing the output after every neural layer, multiple layers are allowed to operate sequentially in the **analog domain** before conversion.  
This significantly reduces the number of ADC activations.

### 3. Analog ReLU Activation
A **current-mode ReLU activation circuit** was designed using differential current subtraction and selective current mirroring.  
This enables fully analog signal propagation between layers.

## Architecture
The system consists of three main blocks:

- Differential **MAC crossbar array**
- **Current subtraction + analog ReLU activation circuit**
- Optional **ADC stage** after cascaded layers

This architecture allows neural network computation to remain in the **analog domain for multiple layers**, reducing conversion overhead.

## Implementation
- Circuit-level implementation in **180 nm CMOS**
- Current-mode analog design
- Differential MAC architecture
- Analog ReLU implemented using current mirrors

## Results
Simulation results show:

- **Over 50% reduction in power consumption per MAC layer**
- Reduced ADC activations through analog layer cascading
- Improved effective precision through statistical conductance splitting


## Future Work
Potential improvements include:

- Bit-slicing for higher precision
- Scaling to advanced technology nodes
- Eliminating op-amps for fully transistor-level implementations
- Exploiting sparsity and weight pruning
- Cascading more than two analog layers

