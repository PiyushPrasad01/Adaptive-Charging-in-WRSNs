# Clustering Based Scheduling for Adaptive Charging in WRSNs
# Clustering-Based Scheduling for Adaptive Charging in WRSNs

## Overview

This project implements an intelligent, adaptive, and cluster-based multi-charger scheduling algorithm for **Wireless Rechargeable Sensor Networks (WRSNs)**. The focus is on maximizing sensor network lifespan, minimizing downtime (especially for high-consumption hotspot nodes), and efficiently utilizing mobile chargers through energy- and demand-aware strategies.

## Features

- **Adaptive Clustering:** Dynamically groups sensors by proximity and energy consumption, assigning a cluster to each mobile charger.
- **Hotspot Detection:** Identifies and prioritizes high-demand (hotspot) sensors; ensures hotspots lie at cluster intersections for joint coverage.
- **Multi-Charger Scheduling:** Assigns one mobile charger per cluster and coordinates multi-charger operations for critical sensors.
- **Priority-Based Scheduling:** Computes real-time priority for each sensor based on energy deficit, demand, and consumption rate.
- **TSP-Based Route Optimization:** Routes for chargers are optimized (bounded TSP) considering travel-energy constraints and guaranteed return-to-base capability.
- **Emergency Handling:** Detects at-risk sensors and immediately reroutes chargers to prevent node failures.
- **Scalable and Modular:** Designed for networks with 75–250+ sensors and multiple mobile chargers.


## Core Algorithmic Flow

1. **Sensor Profiling:**  
   For each sensor, calculate:
   - Current energy level and energy consumption rate
   - Projected depletion time
   - Demand for recharge: `Dk = E_max - E_current`
   - Hotspot flag if demand/consumption exceeds a threshold

2. **Cluster Formation:**  
   Clusters are built based on:
   - Sensor proximity
   - Current energy demand
   - Consumption rate  
   Intersections among clusters allowed only at hotspots to ensure multi-charger access.

3. **Mobile Charger Assignment:**  
   - One charger per cluster (minimizing overlap)
   - Special cooperation at hotspots shared among clusters

4. **Priority-Based Scheduling:**  
   At each scheduling interval, compute the sensor priority:
- Hotspot priorities may be boosted if covered by fewer chargers

5. **TSP-Constrained Route Planning:**  
- Each charger follows a travel plan visiting highest-priority sensors first
- Travel and charging energy budgets enforced, charger returns to base if needed

6. **Emergency Handling:**  
- Sensors close to depletion trigger emergency re-routing
- Nearest available charger is dispatched with minimal disruption

## Usage

1. **Clone the repository:**
 ```
 git clone https://github.com/yourusername/wrsn-clustering-charging.git
 cd wrsn-clustering-charging
 ```

2. **Configure the simulation parameters:**  
Edit `config.py` or use command-line options to set:
- Number of sensors/chargers
- Sensor energy profile and consumption rates
- Charger capacity, efficiency, etc.

3. **Run the main simulation:**
 ```
 python simulation.py --nodes 150 --chargers 4
 ```

4. **Visualize results:**  
- Placement accuracy (hotspot/non-hotspot/overall)
- Sensor uptime and dead-period prevention
- Example graphs and accuracy tables included

## Sample Results

| No. of Sensors | No. of Chargers | Hotspot Accuracy | Non-Hotspot Accuracy | Total Accuracy |
|:--------------:|:--------------:|:----------------:|:--------------------:|:--------------:|
|  75            |    4           |     85.71%       |      100.00%         |   98.67%       |
| 100            |    4           |     96.43%       |      93.06%          |   94.00%       |
| 150            |    4           |     86.36%       |      97.66%          |   96.00%       |
| 250            |    4           |     92.59%       |      99.55%          |   98.80%       |

## Future Directions

- Compare with alternative multi-charger algorithms for large-scale WRSNs.
- Further reduce computational/time complexity for ultra-dense deployments.
- Integrate real-world data and hardware-in-the-loop experiments.
- Extend strategy to urban IoT and industrial sensor deployments.

## References

WRSN scheduling, clustering, and adaptive charging algorithms are implemented as described in current research (see `references` in documentation).

## License

This project is open source under the **MIT License**.  
Contributions and suggestions are welcome!

---



