# Dynamic-pricing-of-parking-lots
It is the final capstone project of the SA 2025. It includes the following contents:
1. A brief overview of the project
2. The tech stacks used
3. A detailed explanation of the project architecture and workflow

Brief Overview:

Urban parking spaces are a limited and highly demanded resource. Prices that remain static
throughout the day can lead to inefficiencies — either overcrowding or underutilization.
To improve utilization, dynamic pricing based on demand, competition, and real-time
conditions is crucial.
This project simulates such a system: participants will create an intelligent, data-driven
pricing engine for 14 parking spaces using real-time data streams, basic economic theory,
and ML models built from scratch, using only numpy, pandas libraries.
Urban parking demand fluctuates due to various factors like traffic, vehicle type, and events. Static pricing leads to under- or overutilization. Hence, dynamic pricing, updated in real-time, is proposed to maximize efficiency and fairness

Tech Stacks used:

+ Python (core language)

+ Numpy, Pandas, Matplotlib(data manipulation and modeling)

+ Pathway (real-time data ingestion and simulation)

+ Bokeh (real-time visualization)

+ Google Colab (execution environment)

Project Architecture and workflow:

1. Data Ingestion:
+ A simulator feeds timestamped data for 14 parking lots using Pathway.
+ Each timestamp has:
    1. Location (Lat-Long)

    2. Lot occupancy, capacity, and queue

    3. Environmental signals (traffic, event flags)

    4. Vehicle type

2. Feature Processing:

+ Normalize features for stable modeling.
+ Compute demand using weighted feature sums.
+ Calculate proximity matrix for competitive pricing.

3. Pricing Models:

    Model 1:
    Basic linear model:
    Price_t+1 = Price_t + α × (Occupancy / Capacity)

    Model 2:
    Demand-driven dynamic model:
    Demand = α×(Occ/Cap) + β×Queue − γ×Traffic + δ×Event + ε×VehicleType
    Price_t = Base × (1 + λ × NormalizedDemand)
    Ensures smooth variation between 0.5x to 2x base price.


