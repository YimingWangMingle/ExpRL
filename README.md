# LEF-Latent-Exploration-Framework

# Temporal-Aware Latent Exploration (TALE)

## Overview

Exploration remains a significant challenge in deep reinforcement learning (RL), particularly in complex environments with high-dimensional observations and sparse rewards. Traditional exploration strategies, like $\epsilon$-greedy and Boltzmann exploration, often fail in such environments, as they do not effectively support the discovery of far-off rewards. To address this, we propose **Temporal-Aware Latent Exploration (TALE)**, a novel method that enhances exploration in high-dimensional state spaces by integrating temporal and latent representations. Our approach aims to bridge the gap between classical exploration methods and modern reinforcement learning challenges.

## Motivation

Exploration in RL can be especially challenging when rewards are sparse or entirely absent. Classical methods, such as $\epsilon$-greedy and Boltzmann exploration, rely on random action selection but struggle in complex environments where rewards are distant from the initial states. More recent methods, like count-based and curiosity-driven exploration, introduce intrinsic rewards based on state novelty to incentivize exploration.

However, these methods often fail in environments with high-dimensional state spaces or sparse rewards, where intrinsic rewards become ineffective or collapse into noise. This limits their ability to guide exploration effectively, especially over long time horizons. 

## Related Work

Several exploration methods have been proposed to tackle the problem of state novelty:

- **Intrinsic Curiosity Module (ICM)**: Uses the prediction error of an inverse dynamics model in the latent space as an intrinsic reward.
- **RIDE**: Defines intrinsic rewards based on the distance between embeddings of consecutive states in a latent space.
- **RE3** and **RLE**: Use random encoders and latent space embeddings to define intrinsic rewards.
- **LIBERTY** and **EME**: Use metric-based encoders to compute state differences, enhancing exploration by generating bisimulation-like latent representations.

However, many of these approaches fail to generalize effectively to environments with high-dimensional observations and sparse rewards. A key limitation is their reliance on temporal-difference updates, which only use one-step transition information, limiting their ability to capture long-term dependencies.

## TALE: Temporal-Aware Latent Exploration

To overcome these challenges, we propose **TALE**, a method that incorporates **temporal-aware** latent representations into the exploration process. Unlike previous methods that only consider immediate transitions, TALE captures long-term dependencies, enabling more effective exploration in sparse-reward and high-dimensional environments.

### Key Contributions

- **Temporal-Aware Latent Space**: By incorporating temporal information, TALE learns long-term behavioral representations that span from present to future states.
- **Improved Exploration**: The method combines state novelty with temporal information, enhancing exploration efficiency, especially in complex, high-dimensional environments.
- **Robust to Sparse Rewards**: TALE maintains effective exploration even in sparse-reward settings where other methods fail due to collapsing representations.

## Benchmark Comparison

We compare TALE with existing latent-based exploration methods across several metrics. The following table summarizes the key features of different algorithms:

| Algorithm       | Intrinsic Reward                                      | Latent Space   | EET | SRL | TAM |
|-----------------|-------------------------------------------------------|----------------|-----|-----|-----|
| RE3             | $\log(\|\phi(s) - \phi(s)^{k\text{-NN}}\|_2 + 1)$     | Random         | ✗   | ✗   | ✗   |
| RLE             | $\phi(s)*\texttt{vector}(\phi(\cdot))$                | Random         | ✗   | ✗   | ✗   |
| ICM             | $\| \hat{\phi}(s^{\prime}) - \phi(s^{\prime}) \|_2^2$ | Dynamics-based | ✗   | ✓   | ✗   |
| RIDE            | $\|\phi(s^{\prime})-\phi(s)\|_2/\sqrt{N_{ep}(s^{\prime})}$ | Dynamics-based | ✗   | ✓   | ✗   |
| LIBERTY         | $[\gamma \phi(s^{\prime},s_0) - \phi(s,s_0)]$        | Metric-based   | ✗   | ✗   | ✗   |
| EME             | $\| \phi(s^{\prime})-\phi(s)\|_1*\zeta(r_s)|_1^{M}$  | Metric-based   | ✓   | ✗   | ✗   |
| **TALE (ours)** | $\| \phi((s^{\prime},\Phi(s^{\prime}))-\phi(s,\Phi(s))\|_1$ | Temporal Metric-based | ✓   | ✓   | ✓   |

### Notation

- **EET**: Embodied Exploration Tasks
- **SRL**: Stable Representation Learning
- **TAM**: Temporal Aware Mechanism
- **$\phi$**: State feature encoder
- **$\hat{\phi}$**: Predicted estimate of forward dynamics model
- **$N_{ep}(s)$**: Episodic count of visits to state $s$
- **$\zeta(r_s)$**: Variance of predictions from an ensemble of reward models
- **$M$**: Maximum reward scaling

## Conclusion

**TALE** introduces a novel approach to latent-based exploration by incorporating temporal awareness into the exploration process. Our method significantly improves exploration efficiency in high-dimensional and sparse-reward environments, addressing the shortcomings of existing techniques. We believe this approach has the potential to push the boundaries of RL exploration in challenging environments.

## Installation

```bash
pip install tale-exploration
