
# Inventory Analysis for Small Businesses Using Python


Managing inventory effectively is crucial for the success of any small business. This blog post will cover key aspects of inventory analysis including safety stock, demand planning, and optimization. We'll use Python for our analysis and visualizations.

## Table of Contents

1. [Safety Stock](#safety-stock)
2. [Demand Planning](#demand-planning)
3. [Optimization](#optimization)
4. [Example Dataset](#example-dataset)
5. [Conclusion](#conclusion)

## Safety Stock

Safety stock is an additional quantity of an item held in the inventory to reduce the risk of stockouts. This is especially important when dealing with demand variability and lead time fluctuations.

### Calculating Safety Stock

Safety stock can be calculated using the following formula:

\[ \text{Safety Stock} = Z \times \sigma_d \times \sqrt{L} \]

where:
- \( Z \) = Z-score (service level)
- \( \sigma_d \) = standard deviation of demand
- \( L \) = lead time

```python
import numpy as np
import matplotlib.pyplot as plt

# Example data
demand = [100, 120, 130, 110, 90, 150, 130, 140, 160, 170]
lead_time = 5  # days
z_score = 1.65  # for 95% service level

# Calculate standard deviation of demand
std_dev_demand = np.std(demand)

# Calculate safety stock
safety_stock = z_score * std_dev_demand * np.sqrt(lead_time)
print(f"Safety Stock: {safety_stock:.2f}")

# Plotting demand
plt.plot(demand, marker='o')
plt.title('Demand over Time')
plt.xlabel('Time Period')
plt.ylabel('Demand')
plt.grid(True)
plt.show()
