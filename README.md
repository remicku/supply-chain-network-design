# Supply Chain Network Design

## Problem

The CFLP (Capacitated Facility Location Problem) consists of choosing which
warehouses to open among a set of candidates and assigning each customer to an
open warehouse, minimizing fixed opening costs and transport costs under
capacity constraints.

## Implemented approaches

| Method | Type | Description |
|---|---|---|
| CP-SAT | Exact | Constraint programming model via OR-Tools |
| MILP | Exact | Mixed-integer linear programming via PuLP (CBC) |
| GRASP | Metaheuristic | Greedy randomized construction + local search |
| ALNS | Metaheuristic | Adaptive destroy/repair + Simulated Annealing |

## Extensions

- **Robustness**: worst-case model for uncertain demand (`uncertainty` parameter)
- **Sustainability**: diesel/electric choice with a configurable CO₂ budget

## Data

CAP instances from Beasley's OR-Library (1988):
`data/cap71.txt`, `data/cap101.txt`, `data/cap131.txt`, `data/cap134.txt`, `data/capopt.txt`

Source: http://people.brunel.ac.uk/~mastjjb/jeb/orlib/capinfo.html

## Installation

```bash
uv sync
```

## Usage

Open `project.ipynb` and run the cells in order.

## Main results (cap134, 50 warehouses, 50 customers)

| Method | Cost | Gap | Time |
|---|---|---|---|
| CP-SAT | 928,941.75 | 0.000% | 0.21s |
| MILP | 928,941.75 | 0.000% | 0.14s |
| GRASP | 928,941.75 | 0.000% | 2.03s |
| ALNS | 945,438.08 | 1.776% | 1.55s |

## References

- Beasley, J.E. (1988). OR-Library. Brunel University.
- Melo et al. (2009). Facility Location and Supply Chain Management. EJOR.
- ADEME (2022). Transport emission factors.
