# GNN-Aided-Modelling-of-Granular-Materials
This project explores the use of Graph Neural Networks (GNNs) to model and predict interparticle normal contact forces in granular assemblies under uniaxial compression.
Traditional Discrete Element Method (DEM) simulations are computationally expensive when modeling force chains in large particle systems. By leveraging GNNs, we aim to provide a faster, accurate, and scalable alternative for force prediction in particulate systems. 

**I have shared here, snippets from my Python notebook containing the full GNN code for the project, to show the broad working and results. It may not be replicated or used without obtaining permission.**

**Objectives:**
- Develop a GNN-based model to predict normal contact forces in granular materials.
- Preprocess and structure large-scale DEM datasets (~10 million data points) into node/edge feature graphs.
- Incorporate particle dynamics (position, velocity, diameter, relative distances) to improve predictive accuracy.
- Validate the GNN’s predictions against DEM simulations and benchmark results from prior research (Cheng & Wang, 2022).

**Methodology:**

1. Data Procurement & Preprocessing:
- 10 granular assemblies (~4000 particles each).
- Generated node and edge CSV files for all configurations (~4000 files, ~10M data points).
- Node features: particle size, position, velocity, number of contacts.
- Edge features: distance, relative velocities, tangential & normal forces.

2. Model Architecture:
- Implemented a message-passing GNN (encode → process → decode).
- Aggregated node and edge features to update graph representations.
- Optimized using Adam optimizer, feature scaling, and hyperparameter tuning.

3. Training & Evaluation:
- Trained on 5 assemblies, validated on 1, tested on 4.
- Used ~100,000 representative data points per strain step to manage large-scale computation.
- Loss function: MSE (Mean Squared Error).

**Results:**
1. Final Model Performance:
- Training Loss: 0.0019
- Validation Loss: 0.00001
- Pearson Correlation Coefficient: 0.99 → near-perfect agreement with DEM simulations.

2. Significance:
- Demonstrates that GNNs can efficiently capture force interactions in granular assemblies.
- Achieved drastic computational savings compared to DEM.
- Opens avenues for extending to colloidal systems and other particulate matter simulations.
