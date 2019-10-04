[![All Contributors](https://img.shields.io/badge/all_contributors-3-orange.svg?style=flat-square)](#contributors)
# PG is all you need!
This is a step-by-step tutorial for Policy Gradient algorithms from A2C to SAC, including learning acceleration methods using demonstrations for treating real applications with sparse rewards. Every chapter contains both of theoretical backgrounds and object-oriented implementation. Just pick any topic in which you are interested, and learn! You can execute them right away with Colab even on your smartphone.

Please feel free to open an issue or a pull-request if you have any idea to make it better. :)

## Contents
1. Advantage Actor-Critic (A2C) [[NBViewer](https://nbviewer.jupyter.org/github/MrSyee/pg-is-all-you-need/blob/master/01.A2C.ipynb)] [[Colab](https://colab.research.google.com/github/MrSyee/pg-is-all-you-need/blob/master/01.A2C.ipynb)]
2. Proximal Policy Optimization Algorithms (PPO) [[NBViewer](https://nbviewer.jupyter.org/github/MrSyee/pg-is-all-you-need/blob/master/02.PPO.ipynb)] [[Colab](https://colab.research.google.com/github/MrSyee/pg-is-all-you-need/blob/master/02.PPO.ipynb)]
3. Deep Deterministic Policy Gradient (DDPG) [[NBViewer](https://nbviewer.jupyter.org/github/MrSyee/pg-is-all-you-need/blob/master/03.DDPG.ipynb)] [[Colab](https://colab.research.google.com/github/MrSyee/pg-is-all-you-need/blob/master/03.DDPG.ipynb)]
4. Twin Delayed Deep Deterministic Policy Gradient Algorithm (TD3) [[NBViewer](https://nbviewer.jupyter.org/github/MrSyee/pg-is-all-you-need/blob/master/04.TD3.ipynb)] [[Colab](https://colab.research.google.com/github/MrSyee/pg-is-all-you-need/blob/master/04.TD3.ipynb)]
5. Soft Actor-Critic (SAC) [[NBViewer](https://nbviewer.jupyter.org/github/MrSyee/pg-is-all-you-need/blob/master/05.SAC.ipynb)] [[Colab](https://colab.research.google.com/github/MrSyee/pg-is-all-you-need/blob/master/05.SAC.ipynb)]
6. DDPG from Demonstration (DDPGfD) [[NBViewer](https://nbviewer.jupyter.org/github/MrSyee/pg-is-all-you-need/blob/master/06.DDPGfD.ipynb)] [[Colab](https://colab.research.google.com/github/MrSyee/pg-is-all-you-need/blob/master/06.DDPGfD.ipynb)]
7. Behavior Cloning (with DDPG) [[NBViewer](https://nbviewer.jupyter.org/github/MrSyee/pg-is-all-you-need/blob/master/07.BC.ipynb)] [[Colab](https://colab.research.google.com/github/MrSyee/pg-is-all-you-need/blob/master/07.BC.ipynb)]

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

## Prerequisites

This repository is tested on [Anaconda](https://www.anaconda.com/distribution/) virtual environment with python 3.6.1+
```
$ conda create -n pg-is-all-you-need python=3.6.1
$ conda activate pg-is-all-you-need
```

## Installation
First, clone the repository.
```
git clone https://github.com/MrSyee/pg-is-all-you-need.git
cd pg-is-all-you-need
```

Secondly, install packages required to execute the code. Just type:
```
make dep
```
## Development
Install packages required to develop the code:
```
make dev
```
If you want to check the difference of jupyter files that you modified, use [nbdime](https://github.com/jupyter/nbdime):
```
nbdiff-web
```

## Related Papers
1. [R. J. Williams et al., "Simple statistical gradient-following algorithms for connectionist reinforcement learning.", Machine Learning, 8(3), 229-256, 1992.](https://link.springer.com/content/pdf/10.1007/BF00992696.pdf)
2. [M. Babaeizadeh et al., "Reinforcement learning through asynchronous advantage actor-critic on a gpu.", International Conference on Learning Representations, 2017.](https://arxiv.org/pdf/1611.06256)
3. [J. Schulman et al., "Proximal Policy Optimization Algorithms." arXiv preprint arXiv:1707.06347, 2017.](https://arxiv.org/abs/1707.06347.pdf)
4. [T. P. Lillicrap et al., "Continuous control with deep reinforcement learning." arXiv preprint arXiv:1509.02971, 2015.](https://arxiv.org/pdf/1509.02971.pdf)
5. [T.  Haarnoja et al., "Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor." arXiv preprint arXiv:1801.01290, 2018.](https://arxiv.org/pdf/1801.01290.pdf)
6. [M. Vecerik et al., "Leveraging Demonstrations for Deep Reinforcement Learning on Robotics Problems with Sparse Rewards."arXiv preprint arXiv:1707.08817, 2017](https://arxiv.org/pdf/1707.08817.pdf)
7. [A. Nair et al., "Overcoming Exploration in Reinforcement Learning with Demonstrations." arXiv preprint arXiv:1709.10089, 2017.](https://arxiv.org/pdf/1709.10089.pdf)

## Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->
<table>
  <tr>
    <td align="center"><a href="https://www.linkedin.com/in/kyunghwan-kim-0739a314a/"><img src="https://avatars3.githubusercontent.com/u/17582508?v=4" width="100px;" alt="Kyunghwan Kim"/><br /><sub><b>Kyunghwan Kim</b></sub></a><br /><a href="https://github.com/MrSyee/pg-is-all-you-need/commits?author=MrSyee" title="Code">💻</a> <a href="https://github.com/MrSyee/pg-is-all-you-need/commits?author=MrSyee" title="Documentation">📖</a></td>
    <td align="center"><a href="https://www.linkedin.com/in/curt-park/"><img src="https://avatars3.githubusercontent.com/u/14961526?v=4" width="100px;" alt="Jinwoo Park (Curt)"/><br /><sub><b>Jinwoo Park (Curt)</b></sub></a><br /><a href="https://github.com/MrSyee/pg-is-all-you-need/commits?author=Curt-Park" title="Code">💻</a> <a href="https://github.com/MrSyee/pg-is-all-you-need/commits?author=Curt-Park" title="Documentation">📖</a></td>
    <td align="center"><a href="https://mclearninglab.tistory.com"><img src="https://avatars0.githubusercontent.com/u/43226417?v=4" width="100px;" alt="Mincheol Kim"/><br /><sub><b>Mincheol Kim</b></sub></a><br /><a href="https://github.com/MrSyee/pg-is-all-you-need/commits?author=mclearning2" title="Code">💻</a> <a href="https://github.com/MrSyee/pg-is-all-you-need/commits?author=mclearning2" title="Documentation">📖</a></td>  
  </tr>
</table>

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
