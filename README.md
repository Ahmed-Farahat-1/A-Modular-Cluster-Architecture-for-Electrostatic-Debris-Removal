# Orbital Maneuver Decision Dataset

Author: Ahmed S. Farahat  

---

## Overview

This folder contains the benchmark dataset generated for evaluating maneuver decision strategies in orbital conjunction scenarios.

The dataset is fully synthetic and was produced using a high-fidelity orbital simulation framework developed by the author. It is intended for research evaluation, benchmarking, and reproducibility purposes.

This folder contains only the generated dataset and configuration files required for review.

---

## Dataset Content

The folder includes:

- `maneuver_episodes.csv` – Main dataset in CSV format  
- `maneuver_episodes.parquet` – Optimized dataset format  
- `metadata.json` – Dataset statistics and feature definitions  
- `config.yaml` – Simulation configuration parameters  
- `assumptions.md` – Physical and modeling assumptions  

---

## Dataset Description

The dataset contains 500 simulated conjunction episodes including:

- Orbital state parameters
- Relative encounter geometry
- Uncertainty representation
- Collision probability metrics
- Environmental parameters
- Optimal maneuver solutions
- Decision labels

Each row represents one independent conjunction episode.

---

## Feature Categories

### 1. State Features
- Semi-major axis  
- Eccentricity  
- Inclination  
- RAAN  
- Argument of perigee  
- Spacecraft mass  
- Cross-sectional area  

### 2. Conjunction Features
- Miss distance  
- Relative velocity  
- RTN relative position components  
- RTN relative velocity components  

### 3. Uncertainty Features
- Position uncertainty  
- Velocity uncertainty  
- Combined covariance trace  

### 4. Risk Metrics
- Probability of collision (Pc)  
- Time to closest approach (TCA)  

### 5. Environmental Features
- F10.7 solar index  
- Ap geomagnetic index  
- Atmospheric density  
- Local object density  

### 6. Target / Optimization Outputs
- Optimal delta-v (R, T, N)  
- Delta-v magnitude  
- Maneuver type  

### 7. Labels
- maneuver_required  
- maneuver_feasible  

---

## Units

- Distance: km  
- Velocity: km/s (state) or m/s (delta-v)  
- Mass: kg  
- Area: m²  
- Time: seconds  
- Density: kg/m³  
- Probability: dimensionless  

---

## Simulation Assumptions

The dataset is generated under documented physical and operational assumptions detailed in `assumptions.md`, including:

- Earth geopotential up to J6
- Atmospheric drag modeling
- Solar radiation pressure
- Third-body perturbations
- Covariance-based collision probability estimation
- Impulsive maneuver modeling

This dataset does not include real operational conjunction data.

---

## Intended Use

This dataset is intended for:

- Research benchmarking  
- Decision-strategy evaluation  
- Autonomous maneuver planning studies  
- Reproducibility validation  

Not intended for operational collision avoidance or real-time mission decision-making.

---

## Reproducibility

All generation parameters are documented in `config.yaml`.  
Statistical summaries are provided in `metadata.json`.

Random seed control ensures reproducibility.

---

## Contact

Ahmed Farahat  
Research in Orbital Dynamics and Autonomous Space Systems
