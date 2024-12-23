# LEF-Latent-Exploration-Framework

## Overview

Exploration remains a significant challenge in deep reinforcement learning (RL), particularly in complex environments with high-dimensional observations and sparse rewards. Traditional exploration strategies, like $\epsilon$-greedy and Boltzmann exploration, often fail in such environments, as they do not effectively support the discovery of far-off rewards. To address this, latent-based exploration is proposed to enhance exploration in high-dimensional state spaces by integrating latent representations. 


## Benchmark Comparison

Existing latent-based exploration methods across several metrics. The following table summarizes the key features of different algorithms:

| Algorithm       | Exploration Bonus                                     | Latent Space   | TAW | RSL | MEA |
|-----------------|-------------------------------------------------------|----------------|-----|-----|-----|
| RE3             |     | Random         | ✗   | ✗   | ✗   |
| RLE             |                | -        | ✗   | ✗   | ✗   |
| ICM             |  | Dynamics-based | ✗   | ✓   | ✗   |
| RIDE            | | Dynamics-based | ✗   | ✓   | ✗   |
| LIBERTY         |        | Metric-based   | ✗   | ✗   | ✗   |
| EME             |  | - | ✓   | ✗   | ✗   |
| E3B |   |   Dynamics-based |  ✓   | ✗   | ✗   |
| UnitD |   |   Dynamics-based |  ✓   | ✗   | ✗   |
| ... |   | ... | ...   | ...   | ..  |


## Installation

## To be released

