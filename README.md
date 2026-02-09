# Road-Safety-ML-Analysis
An end-to-end predictive analytics framework for road safety. Features a multi-source ETL pipeline integrating telematics, weather, and geospatial data with a Random Forest model (99.8% Accuracy) for hazardous maneuver detection.

# Executive Summary
This project develops a data-driven risk assessment framework for road safety by extending traditional over-speeding algorithms with high-frequency telematics data. Developed as an MSc Dissertation at the University of East London, this research earned a Pass with Distinction (84.6%).

# The Analytical Problem 
Standard safety models often focus solely on speed and duration, overlooking aggressive driving behaviors such as sharp turns. This research bridges that gap by integrating lateral acceleration ($m/s^2$), geospatial speed limits, and environmental data to detect and classify hazardous maneuvers with high precision.

# Technical Methodology
* Multi-Source ETL Pipeline: Integrated three distinct datasets—Telematic Devices, Historical Weather, and Geospatial Speed Limits—using time-series alignment and coordinate normalization.
Feature Engineering: 
* Converted raw sensor data into lateral G-force ($m/s^2$) to detect sharp turn signatures.
  * Developed a weighted Total Risk Score incorporating over-speeding duration, weather conditions (Foggy, Wet, Icy), and high-risk temporal factors (Night-driving).
Machine Learning Optimization:
* Handled class imbalance for rare hazardous events using RandomOverSampler.
  * Optimized a Random Forest Classifier via GridSearchCV, outperforming Logistic Regression and KNN benchmarks.

# Performance Metrics
Validated on a clean, unique-feature split to ensure professional predictive integrity:
* Model Accuracy: 99.8%
* F1-Score: 0.997
* Recall: 99.8%.
* Note on Accuracy: The near-perfect score demonstrates the effectiveness of the physics-based thresholds used to classify maneuvers.

# Technical Challenges & Resolution

* Data Leakage Mitigation: Identified 224 overlapping samples during initial model validation. Resolved this by implementing a unique-signature split, ensuring the model generalizes to new driving data rather than memorizing duplicate signals.
* Scalability: The pipeline is architected to process high-velocity telematic streams, making it applicable for real-time fleet management and insurance risk modeling.

# Documentation & Tools
* Languages: Python
* Libraries: Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn, Imbalanced-Learn
