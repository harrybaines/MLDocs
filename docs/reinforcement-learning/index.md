# Bellman Equation

Bellman Optimality Equation for state-action value function:

$$
q_*(s, a) = \mathcal{R}^{a}_{s} + \gamma \sum_{s' \in S}\mathcal{P}^{a}_{ss'}\max_{a'}q_*(s',a')
$$