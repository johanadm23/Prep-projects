# Consciousness Credence Propagation

A small simulation exploring how confidence about consciousness in one
species can rationally inform confidence about other species, using
Bayesian belief updating and a similarity graph.

---

## The Question

We are highly confident humans are conscious. We are much less sure
about octopuses, fish, or AI systems. When new evidence arrives — say,
a study showing monkeys exhibit pain behaviour — how much should that
shift our confidence about other species?

This project builds a minimal formal model of that reasoning process.

---

## How It Works

Populations are represented as nodes in a graph. Each edge carries a
similarity score between 0 and 1 — how alike two populations are.
Each node holds a credence: a probability representing current
confidence that this population is conscious.

```
Humans (0.99)
    │ 0.92
Great Apes (0.50)
    │ 0.78
Monkeys (0.40)
   ├──────── Octopuses (0.30)
   └──────── Fish (0.25)
                  └──────── AI Systems (0.10)
```

When evidence arrives at a population, two things happen:

1. That population's credence updates via Bayes' rule
2. The update propagates outward to other populations, weakened
   in proportion to how dissimilar they are

So strong evidence about monkeys shifts our credence about great apes
a lot, and about AI systems very little.

---

## Results

After five pieces of evidence arriving at different populations:

| Population | Prior | Final |
|---|---|---|
| Humans | 0.99 | 1.00 |
| Great Apes | 0.50 | 0.84 |
| Monkeys | 0.40 | 0.75 |
| Octopuses | 0.30 | 0.56 |
| Fish | 0.25 | 0.38 |
| AI Systems | 0.10 | 0.14 |

![Results](ink_results.png)

AI Systems barely moves — not because the evidence is weak, but
because it sits at the end of two long low-similarity chains. The
model makes explicit why extending consciousness attributions to AI
is genuinely difficult, not just intuitively hard.

---

## Usage

```bash
pip install numpy networkx matplotlib
python simulation.py
```

Saves `ink_results.png` in the current directory.

---

## Project Structure

```
consciousness-credence/
├── simulation.py       # graph, update rule, plots
├── requirements.txt
├── ink_results.png     # generated on run
└── README.md
```
