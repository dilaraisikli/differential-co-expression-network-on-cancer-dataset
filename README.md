# $$\text{DEPM Project — Group 08}$$

This project focuses on analyzing the structure, robustness, and dynamic behavior of **transportation networks**, with a special focus on **air traffic networks**. The goal is to study how complex network properties influence congestion, delays, and vulnerability under different scenarios.

---

# $$\text{1. INTRODUCTION}$$

The study explores transportation systems through the lens of **complex networks**, where each airport is treated as a node and each direct flight between two airports is treated as a link.  
The project examines:

- Network topology  
- Connectivity  
- Degree distribution  
- Centrality metrics  
- Network robustness  
- Dynamics under stress (e.g., airport failures, delays, etc.)

Such an approach helps understand how structural characteristics affect the stability and efficiency of transportation systems.

---

# $$\text{2. DATASET DESCRIPTION}$$

The dataset represents a transportation network where:

- **Nodes:** airports  
- **Edges:** flight connections  
- **Weights:** number of flights or passenger volumes (depending on dataset)

The network can be represented as:

- **Directed or undirected graph**
- **Weighted or unweighted connections**
- **Static or dynamic (time-dependent)**

The dataset serves as the foundation for all computations, including centrality, clustering, and failure analysis.

---

# $$\text{3. NETWORK TOPOLOGY ANALYSIS}$$

This section explores the overall structure of the network.

### Key metrics analyzed:

- **Degree distribution**  
  - Identifying whether the network is scale-free  
  - Presence of hubs and highly connected airports  

- **Clustering coefficient**  
  - Measures the density of triangles  
  - Indicates local redundancy in the network  

- **Shortest path distribution**  
  - Indicates global connectivity efficiency  

- **Connected components**  
  - Whether the network forms a giant connected component  
  - Detection of isolated subnetworks  

These measures reveal how efficiently the network supports mobility and how vulnerable it may be to disruptions.

---

# $$\text{4. CENTRALITY MEASURES}$$

Centrality metrics identify the most important nodes (airports) in the network.

### Metrics computed:

- **Degree centrality**  
  - Airports with the most direct connections  

- **Betweenness centrality**  
  - Airports most frequently used as transit hubs  

- **Closeness centrality**  
  - Airports with the shortest average travel distance to all others  

- **Eigenvector centrality**  
  - Airports connected to other highly central airports  

Together, these metrics reveal the hierarchy and influence of different airports within the global structure.

---

# $$\text{5. NETWORK ROBUSTNESS}$$

This section analyzes how the network behaves under failures or targeted attacks.

### Scenarios studied:

- **Random removal of airports**  
  - Simulates unpredictable failures  
  - Measures loss of connectivity  

- **Targeted removal of hubs**  
  - Models strategic attacks  
  - Identifies vulnerability around major airports  

### Evaluated metrics:

- Size of the largest connected component  
- Average shortest path length  
- Degree of fragmentation  

Results typically show that:

- Scale-free networks are robust to random failures  
- …but highly vulnerable to targeted attacks  

---

# $$\text{6. EPIDEMIC OR SPREADING DYNAMICS}$$

The project includes a simulation of spreading processes on the network (e.g., delays, congestion, or epidemics).

### Key concepts:

- **SIR or SIS models**  
  - Nodes transition between states (e.g., active/infected/recovered)  

- **Transmission probability**  
  - Likelihood of spreading via a connection  

- **Critical thresholds**  
  - Minimum value required for sustained spreading  

The spreading behavior depends strongly on:

- Degree distribution  
- Weight distribution  
- Presence of hubs  

---

# $$\text{7. TRAFFIC FLOW AND CONGESTION ANALYSIS}$$

The project analyzes how traffic loads are distributed across the network.

### Important insights:

- Traffic tends to accumulate around hubs  
- Removal or slowdown of high-centrality nodes creates cascading congestion  
- Path lengths increase sharply under stress  
- Bottlenecks can be identified using centrality and flow models  

This helps evaluate the network’s real-world performance under heavy demand.

---

# $$\text{8. SUMMARY OF FINDINGS}$$

Main conclusions from the project:

- The air traffic network exhibits **scale-free characteristics**, with a small number of major hubs.
- The network is **robust to random failures** but **extremely vulnerable to targeted removal** of hubs.
- Centrality measures highlight the airports most critical for global connectivity.
- Spreading processes (e.g., congestion or disease) propagate **faster in hub-dominated networks**.
- Congestion simulations show that traffic flow is uneven and highly sensitive to disruptions.

These results provide valuable insights into how transportation systems can be made more resilient and efficient.

---

# $$\text{ACKNOWLEDGMENTS}$$

This work was completed as part of the **DEPM-1 course project**, Group 08.  
It demonstrates the application of complex network theory to real-world transportation systems.

