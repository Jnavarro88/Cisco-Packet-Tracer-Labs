Technical Report: EIGRP Enterprise Implementation

📌 Project Overview

The goal of this lab was to implement Enhanced Interior Gateway Routing Protocol (EIGRP) across a multi-router mesh topology. EIGRP was selected for this environment due to its rapid convergence times and its use of the Diffusing Update Algorithm (DUAL) to maintain loop-free paths.

🏗️ Network Architecture

Protocol: EIGRP (Autonomous System 10)

Algorithm: DUAL (Diffusing Update Algorithm)

Metric: Composite (Bandwidth + Delay)

Topology: Multi-router mesh with redundant pathing.

Topology Diagram

⚙️ Configuration & Implementation Logic

This implementation focuses on efficient network advertisement and path stability. I used a flat AS 10 structure with no auto-summary to ensure proper subnet propagation.
