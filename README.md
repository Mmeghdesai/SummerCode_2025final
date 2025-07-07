# Model 1 – Linear Pricing Strategy

This notebook implements a basic **linear dynamic pricing model** based on occupancy and queue length using a fixed mathematical formula.
The pricing is derived from a formula:
price = BASE_PRICE + α * occupancy_ratio + β * queue_length

- **Base Price:** $10.00  
- **Occupancy Ratio:** Occupancy / Capacity  
- **α (Alpha):** 8.0  
- **β (Queue Weight):** 0.5

Features

- Calculates a **target price** using a simple linear equation.
- Computes **Mean Absolute Error (MAE)**.
- Visualizes predicted vs. actual price performance (if included).

usage
1. Load the dataset `dataset.csv`.
2. Run the cells to generate predicted prices.
3. Adjust `alpha` or `queue_weight` to tune model behavior.


- Ideal for simple real-time pricing where computational simplicity is a priority.
- Does not consider complex temporal, traffic, or vehicle factors.
# Model 2 – AI-Based Dynamic Pricing with XGBoost

This notebook builds an **advanced dynamic pricing model** using **XGBoost**, driven by a **mathematical demand function** and real-time features like time, traffic, and vehicle type.

Core Concept

The model calculates a **demand factor** influenced by:

- Occupancy ratio
- Queue length
- Traffic conditions
- Day of the week
- Hour of the day
- Vehicle type
- Special days

The target price is:
target_price = BASE_PRICE × demand_factor

Where:
- Demand factor is computed using non-linear logic and smoothed using a sigmoid.
- Output is normalized between `0.6x` to `2.0x` of base price.

Model Training

- Model: `XGBRegressor`
- Features used: 8 total including encoded categories
- Evaluation Metric: RMSE
- Visuals: Feature importance, hourly pattern, actual vs predicted

Real-Time Pricing API

A Python function `dynamic_pricing_function(...)` is included for real-time use. Inputs include:



