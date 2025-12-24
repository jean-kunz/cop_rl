# Project: cop_rl

## Overview
Reinforcement learning project focusing on planning and learning algorithms. Currently implements examples from CS234 course materials, specifically the Mars Rover Problem (MRP).

## Project Structure

```
cop_rl/
├── cop_rl/              # Main Python package
│   └── __init__.py
├── nbks/                # Jupyter notebooks
│   └── 1_mrp_planning.ipynb  # Mars Rover Problem planning example
├── pyproject.toml       # Project dependencies and configuration
├── Makefile             # Git remote configuration helpers
└── README.md
```

## Key Dependencies

- numpy >= 2.2.6
- matplotlib >= 3.10.8
- ipympl >= 0.9.8 (for interactive plots)
- ipykernel >= 7.1.0 (dev)

Python version: >= 3.10

## Current Work

### Mars Rover Problem (MRP) Planning
Location: `nbks/1_mrp_planning.ipynb`

This notebook demonstrates:
- **Policy Evaluation/Planning** with known model
- **Markov Reward Process (MRP)** with 7 states
- **Value Function Computation** using both:
  - Analytic solution: V = (I - γP)^(-1) * R
  - Iterative solution: V_k = R + γP * V_{k-1}
- **Visualization** of value convergence over iterations
- **Path Simulation** with animated Mars Rover movement

Key parameters:
- Discount factor (γ): 0.9
- States: s1 through s7
- Rewards: +1 at s1, +10 at s7 (goal)
- Transition matrix P: 7x7 stochastic matrix

## Development Setup

The project uses `uv` for dependency management (uv.lock present).

Virtual environment: `.venv/`

## Git Configuration

The Makefile provides helpers for GitHub SSH configuration:
- `make set_remote` - Set remote URL for github-jean-kunz
- `make login_github` - Verify SSH authentication

## Notes for Claude

1. **Project Type**: Educational/research RL implementation
2. **Code Style**: Scientific computing with numpy/matplotlib
3. **Visualization**: Uses matplotlib animations (FuncAnimation) for dynamic displays
4. **Learning Approach**: Demonstrates both mathematical/analytic solutions and iterative learning algorithms
5. **Current Focus**: Planning (model-based) rather than model-free learning

## Typical Tasks

- Implementing RL algorithms (planning, value iteration, policy iteration)
- Creating visualizations of learning dynamics
- Adding new MRP/MDP examples
- Comparing analytic vs iterative solutions
- Building animations for agent behavior
