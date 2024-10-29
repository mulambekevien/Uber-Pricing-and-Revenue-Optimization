# Uber Pricing and Revenue Optimization Model
## Overview
This project is a pricing and revenue optimization model designed for Uber-like ride-hailing services. The model takes into account various factors such as base fares, traffic conditions, weather, demand, and surge multipliers to optimize pricing per ride and maximize total revenue. This solution is built in Excel, utilizing Excel’s Solver for optimization, and provides an example with 20 hours of operational data.

## Data Structure
The model uses the following columns in the data table:

- Hour: Represents the hour of the day.
- Base Fare (BF): The initial fare set per ride for each hour.
- Traffic (T): A qualitative description of traffic conditions (Low, Medium, High).
- Traffic Condition: A numerical factor associated with the traffic (e.g., 1 for Low, 1.2 for Medium, 1.5 for High).
- Weather (W): Description of weather conditions (Clear, Rainy, Stormy).
- Weather Adjusted: A multiplier based on weather conditions (1 for Clear, 1.1 for Rainy, 1.3 for Stormy).
- Event (E): Description of any special events that may influence demand (e.g., Concert, Sports).
- Event Impact: A multiplier that adjusts demand based on the presence of events (e.g., 1 for None, 1.3 for Concert, 1.5 for Sports).
- Demand (D): The initial demand estimate for each hour.
- Surge Multiplier (SM): A dynamic multiplier that adjusts based on demand and external conditions.
- Adjusted Demand: The adjusted demand after applying multipliers.
- Price per Ride: The final price per ride after applying the surge multiplier to the base fare.
- Revenue: The total revenue per hour, calculated as Adjusted Demand * Price per Ride.
- Total Revenue is calculated as the sum of revenue across all hours.

## How the Model Works
The model calculates the final price per ride and revenue based on the following formulas:

- Adjusted Demand: Demand * Traffic Condition * Weather Adjusted * Event Impact
- Price per Ride: Base Fare * Surge Multiplier
- Revenue: Adjusted Demand * Price per Ride
## Objective
The objective is to maximize Total Revenue by adjusting the Base Fare and Surge Multiplier within reasonable constraints.

## Constraints
To ensure realistic pricing, the following constraints were applied in Excel's Solver:

Base Fare (B2:B21):

- Minimum: $5.00
- Maximum: $20.00
- Surge Multiplier (G2:G21):

- Minimum: 1.0
- Maximum: 2.5
These constraints prevent extreme pricing while still allowing flexibility for demand-based adjustments.

### Running the Optimization
Set Objective: The Total Revenue cell (e.g., J101) is set as the Objective Cell in Solver.
### Choose Max to maximize revenue.
By Changing Variable Cells: Set B2:B21 and G2:G21 as the variable cells to be optimized.
Add Constraints: Apply constraints on Base Fare and Surge Multiplier as described above.
Click Solve: Run Solver to find the optimal base fares and surge multipliers.
#### Example Output
Using the input data, the model achieved a Total Revenue of $33,764.89.

### Conclusion
This model serves as a robust tool for pricing and revenue optimization in the ride-hailing industry. It allows adjustment of fare structures based on demand fluctuations, traffic, weather, and special events, helping maximize revenue while ensuring fares remain competitive.
