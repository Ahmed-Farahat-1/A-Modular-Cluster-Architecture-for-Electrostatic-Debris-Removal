# Simulation Assumptions and Limitations

## Physical Models

### Orbital Dynamics
- **Gravitational Model**: Earth geopotential up to J6 harmonics
- **Atmospheric Drag**: Exponential atmosphere with altitude-dependent scale heights
- **Solar Radiation Pressure**: Cannonball model with shadow function
- **Third-Body Perturbations**: Sun and Moon (simplified ephemeris)
- **Numerical Integration**: DOP853 (8th order Runge-Kutta)

### Atmospheric Model
- Base model: NRLMSISE-00 approximation
- Solar activity scaling via F10.7 index
- No real-time space weather data

### Collision Probability
- Method: Chan's 2D formula with Alfano encounter plane projection
- Assumes Gaussian uncertainty distribution
- Hard body radius: 15 meters (default)

## Maneuver Planning

### Decision Strategies
1. **Fixed Miss Distance**: Maneuver if miss < 1 km
2. **Pc Threshold**: Maneuver if Pc > 1e-4
3. **Fuel Minimizing**: Minimum delta-v to achieve safety

### Execution Model
- Impulsive maneuvers only (no finite burns)
- Magnitude error: 1% (1-sigma)
- Pointing error: 1 degree (1-sigma)
- Fuel consumption: Tsiolkovsky equation with Isp = 220s

## Dataset Generation

### Conjunction Scenarios
- Synthetic conjunctions generated from real orbital catalog
- Miss distances: 50m to 10 km
- Warning times: 1 to 24 hours
- 30% high-risk scenarios (Pc > 1e-4)

### Limitations
1. No operational constraints (ground contact, power, etc.)
2. No multi-conjunction scenarios
3. No secondary maneuver capability
4. Simplified covariance propagation
5. No real conjunction data (CDMs)

## Reproducibility
- Random seed: 42 (configurable)
- All parameters documented in config.yaml
- Source code version controlled

## Intended Use
This dataset is designed for:
- Training AI-based maneuver decision systems
- Benchmarking against classical strategies
- Research in autonomous space operations

NOT intended for:
- Operational collision avoidance
- Real-time decision support
- Safety-critical applications without validation
