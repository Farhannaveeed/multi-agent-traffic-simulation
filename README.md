# Multi-Agent Traffic Simulation

A Deep Reinforcement Learning project designed to optimize traffic light control at intersections using Deep Q-Learning (DQN) and the SUMO (Simulation of Urban MObility) environment.

## Overview

This project implements a multi-agent system where an agent learns to control traffic lights to minimize wait times and maximize traffic flow. The simulation uses SUMO for realistic vehicle dynamics and TraCI for real-time interaction between the Python code and the simulation.

## Features

- Deep Q-Network (DQN) architecture for traffic signal control.
- Integration with SUMO for high-fidelity traffic simulation.
- Configurable simulation parameters via .ini files.
- Training and testing pipelines.
- Memory replay and target network for stable reinforcement learning.
- Support for GUI and non-GUI simulation modes.

## Prerequisites

- Python 3.8+
- SUMO (Simulation of Urban MObility) installed and available in system PATH.
- Graphviz (for model visualization if used).

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Farhannaveeed/multi-agent-traffic-simulation.git
   cd multi-agent-traffic-simulation
   ```

2. Install the required Python packages:
   ```bash
   pip install -r src/requirements.txt
   ```

3. Ensure SUMO_HOME environment variable is set:
   - Windows: `C:\Program Files (x86)\Eclipse\Sumo` (or your installation path)
   - Linux: `/usr/share/sumo`

## Usage

### Training

To train the traffic agent, run:
```bash
python src/training_main.py
```
Training parameters like number of episodes, layers, and learning rate can be modified in `src/training_settings.ini`.

### Testing

To test a trained model:
```bash
python src/testing_main.py
```
Testing configurations can be found in `src/testing_settings.ini`.

## Project Structure

- `src/`: Core source code directory.
  - `training_main.py`: Main entry point for training.
  - `testing_main.py`: Main entry point for testing.
  - `model.py`: DQN model architecture using TensorFlow.
  - `training_simulation.py`: Environment logic for training.
  - `testing_simulation.py`: Environment logic for testing.
  - `generator.py`: Generates traffic patterns for simulation.
  - `memory.py`: Replay memory implementation.
  - `utils.py`: Utility functions.
  - `training_settings.ini`: Configuration for training runs.
  - `testing_settings.ini`: Configuration for testing runs.
- `trainingDetails.txt`: Log of training episodes and parameters.
- `.gitignore`: Specifies files to be ignored by Git (venv, results, cache).

## Configuration

The simulation behavior and model architecture are controlled through settings files. Key parameters include:
- `total_episodes`: Number of training runs.
- `max_steps`: Maximum duration of each simulation.
- `n_cars_generated`: Number of vehicles per simulation.
- `num_layers` & `width_layers`: Neural network configuration.
- `learning_rate`: Step size for weight updates.
