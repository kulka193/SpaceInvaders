# SpaceInvaders

# SpaceInvaders RL Agents

A collection of Jupyter Notebooks for training reinforcement learning (RL) agents on the classic Atari game Space Invaders using Python, TensorFlow/Keras, and OpenAI Gym. The repository demonstrates modern RL techniques including Deep Q-Networks (DQN) and Advantage Actor Critic (A2C), with robust preprocessing, environment wrappers, and model architectures.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Notebooks Overview](#notebooks-overview)
  - [DQN_SpaceIvaders (2).ipynb](#dqn_spaceivaders-2ipynb)
  - [actor_critic_2.ipynb](#actor_critic_2ipynb)
- [Installation](#installation)
- [How to Run](#how-to-run)
- [Usage & Customization](#usage--customization)
- [References](#references)
- [License](#license)

---

## Project Overview

This project implements RL agents that learn to play the Space Invaders Atari game. It provides:

- Deep Q-Network (DQN) agent with frame stacking, experience replay, and Huber loss optimization.
- Advantage Actor Critic (A2C) agent using dual-headed neural networks (actor and critic), custom loss functions, and reward discounting.
- Extensive notebook-based implementation for experimentation and visualization, compatible with Google Colab and local Jupyter environments.
- Preprocessing (frame cropping, grayscaling, resizing, stacking) inspired by state-of-the-art DeepMind RL research.

---

## Notebooks Overview

### `DQN_SpaceIvaders (2).ipynb`

Implements a DQN Agent with the following features:

- Image preprocessing: grayscaling, normalization, resizing.
- Frame stacking for temporal awareness.
- Experience replay buffer for stable training.
- Neural network function approximation with convolutional layers.
- Target network soft updates (controlled by τ parameter).
- Huber loss and RMSprop optimizer to stabilize training.
- Action selection with ε-greedy exploration and dynamic decay.
- Model saving, video recording, and result visualization.
- Hyperparameters tuned as per DeepMind’s DQN paper.

### `actor_critic_2.ipynb`

Implements an A2C (Advantage Actor Critic) Agent:

- Dual-headed neural network model (actor for policy, critic for value estimation) built with TensorFlow/Keras.
- Custom loss functions using advantage-based gradients (for actor) and Huber loss (for critic).
- Environment wrappers and classes for preprocessing, model checkpoints, video recording, and reward shaping.
- Training loop for distributed interaction and checkpointing.
- Utilities for rendering gameplay videos inside the notebook.

---

## Installation

**Local (recommended for advanced users):**

1. **Clone the repository:**
   ```bash
   git clone https://github.com/kulka193/SpaceInvaders.git
   cd SpaceInvaders
   ```

2. **(Optional) Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # For Windows: venv\Scripts\activate
   ```

3. **Install Python dependencies:**
   The notebooks mainly require:
   - Python >= 3.6
   - numpy, gym, tensorflow, keras, opencv-python, matplotlib, scikit-image, pyvirtualdisplay, autorom
   - For Atari ROMs:
     ```bash
     pip install gym[atari] autorom ale-py pyvirtualdisplay opencv-python matplotlib scikit-image tensorflow keras wandb
     AutoROM --accept-license
     ```
   (Some installation commands are included as notebook cells; run them as needed.)

**Google Colab (no local setup required):**
- Simply upload the notebook to Colab and run. Required packages are installed by the first code cells.

---

## How to Run

1. **Open the notebook with Jupyter or Google Colab:**
   - Locally: `jupyter notebook`
   - Or in Colab via the GitHub link.

2. **Run the setup cells:**
   - Make sure to run the cells that install Python packages, setup virtual display, and download Atari ROMs.
   - For Colab: Follow cell instructions; e.g., run `!pip install ...`, `!apt-get install ...`, and `!AutoROM --accept-license`.

3. **Train the agent:**
   - For DQN: Run all cells sequentially. Adjust hyperparameters and agent configuration as needed.
   - For A2C: Similarly, run setup, then proceed through exploration, training, and evaluation cells.

4. **Monitor progress:**
   - Some notebooks use `wandb` (Weights & Biases) for logging metrics and saving models. Configure your API key if used.
   - Play back reward trends and video frames generated within the notebook cells.

5. **Experiment and modify:**
   - The code is structured for easy experimentation. Change hyperparameters, network architectures, preprocessing, or RL algorithms.

---

## Usage & Customization

- Change the environment (e.g., different Atari games) by modifying `gym.make(...)`.
- Tune hyperparameters (network size, optimizer, replay buffer, batch size, etc.) for performance.
- Integrate with tracking/logging tools (WandB, TensorBoard) as shown in the notebooks.
- Use saved models for inference or continued training.
- Extend agents to try Dueling DQN, Double DQN, or bootstrapped actor-critic variants.

---

## References

- [Deep Q-Learning (DQN) paper (Mnih et al., 2015)](https://www.nature.com/articles/nature14236)
- [OpenAI Gym documentation](https://www.gymlibrary.dev/)
- [Advantage Actor-Critic (A2C) research](https://spinningup.openai.com/en/latest/algorithms/a2c.html)
- [Deep Reinforcement Learning resources](https://nihit.github.io/resources/spaceinvaders.pdf), [BecomingHuman.ai SpaceInvaders DQN tutorial](https://becominghuman.ai/beat-atari-with-deep-reinforcement-learning-part-2-dqn-improvements-d3563f665a2c)

---

## License

This project is licensed under the MIT License.
