# tsp-solver
Jitter Tree TSP Solver — Adaptive TSP heuristic with metric recovery from indirect sensor features. Scales via empirical formula S∝N¹·⁹⁵, B∝N¹·⁰⁸. 100% accuracy on Euclidean TSP up to N=50.

# 🌳 Jitter Tree TSP Solver

Adaptive Traveling Salesman Problem solver that **recovers distances from indirect features** (signal delays from sensors) and finds near-optimal routes via 2-opt with dynamic resource scaling.

## 🔥 Features

- **Empirical scaling formula**:  
  `Starts = 4000·(N/10)¹·⁹⁵`  
  `Branch = 20·(N/10)¹·⁰⁸`  
  Ensures stable accuracy as city count grows.

- **Two-level Jitter Tree**:  
  Feature clustering (delays + deltas) for fast Euclidean distance approximation.

- **100% accuracy** on Euclidean TSP up to **N=50** with noise ≤1e-5.

- **Zero UI freezes**:  
  JS version with chunked async processing, C++ version for raw speed.

## 🚀 Quick Start

### JavaScript (with 3D visualization)
Just open `index.html` in your browser. No dependencies (Three.js loads from CDN).

How It Works

    Feature extraction: For each city pair, compute 10 features (mean time and time difference of signal arrival to 5 sensors).
    Tree training: Generate N random segments, cluster them into B₁×B₂ leaves.
    Distance matrix: Query the tree to estimate distances for all N×N pairs.
    TSP solving: Multi-start 2-opt with adaptive iteration count.

📈 Performance
Cities
	
Samples
	
Starts
	
Time (JS)
	
Accuracy
10
	
120k
	
4k
	
~0.3s
	
100%
25
	
600k
	
15k
	
~1.2s
	
100%
50
	
1.2M
	
72k
	
~3.5s
	
100%
🧪 Stress Testing
Try increasing noise to see degradation:

    noise=0.0001 → ~99.5% accuracy
    noise=0.001 → ~97-98% accuracy  
    noise=0.005 → ~92-95% accuracy

🛠️ Tech Stack

    Frontend: Three.js (WebGL visualization), vanilla JS
    Backend: C++17 (optional, for CLI usage)
    Algorithm: Feature-based metric learning + 2-opt local search

📄 License
MIT License — use it for research, education, or fun.
🤝 Contributing
Found a bug? Want to add 3-opt or LKH integration? PRs welcome!
Built with vibe coding and empirical curiosity. Not a formal TSP solution, but a practical heuristic that works remarkably well for Euclidean instances

**Using AI-coding

Author: Pavel Bobkin  

Github: koolkid90



