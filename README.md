#  Statistical Engineering & Simulation Project

## Project Overview

This project implements a pure Python statistical engine from scratch and applies it to real-world data analysis and probability simulation.

The system is capable of:
- Computing statistical measures (mean, median, mode)
- Measuring data spread (variance, standard deviation)
- Detecting outliers
- Simulating probability using Monte Carlo methods
- Demonstrating the Law of Large Numbers (LLN)

---

## Core Features

### 1. Central Tendency

- **Mean**
  - Formula: sum(data) / n

- **Median**
  - Odd dataset → middle value  
  - Even dataset → average of two middle values  

- **Mode**
  - Returns all most frequent values (supports multimodal data)
  - Returns a message if all values are unique

---

### 2. Dispersion

#### Variance

- **Population Variance**
  σ² = Σ(x - μ)² / n

- **Sample Variance (Bessel’s Correction)**
  s² = Σ(x - x̄)² / (n - 1)

#### Standard Deviation

- σ = √variance
- Represents spread in same unit as data

---

### 3. Outlier Detection

- Uses **Z-score method**
- Formula:
  z = (x - mean) / std

- Values with |z| > 2 are considered outliers

---

### 4. Error Handling

- Handles empty datasets
- Validates numeric-only input
- Raises clear error messages

---

##  Monte Carlo Simulation

### Scenario

A server has a **4.5% (0.045)** probability of crashing per day.

### Simulation Logic

- Generate random number between 0 and 1
- If random < 0.045 → crash occurs
- Repeat for many days

### Function

simulate_crashes(days)

Returns:
crashes / days

---

##  Law of Large Numbers (LLN)

### Observation

- Small sample (30 days) → unstable results  
- Large sample (10,000 days) → stable results  

### Conclusion

As the number of trials increases, the simulated probability approaches the true probability.

---

##  Real-World Insight

Using small datasets is dangerous because:
- Results vary due to randomness
- Leads to incorrect predictions

Example:
A startup using 30 days of data may miscalculate server failure rates and budget incorrectly.

---

##  Project Structure


statistical_engine/
│
├── data/
│ └── sample_salaries.json
├── src/
│ ├── stat_engine.py
│ └── monte_carlo.py
├── tests/
│ └── test_stat_engine.py
├── README.md
└── main.py
