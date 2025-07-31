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

## Repository Structure

