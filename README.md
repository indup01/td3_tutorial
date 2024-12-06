# td3_tutorial  
Github for TD3 Implementation with MuJoCo Inverted Pendulum v4

https://nbviewer.org/github/indup01/td3_tutorial/blob/main/TD3_visual.ipynb

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/git/https%3A%2F%2Fgithub.com%2Findup01%2Ftd3_tutorial/main?labpath=%2FTD3_visual.ipynb)

Required Packages:

stable_baselines3 

typing

gymnasium (newer) / gym

gym-notices

numpy

os

mujoco

jupyter notebook

matplotlib

moviepy

pygame

pytorch

pandas

tensorboard

Hyper parameters - can be adjusted by calling self.___ =  after TD3 class model is created

:param policy: The policy model to use (MlpPolicy, CnnPolicy, ...)
 "MlpPolicy" for low-dimensional state spaces, "CnnPolicy" for high-dimensional state spaces (e.g., images).

:param env: The environment to learn from (if registered in Gym, can be str)
Ensure the action space is continuous since TD3 is designed for continuous action environments.

:param learning_rate: learning rate for adam optimizer, the same learning rate will be used for all networks (Q-Values, Actor and Value function) it can be a function of the current progress remaining (from 1 to 0)
1e-3 (default), or a schedule like lambda x: x * 1e-3 for gradual decay.

:param buffer_size: size of the replay buffer
1_000_000 for large tasks, 100_000 for memory-limited systems.
Affects data diversity for training. Larger buffers improve learning but require more RAM.

:param learning_starts: how many steps of the model to collect transitions for before learning starts
100 (default), or 1000 for more initial exploration.

:param batch_size: Minibatch size for each gradient update
Larger batches lead to smoother updates but require more computation

:param tau: the soft update coefficient ("Polyak update", between 0 and 1)
Controls how fast the target networks track the main networks. Lower values smooth updates.

:param gamma: the discount factor (between 0 and 1)
High values emphasize long-term rewards; low values focus on immediate rewards.

:param train_freq: Update the model every ``train_freq`` steps. Alternatively pass a tuple of frequency and unit like ``(5, "step")`` or ``(2, "episode")``.
Defines how often the model is updated. Frequent updates can overfit to recent data.

:param gradient_steps: How many gradient steps to do after each rollout (see ``train_freq``)Set to ``-1`` means to do as many gradient steps as steps done in the environment during the rollout.
    
:param action_noise: the action noise type (None by default), this can help for hard exploration problem. Cf common.noise for the different action noise type.
use NormalActionNoise(mean=0, sigma=0.1

:param replay_buffer_class: Replay buffer class to use (for instance ``HerReplayBuffer``).If ``None``, it will be automatically selected.

:param replay_buffer_kwargs: Keyword arguments to pass to the replay buffer on creation.

:param optimize_memory_usage: Enable a memory efficient variant of the replay buffer at a cost of more complexity.
See https://github.com/DLR-RM/stable-baselines3/issues/37#issuecomment-637501195

:param policy_delay: Policy and target networks will only be updated once every policy_delay steps per training steps. The Q values will be updated policy_delay more often (update every training step).
default - 2

:param target_policy_noise: Standard deviation of Gaussian noise added to target policy (smoothing noise)

:param target_noise_clip: Limit for absolute value of target policy smoothing noise.

:param stats_window_size: Window size for the rollout logging, specifying the number of episodes to average the reported success rate, mean episode length, and mean reward over

:param tensorboard_log: the log location for tensorboard (if None, no logging)

:param policy_kwargs: additional arguments to be passed to the policy on creation

:param verbose: Verbosity level: 0 for no output, 1 for info messages (such as device or wrappers used), 2 for debug messages

:param seed: Seed for the pseudo random generators

:param device: Device (cpu, cuda, ...) on which the code should be run. Setting it to auto, the code will be run on the GPU if possible.

:param _init_setup_model: Whether or not to build the network at the creation of the instance
"""
