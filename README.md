# LEF-Latent-Exploration-Framework

## Overview

Exploration remains a significant challenge in deep reinforcement learning (RL), particularly in complex environments with high-dimensional observations and sparse rewards. Traditional exploration strategies, like $\epsilon$-greedy and Boltzmann exploration, often fail in such environments, as they do not effectively support the discovery of far-off rewards. To address this, latent-based exploration is proposed to enhance exploration in high-dimensional state spaces by integrating latent representations. 


## Benchmark Comparison

Existing latent-based exploration methods across several metrics. The following table summarizes the key features of different algorithms:

| Algorithm       | Exploration Bonus                                     | Latent Space   | EET | SRL | TAM |
|-----------------|-------------------------------------------------------|----------------|-----|-----|-----|
| RE3             | $\log(\|\phi(s) - \phi(s)^{k\text{-NN}}\|_2 + 1)$     | Random         | ✗   | ✗   | ✗   |
| RLE             | $\phi(s)*\texttt{vector}(\phi(\cdot))$                | Random         | ✗   | ✗   | ✗   |
| ICM             | $\| \hat{\phi}(s^{\prime}) - \phi(s^{\prime}) \|_2^2$ | Dynamics-based | ✗   | ✓   | ✗   |
| RIDE            | $\|\phi(s^{\prime})-\phi(s)\|_2/\sqrt{N_{ep}(s^{\prime})}$ | Dynamics-based | ✗   | ✓   | ✗   |
| LIBERTY         | $[\gamma \phi(s^{\prime},s_0) - \phi(s,s_0)]$        | Metric-based   | ✗   | ✗   | ✗   |
| EME             | $\| \phi(s^{\prime})-\phi(s)\|_1*\zeta(r_s)|_1^{M}$  | Metric-based   | ✓   | ✗   | ✗   |
| LBF |   | unified | ✓   | ✓   | ✓   |



## Installation
 

