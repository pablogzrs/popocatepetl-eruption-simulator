# 🌋 Popocatépetl Eruption Simulator

MATLAB simulation of volcanic projectile trajectories from Popocatépetl volcano using Euler's method and drag force calculations.

## 📋 Overview

Physics-based simulator that models the trajectory of volcanic rocks ejected from Popocatépetl, considering air resistance and gravitational effects. Visualizes potential impact zones relative to nearby towns (Ecatzingo de Hidalgo and Amecameca de Juárez).

## ✨ Features

- Real-time trajectory visualization with animated projectile paths
- Monte Carlo simulation (3 random launches per run)
- Drag force calculations using spherical projectile model
- Geographic accuracy with actual distances and elevations
- Impact zone analysis for nearby settlements

## 🛠️ Technologies

- **Platform:** MATLAB R2019a or later
- **Numerical Method:** Euler's method for ODE solving
- **Physics:** Newtonian mechanics with fluid dynamics

## 📐 Physical Model

**Forces Considered:**
- Gravity: `F_g = -mg`
- Drag: `F_d = ½ρCdAv²`

**Equations of Motion:**
```matlab
ax = -(Cd·ρ·A·(vx/v)·v²) / (2m)
ay = -g - (Cd·ρ·A·(vy/v)·v²) / (2m)
```

**Parameters:**
- Air density (ρ): 1.225 kg/m³
- Drag coefficient (Cd): 0.47 (sphere)
- Gravity (g): 9.81 m/s²
- Time step (h): 0.1 s

## 🎯 Random Variables

Each simulation run generates 3 projectiles with randomized:
- **Initial velocity:** 100-300 m/s (vertical component)
- **Launch angle:** 45-135°
- **Rock density:** 2800-2900 kg/m³
- **Rock radius:** 0.32-3.0 m

## 🗺️ Geographic Data

**Volcano:**
- Height: 5,400 m
- Crater diameter: 900 m
- Base diameter: 25,000 m

**Towns:**
- **Ecatzingo de Hidalgo:** 14-18 km east
- **Amecameca de Juárez:** 13.5-15 km west

## 🚀 How to Run

```matlab
>> simulacionVolcan
```

**Output:**
- Animated trajectory plot
- Console output with projectile ranges
- Visual representation of danger zones

## 📊 Visualization

The simulation displays:
- 🔴 Red: Popocatépetl volcano (trapezoid model)
- ⚫ Black: Ecatzingo de Hidalgo
- 🟢 Green: Amecameca de Juárez
- 🟡 Yellow: Projectile trajectories
- 🔵 Blue: Sky background

## 🔬 Numerical Method

**Euler's Method Implementation:**
```
x(n+1) = x(n) + vx(n)·h
y(n+1) = y(n) + vy(n)·h
vx(n+1) = vx(n) + ax(n)·h
vy(n+1) = vy(n) + ay(n)·h
```

Time step: h = 0.1 seconds

## 📝 Results

Each run outputs:
```
La primera roca alcanzó una distancia de XXXX.XXXX metros desde el cráter.
La segunda roca alcanzó una distancia de XXXX.XXXX metros desde el cráter.
La tercera roca alcanzó una distancia de XXXX.XXXX metros desde el cráter.
```

## 🎓 Academic Context

**Application:** Computational physics / Numerical methods coursework  
**Topics Covered:**
- Projectile motion with air resistance
- Numerical integration (Euler's method)
- Monte Carlo simulation
- MATLAB visualization

## ⚠️ Limitations

- Assumes constant air density (actual decreases with altitude)
- Spherical projectile model (real rocks are irregular)
- No wind effects
- Simplified volcano geometry
- Euler's method has limited accuracy (better: RK4)

## 🔧 Customization

Modify these variables for different scenarios:
```matlab
v0_y = randi([100,300]);    % Initial velocity range
angulo_tiro = randi([45,135]); % Launch angle range
h = 0.1;                    % Time step
```

## 📚 References

- Real Popocatépetl dimensions and town distances
- Standard atmospheric model for air density
- Spherical drag coefficient (Cd = 0.47)

---

**Course:** Computational Physics / Numerical Methods  
**Institution:** ITESM  
**Method:** Euler's Integration  
**Language:** MATLAB
