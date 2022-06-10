---
title: Key Ideas
---

# Key Ideas
## Reward Function

Finite-horizon undiscounted return:

$$
R(\tau)=\sum_{t=0}^{T} r_{t}
$$

Infinite-horizon discounted return:

$$
R(\tau)=\sum_{t=0}^{\infty} \gamma^{t} r_{t},\quad \gamma \in(0,1)
$$

## Value Functions

On-Policy Value Function:

$$
V^{\pi}(s)=\underset{\tau \sim \pi}{\mathbb{E}}\left[R(\tau) \mid s_{0}=s\right]
$$

## Bellman Equation

Bellman Optimality Equation for state-action value function:

$$
q_*(s, a) = \mathcal{R}^{a}_{s} + \gamma \sum_{s' \in S}\mathcal{P}^{a}_{ss'}\max_{a'}q_*(s',a')
$$


## References

- [OpenAI Spinning Up Documentation Part 1: Key Concepts in RL](https://spinningup.openai.com/en/latest/spinningup/rl_intro.html)