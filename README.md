# PG is all you need!
Step-by-step tutorials PG algorithms

## Contents
1. REINFORCE
2. Advantage Actor-Critic (A2C)
3. Generalized Advantage Estimation (GAE)
4. Proximal Policy Optimization Algorithms (PPO)
5. Deep Deterministic Policy Gradient (DDPG)
6. Twin Delayed Deep Deterministic Policy Gradient Algorithm (TD3)
7. Soft Actor-Critic (SAC)
8. DDPG from Demonstration (DDPGfD)
9. Behavior Cloning (with DDPG)

## Environment
### Pendulum-v0
<img src="https://media.giphy.com/media/gHJavzDcIQ0Z8WCk97/giphy.gif" width="200" height="140"/>

Reference: [OpenAI gym Pendulum-v0](https://github.com/openai/gym/wiki/Pendulum-v0)

### Observation

Type: Box(3)

Num | Observation  | Min | Max  
----|--------------|-----|----   
0   | cos(theta)   | -1.0| 1.0
1   | sin(theta)   | -1.0| 1.0
2   | theta dot    | -8.0| 8.0


### Actions

Type: Box(1)

Num | Action  | Min | Max  
----|--------------|-----|----   
0   | Joint effort | -2.0| 2.0

### Reward

The precise equation for reward:

    -(theta^2 + 0.1*theta_dt^2 + 0.001*action^2)

Theta is normalized between -pi and pi. Therefore, the lowest cost is `-(pi^2 + 0.1*8^2 + 0.001*2^2) = -16.2736044`, and the highest cost is `0`. In essence, the goal is to remain at zero angle (vertical), with the least rotational velocity, and the least effort. Max steps per an episode is 200 steps.

## Installation


## Related Papers
0. R. Sutton and A. Barto, Reinforcement Learning: An Introduction, 2nd ed., MIT Press, 2018.
1. [R. J. Williams et al., "Simple statistical gradient-following algorithms for connectionist reinforcement learning.", Machine Learning, 8(3), 229-256, 1992.](https://link.springer.com/content/pdf/10.1007/BF00992696.pdf)
2. [M. Babaeizadeh et al., "Reinforcement learning through asynchronous advantage actor-critic on a gpu.", International Conference on Learning Representations, 2017.](https://arxiv.org/pdf/1611.06256)
3. [J. Schulman et al., "High-Dimensional Continuous Control Using Generalized Advantage Estimation.", arXiv preprint arXiv:1506.02438, 2015b.](https://arxiv.org/pdf/1506.02438)
4. [J. Schulman et al., "Proximal Policy Optimization Algorithms." arXiv preprint arXiv:1707.06347, 2017.](https://arxiv.org/abs/1707.06347.pdf)
5. [T. P. Lillicrap et al., "Continuous control with deep reinforcement learning." arXiv preprint arXiv:1509.02971, 2015.](https://arxiv.org/pdf/1509.02971.pdf)
6. [A. Nair et al., "Overcoming Exploration in Reinforcement Learning with Demonstrations." arXiv preprint arXiv:1709.10089, 2017.](https://arxiv.org/pdf/1709.10089.pdf)
7. [T.  Haarnoja et al., "Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor." arXiv preprint arXiv:1801.01290, 2018.](https://arxiv.org/pdf/1801.01290.pdf)
8. [M. Vecerik et al., "Leveraging Demonstrations for Deep Reinforcement Learning on Robotics Problems with Sparse Rewards."arXiv preprint arXiv:1707.08817, 2017](https://arxiv.org/pdf/1707.08817.pdf)
9. [A. Nair et al., "Overcoming Exploration in Reinforcement Learning with Demonstrations." arXiv preprint arXiv:1709.10089, 2017.](https://arxiv.org/pdf/1709.10089.pdf)

