# Spiking Neural Network for Robot Manipulation

![SNN Robot Manipulation Banner](https://source.unsplash.com/800x200/?robotics,neural-network)  
*Implementation of a Spiking Neural Network for robot manipulation tasks using Behavior Cloning, based on the ManiSkill2 Challenges.*

This repository contains the planned implementation of the spiking neural network (SNN) architecture described in the paper *"Policy Learning with Spiking Neural Network for Robot Manipulation Tasks"* (1st International Conference on Hybrid Societies 2023). The project focuses on training a mobile robot arm for tasks like `OpenCabinetDrawer` using Behavior Cloning (BC) in the ManiSkill2 environment, comparing SNNs with traditional artificial neural networks (ANNs). As a Senior AI & Machine Learning Engineer, this work showcases my expertise in deep reinforcement learning, neuromorphic computing, and robotics.

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)](https://www.python.org/) 
[![PyTorch](https://img.shields.io/badge/PyTorch-2.1+-EE4C2C?logo=pytorch&logoColor=white)](https://pytorch.org/) 
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

---

## 📚 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
- [Dependencies](#dependencies)
- [Project Structure](#project-structure)
- [Implementation Plan](#implementation-plan)
- [Contributing](#contributing)
- [Contact](#contact)
- [Acknowledgments](#acknowledgments)

---

## 📖 Overview

This project will implement the spiking neural network (SNN) architecture described in the paper, which replaces a traditional ANN with a 2D convolutional SNN using Leaky Integrate-and-Fire (LIF) neurons for robot manipulation tasks in the ManiSkill2 environment. The paper reports a 100% success rate and reduced task time (2 seconds vs. 10 seconds) compared to the ANN baseline, with 25% of the original training time. The code will focus on:
- Training an SNN-based policy using Behavior Cloning (BC).
- Processing point cloud data from ManiSkill2.
- Comparing SNN performance against ANN baselines (e.g., SAC, TD3, CQL).

The implementation will be developed in Python using PyTorch and libraries like `snnTorch` for SNN support, aligning with my expertise in neuromorphic computing and reinforcement learning.

---

## ✨ Features

| Feature | Description | Use Case |
|---------|-------------|----------|
| **SNN Architecture** | 2D convolutional SNN with LIF neurons for policy learning. | Efficient robot manipulation |
| **Behavior Cloning** | Trains the agent to mimic expert state-action pairs. | Fast policy learning |
| **Point Cloud Processing** | Handles sensor data for tasks like `OpenCabinetDrawer`. | Robust environment interaction |
| **Performance Comparison** | Benchmarks SNN vs. ANN (success rate, training time). | Evaluate SNN advantages |
| **ManiSkill2 Integration** | Uses ManiSkill2 environment for realistic robot tasks. | Test in standardized challenges |

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10 or higher
- PyTorch 2.1 or higher
- Git
- ManiSkill2 environment (to be installed)

### Setup
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Novalis133/Medium.git
   cd Medium/snn_robot_manipulation
   ```

2. **Create a Virtual Environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   .\venv\Scripts\activate   # Windows
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Code** (once implemented):
   ```bash
   python train_snn.py
   ```

**Troubleshooting** (to be updated post-implementation):
- **Module Not Found**: Ensure `requirements.txt` includes `torch`, `snntorch`, and `maniskill2`.
- **Environment Errors**: Verify ManiSkill2 setup and compatibility with Python version.
- **Path Issues**: Run commands from the `snn_robot_manipulation` directory.

---

## 📋 Dependencies

| Dependency | Version | Installation | Notes |
|------------|---------|--------------|-------|
| Python | 3.10+ | `brew install python@3.10` (macOS) or [python.org](https://www.python.org/) | Core language |
| PyTorch | 2.1+ | `pip install torch>=2.1.0` | Neural network framework |
| snnTorch | Latest | `pip install snntorch` | SNN implementation |
| ManiSkill2 | Latest | `pip install maniskill2` | Robotics environment |
| NumPy | 1.23+ | `pip install numpy>=1.23.0` | Data processing |

Install dependencies:
```bash
pip install torch>=2.1.0 snntorch maniskill2 numpy>=1.23.0
```

**Note**: Dependency versions will be finalized once the code is implemented.

---

## 📂 Project Structure

```
Medium/snn_robot_manipulation/
├── src/                          # Source code for SNN implementation
│   ├── train_snn.py              # Main training script (TBD)
│   ├── models/                   # SNN and ANN model definitions
│   ├── data/                     # Point cloud data processing
│   └── utils/                    # Helper functions
├── experiments/                  # Training logs and results
├── requirements.txt              # Python dependencies
├── LICENSE                       # MIT License
└── README.md                     # Project documentation
```

*Note*: Structure is tentative and will be updated as code is developed.

---

## 📅 Implementation Plan

The code is under development and will include:
1. **SNN Architecture**:
   - Implement 2D convolutional SNN with LIF neurons using `snntorch`.
   - Replace ANN’s MLP and convolutional layers as described in the paper.
   - Include a fully connected layer for policy output.
2. **Behavior Cloning**:
   - Train the SNN using BC to match state-action pairs from ManiSkill2 datasets.
   - Optimize for the `OpenCabinetDrawer` task.
3. **Data Processing**:
   - Process point cloud data using 1D/2D convolutional layers.
   - Integrate sensor data for environment interaction.
4. **Evaluation**:
   - Compare SNN performance (success rate, task time, training time) against ANN baselines (SAC, TD3, CQL).
   - Reproduce the paper’s results: 100% success rate, 2-second task time, 25% training time.
5. **Testing**:
   - Add unit tests for model initialization, data processing, and policy execution.

Expected completion: [Insert estimated timeline, e.g., within 2 weeks from August 2, 2025].

---

## 🤝 Contributing

Contributions to the SNN implementation or ManiSkill2 experiments are welcome! Follow these steps:
1. **Fork the Repository**:
   ```bash
   git fork https://github.com/Novalis133/Medium.git
   ```
2. **Create a Feature Branch**:
   ```bash
   cd Medium/snn_robot_manipulation
   git checkout -b feature/add-snn-layer
   ```
3. **Commit Changes**:
   Use [Conventional Commits](https://www.conventionalcommits.org/):
   ```bash
   git commit -m "feat: implement LIF neuron layer"
   ```
4. **Run Tests and Linting** (once implemented):
   ```bash
   python -m unittest
   black .
   flake8 .
   ```
5. **Submit a Pull Request**:
   ```bash
   git push origin feature/add-snn-layer
   ```
   Open a PR with a detailed description.

**Guidelines**:
- Follow the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/).
- Ensure compatibility with ManiSkill2 and `snntorch`.
- Update `README.md` and `requirements.txt` for new features.

---

## 📫 Contact

- **Email**: osama1339669@gmail.com
- **LinkedIn**: [Osama](https://www.linkedin.com/in/osamat339669/)
- **GitHub Issues**: [Issues Page](https://github.com/Novalis133/Medium/issues)
- **Medium Blog**: [Osama’s Medium](https://medium.com/@osama1339669)

---

## 🙏 Acknowledgments

- [ManiSkill2](https://maniskill2.github.io/) for the robotics environment.
- [snnTorch](https://snntorch.readthedocs.io/) for SNN support.
- [PyTorch](https://pytorch.org/) for the deep learning framework.
- [1st International Conference on Hybrid Societies 2023](https://www.hybrid-societies.org/) for publishing the paper.