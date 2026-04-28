# Deep Reinforcement Learning Agent

A comprehensive implementation of a Deep Reinforcement Learning agent trained on the LunarLander-v3 environment using state-of-the-art algorithms and frameworks.

## 📋 Overview

This project demonstrates the implementation and training of a deep reinforcement learning agent using:
- **Algorithm**: Proximal Policy Optimization (PPO)
- **Environment**: LunarLander-v3 (Gymnasium)
- **Framework**: Stable Baselines3
- **Model Hub Integration**: Hugging Face Hub

The agent learns to successfully land a spacecraft by managing fuel consumption and maintaining stability.

## 📁 Project Structure

```
Deep-Reinforcement-Learning-Agent/
├── Deep_Reinforcement_Learning_Agent.ipynb    # Main implementation notebook
├── Deep_RL_Agent_Train.ipynb                   # Training and evaluation notebook
└── README.md                                   # This file
```

## 🚀 Features

- **Environment Setup**: Automatic installation of dependencies including virtual display for headless rendering
- **Agent Training**: PPO-based training on the LunarLander-v3 environment
- **Vectorized Environments**: Multi-environment training (16 parallel environments) for improved efficiency
- **Model Evaluation**: Comprehensive evaluation metrics and policy performance assessment
- **Hub Integration**: Easy model upload and sharing via Hugging Face Hub
- **Google Colab Support**: Fully compatible with Google Colab for cloud-based training

## 🛠️ Installation

### Prerequisites
- Python 3.7+
- pip package manager

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/nuwanisamarakoon/Deep-Reinforcement-Learning-Agent.git
   cd Deep-Reinforcement-Learning-Agent
   ```

2. **Install dependencies**
   ```bash
   pip install -r https://raw.githubusercontent.com/huggingface/deep-rl-class/main/notebooks/unit1/requirements-unit1.txt
   ```

3. **Additional dependencies** (for rendering)
   ```bash
   pip install gymnasium[box2d]
   pip install stable-baselines3
   pip install huggingface-sb3
   pip install pyvirtualdisplay
   ```

### Environment Requirements (Linux/Google Colab)

For headless rendering support:
```bash
apt-get update
apt-get install -y python3-opengl ffmpeg xvfb swig cmake
```

## 📚 How to Use

### Running in Jupyter Notebook

1. **Open the notebooks**
   - `Deep_Reinforcement_Learning_Agent.ipynb` - Start here for the main implementation
   - `Deep_RL_Agent_Train.ipynb` - Run this for training and evaluation

2. **Execute cells sequentially** to:
   - Install dependencies
   - Set up the virtual display (if running headless)
   - Initialize the LunarLander environment
   - Train the PPO agent
   - Evaluate the trained agent

### Running in Google Colab

Click the "Open In Colab" button at the top of the notebooks to run directly in the cloud.

## 🎮 LunarLander Environment

The LunarLander-v3 environment provides:
- **Observation Space**: 8-dimensional vector (position, velocity, angle, angular velocity, leg contact flags)
- **Action Space**: 4 discrete actions (no action, fire left thruster, fire main engine, fire right thruster)
- **Goal**: Land the spacecraft smoothly without crashing

### Environment Specifications

```python
# Observation Space
Shape: (8,)
Sample observation: [x, y, vx, vy, angle, angular_velocity, left_leg_contact, right_leg_contact]

# Action Space
Discrete(4)
0: Do nothing
1: Fire left thruster
2: Fire main engine
3: Fire right thruster
```

## 🤖 Training Details

### Algorithm: Proximal Policy Optimization (PPO)

PPO is a state-of-the-art reinforcement learning algorithm that:
- Provides stable and sample-efficient training
- Uses importance sampling to prevent large policy updates
- Maintains a good balance between exploration and exploitation

### Vectorized Training

The project uses 16 parallel environments to:
- Accelerate training convergence
- Increase computational efficiency
- Provide more diverse experiences for the agent

## 📊 Model Evaluation

The trained agent is evaluated using:
- **Mean Reward**: Average cumulative reward across episodes
- **Success Rate**: Percentage of successful landings
- **Policy Performance**: Consistency and stability metrics

## 🤗 Hugging Face Hub Integration

The project includes functionality to:
- Push trained models to Hugging Face Hub
- Load pre-trained models from the Hub
- Share models with the community

### Uploading Your Model

```python
from huggingface_sb3 import package_to_hub

package_to_hub(
    model_id="your-username/lunar-lander-ppo",
    model=model,
    repo_url="https://huggingface.co/your-username/lunar-lander-ppo",
    commit_message="Add my trained LunarLander agent"
)
```

## 📦 Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| gymnasium | Latest | RL environment framework |
| stable-baselines3 | Latest | PPO and other RL algorithms |
| huggingface-sb3 | Latest | Hub integration for SB3 models |
| huggingface-hub | Latest | Hugging Face Hub API |
| numpy | Latest | Numerical computations |
| torch | Latest | Deep learning backend |
| Box2D | Latest | LunarLander physics simulation |

## 📝 Notebooks Overview

### Deep_Reinforcement_Learning_Agent.ipynb
- Environment setup and verification
- Agent initialization and configuration
- Model creation with PPO algorithm
- Basic training loop demonstration

### Deep_RL_Agent_Train.ipynb
- Full training pipeline
- Vectorized environment creation
- Extended training runs
- Policy evaluation and performance metrics
- Model saving and hub integration

## 🎯 Key Concepts Demonstrated

- **Policy Gradient Methods**: Understanding PPO algorithm
- **Vectorized Environments**: Multi-environment training
- **Evaluation Metrics**: Assessing agent performance
- **Virtual Rendering**: Headless environment visualization
- **Model Persistence**: Saving and loading trained agents

## 🔗 Resources

- [Gymnasium Documentation](https://gymnasium.farama.org/)
- [Stable Baselines3](https://stable-baselines3.readthedocs.io/)
- [Hugging Face Deep RL Course](https://huggingface.co/deep-rl-class)
- [PPO Paper](https://arxiv.org/abs/1707.06347)

## 💡 Tips for Improvement

- Experiment with different hyperparameters (learning rate, n_steps, batch_size)
- Try different environments from Gymnasium
- Implement custom reward shaping
- Explore other algorithms (A2C, DDPG, TD3)
- Add tensorboard logging for better training visualization

## 🐛 Troubleshooting

### Import Errors
- Ensure all dependencies are installed: `pip install -r requirements.txt`

### GPU Issues
- The project works on both CPU and GPU
- PyTorch will automatically detect and use available GPU

### Rendering Issues (Colab)
- Virtual display setup is included in the notebooks
- For local headless systems, ensure X11 dependencies are installed

## 📄 License

This project is provided as-is for educational purposes.

## 👤 Author

Created by nuwanisamarakoon

## 🤝 Contributing

Feel free to fork, modify, and improve this project!

## ⭐ Acknowledgments

- Hugging Face for the Deep RL Class and resources
- OpenAI/Farama Foundation for Gymnasium
- DRL-driven research community

---


