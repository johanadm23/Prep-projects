# PhD Prep Projects

Two small computational projects exploring questions at the
intersection of neuroscience, AI, and consciousness science.

---

## Projects

### [Active Inference vs RL](./dishbrain/)

Compares three adaptive agents — reactive, reinforcement learning,
and active inference — on a hidden state-switching task. Tests whether
an agent that maintains beliefs about hidden world states outperforms
agents that simply react to rewards.

**Key result:** Active inference achieves 91% reward rate vs 64% for
RL and 52% for reactive, with near-instant recovery after environment
switches.

→ [`dishbrain/`](./dishbrain/)

---

### [Consciousness Credence Propagation](./consciousness-credence/)

A minimal Bayesian model of how confidence about consciousness in one
species can rationally inform confidence in others, using a population
similarity graph.

**Key result:** Populations at the periphery of the similarity graph
(fish, AI systems) remain uncertain even after substantial evidence
accumulates closer to the consensus — the model makes explicit why
some cases are structurally hard, not just empirically hard.

→ [`consciousness-credence/`](./consciousness-credence/)

---

## Setup

Each project is self-contained with its own dependencies. See the
README in each folder.

```bash
pip install numpy matplotlib scipy        # dishbrain
pip install numpy networkx matplotlib     # consciousness-credence
```
