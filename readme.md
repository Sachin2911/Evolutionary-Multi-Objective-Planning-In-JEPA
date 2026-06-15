# Evolutionary Multi-Objective Planning in Joint-Embedding Predictive Architectures for Safe Reinforcement Learning

**Using selection pressure as an alternative to hand-crafted reward penalties**

Honours research project, University of the Witwatersrand  
**Author:** Sachin Mohan (2699183) · **Supervisor:** Geraud Nangue Tasse

## Overview

Safe reinforcement learning usually depends on hand-crafted reward penalties or cost functions — both fragile and hard to tune. This project explores an alternative: pairing a [JEPA](https://arxiv.org/abs/2206.00647) world model with a multi-objective evolutionary planner (NSGA-II) that searches over action sequences in latent space.

Instead of collapsing task performance and safety into one scalar reward, the planner returns a **Pareto front** of trade-offs. The safety-performance balance becomes a deployment-time choice, not something fixed during training. Safety signals come from the world model itself — prediction surprise, latent smoothness, and learned probes — rather than hand-designed cost functions.

## Approach

A frozen [LeWorldModel](https://github.com/lucas-maes/le-wm) encoder and predictor roll out candidate plans in latent space. NSGA-II optimises for task achievement and safety separately, returning a set of non-dominated plans. The selected plan is executed under model predictive control before replanning.

Evaluation targets Push-T and Reacher (with OGBench-Cube as an optional generalisation test), compared against penalty-tuned CEM and constrained RL baselines.

## Status

Early development. Full details in [`docs/ResearchProposal.pdf`](docs/ResearchProposal.pdf).  
**Timeline:** May 2026 – November 2026
