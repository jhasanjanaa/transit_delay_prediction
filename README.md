# Public Transit Delay Prediction

> Predicting whether public transit will be delayed using schedules, weather, traffic & city events.
>
> 
Dataset Source - Kaggle Dataset


Dataset Link - https://www.kaggle.com/datasets/khushikyad001/public-transport-delays-with-weather-and-events

---

###  Summary & Workflow
* **Goal**: Binary classification (`1 = Delayed`, `0 = On-Time`).
* **Zero Leakage**: Dropped actual arrival & departure delay times prior to training.
* **Feature Engineering**: Extracted scheduled departure hour, calculated trip duration, and flagged public events.
* **Class Imbalance**: Since **75% of trips were delayed**, unweighted models got a deceptive 75% accuracy by only predicting delays. Using `class_weight="balanced"` fixed this and enabled real predictions for on-time trips.

---

### Results

| Model | Accuracy | On-Time Recall | Delayed Recall |
| :--- | :---: | :---: | :---: |
| **Logistic Regression** | 72.8% | 2% | 96% |
| **Random Forest (Default)** | 75.0% | 0% | 100% |
| **Random Forest (Balanced) ** | **Balanced** | **40%+** | **70%+** |

---

### Key Delay Factors
1. **Trip Duration & Hour**: Longer journeys and rush hours compound delays.
2. **Traffic Congestion**: Major cause of delays for buses and trams.
3. **Bad Weather**: High wind speeds and heavy rain.
4. **Events**: High-attendance concerts and sports matches.

---

**Tech Stack**: `Python` • `pandas` • `scikit-learn` • `seaborn`

