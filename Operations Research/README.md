## 1. What is [Operations Research](https://en.wikipedia.org/wiki/Category:Operations_research)?

**Goal:** Use mathematical modeling, optimization, and data to support **better decisions** in complex systems.

**Common objectives:**

* Minimize cost, time, or risk
* Maximize profit, throughput, service level, or reliability
* Balance multiple objectives (cost vs. quality vs. risk, etc.)

**General Resources**

- [Cornell University Computational Optimization Open Textbook](https://optimization.cbe.cornell.edu/index.php?title=Main_Page)
- [Mathematical Optimization](https://en.wikipedia.org/wiki/Category:Mathematical_optimization)
- [Google OR Tools](https://developers.google.com/optimization)
- [MOSEK Modeling Cookbook](https://docs.mosek.com/modeling-cookbook/index.html#)

---

## 2. Deterministic Optimization

### 2.1 [Linear_programming](https://en.wikipedia.org/wiki/Category:Linear_programming)

**What it studies:** Optimization of a linear objective subject to linear constraints, continuous decision variables.

**Canonical form:**
Max/min (c^T x) s.t. (Ax \le b, x \ge 0).

**Key methods & algorithms:**

* Simplex method
* Revised simplex
* Dual simplex
* Interior-point methods
* Sensitivity / post-optimality analysis

**Applications:**

* Production planning & resource allocation
* Blending problems (oil, chemicals, food)
* Transportation and assignment problems
* Workforce / shift scheduling (when relaxed to continuous)

---

### 2.2 Integer & Mixed-Integer Programming (IP / MIP)

**What it studies:** Same as LP but with **integer or binary variables** (yes/no decisions, counts).

**Key concepts:**

* 0–1 programming
* Mixed-integer linear programming (MILP)
* Cutting planes, relaxations

**Core algorithms:**

* [Branch-and-bound](https://en.wikipedia.org/wiki/Branch_and_bound)
* [Branch-and-cut](https://en.wikipedia.org/wiki/Branch_and_cut)
* Branch-and-price
* Cutting plane methods (Gomory cuts, etc.)

**Typical problems:**

* Facility location, network design
* Vehicle routing and logistics
* Project selection and capital budgeting
* Scheduling with discrete constraints (e.g., assigning workers to shifts)

---

### 2.3 Network Optimization / Network Flows

**What it studies:** Problems modeled on **graphs** (nodes and arcs) with flows, capacities, and costs.

**Major problem types:**

* Shortest path
* Maximum flow
* Minimum-cost flow
* Assignment and matching
* Steiner trees, network design

**Algorithms:**

* Dijkstra, Bellman–Ford, Floyd–Warshall (shortest path)
* Ford–Fulkerson, Edmonds–Karp, Dinic (max flow)
* Successive shortest path, cycle-canceling, network simplex (min-cost flow)
* Hungarian algorithm (assignment)

**Applications:**

* Routing (telecom, transportation)
* Supply chain design and distribution networks
* Energy and power grids
* Crew scheduling and airline planning

---

### 2.4 Nonlinear & Convex Optimization

**What it studies:** Problems with **nonlinear** objectives or constraints; special focus on **convex** structure.

**Types:**

* Unconstrained vs. constrained
* Convex vs. non-convex
* Quadratic programming, conic optimization

**Methods:**

* Gradient / steepest descent
* Newton and quasi-Newton (BFGS, etc.)
* Sequential quadratic programming (SQP)
* Interior-point methods for convex problems
* ADMM and first-order methods for large-scale problems

**Applications:**

* Portfolio optimization and risk management
* Engineering design (aerospace, mechanical, electrical)
* Machine learning model training (many models = large nonlinear optimization)

---

### 2.5 [Combinatorial_optimization](https://en.wikipedia.org/wiki/Category:Combinatorial_optimization) & Scheduling

**What it studies:** Discrete structures, often with **NP-hard** problems.

**Typical problems:**

* Traveling Salesman Problem (TSP)
* Vehicle Routing Problem (VRP)
* Job shop & flow shop scheduling
* Knapsack and variants

**Approaches:**

* Exact algorithms (branch-and-bound, dynamic programming, cutting planes)
* Decomposition methods (Lagrangian, Benders)
* Heuristics and metaheuristics (see Section 7)

**Applications:**

* Manufacturing and production scheduling
* Logistics and delivery routing
* Timetabling & rostering (schools, hospitals, airlines)

---

## 3. Stochastic Models & Probability-Based OR

1. [Markov_models](https://en.wikipedia.org/wiki/Category:Markov_models)
2. [Markov_processes](https://en.wikipedia.org/wiki/Category:Markov_processes)
3. [Stochastic_processes](https://en.wikipedia.org/wiki/Category:Stochastic_processes)
	- [Probability, Random Variables, and Stochastic Processes](https://www.youtube.com/playlist?list=PLYemDO44RhzSgZmCQgubQ_Vn9QQ9s3kN4)
	- [Stochastic Processes](https://www.youtube.com/playlist?list=PLTDbRVt9ixKRO0T0qmP43IyDrbh1i_5kW)
	- [Advanced Stochastic Processes](https://www.youtube.com/playlist?list=PLV3oHJg9b1NRk4_LKUdqXPoN9jOWRypKI)
	- [Stochastic Process](https://www.youtube.com/playlist?list=PLvpcUbGDkR2Cu_FGZifjh0Lgh1wNs2exH)
4. [Queueing Theory](https://en.wikipedia.org/wiki/Category:Queueing_theory)

### 3.1 Queueing Theory

**What it studies:** Systems with **random arrivals and service times**.

**Key concepts:**

* Arrival processes (Poisson)
* Service time distributions (exponential, general)
* Kendall notation (M/M/1, M/M/c, etc.)
* Performance measures: waiting time, queue length, utilization, throughput

**Analysis methods:**

* Birth–death processes
* Markov chains
* Embedded Markov chains, transform methods
* Approximation and heavy-traffic limits

**Applications:**

* Call centers, help desks
* Hospital emergency departments
* Computer networks, cloud servers
* Airport security, checkout lines

---

### 3.2 Markov Chains & Markov Processes

**Stochastic Processes Courses** 
- [Course 1](https://www.stat.auckland.ac.nz/~fewster/325/index.php)
- [Course 2](https://ocw.mit.edu/courses/6-262-discrete-stochastic-processes-spring-2011/)
- [Course 3](https://www.ee.ryerson.ca/~courses/ee8103/)
- [Applied Stochastic Processes](https://sidbanerjee.orie.cornell.edu/courses/orie6500/)
- [Introduction to Stochastic Processes](https://ocw.mit.edu/courses/18-445-introduction-to-stochastic-processes-spring-2015/)
- [Probability and Stochastic Processes 1](https://www.utstat.utoronto.ca/mikevans/stac62/staC622021.html)
- [Stochastic_systems_courses](https://murray.cds.caltech.edu/Stochastic_systems_courses)
- [Probability and Stochastic Processes](https://ocw.metu.edu.tr/course/view.php?id=323)

**What it studies:** Systems evolving over time with **probabilistic transitions**.

**Types:**

* Discrete-time Markov chains (DTMC)
* Continuous-time Markov chains (CTMC)
* Markov reward processes

**Methods:**

* Transition matrices, steady-state analysis
* First passage times, hitting probabilities
* Decomposition, aggregation techniques

**Applications:**

* Reliability modeling and maintenance
* Customer behavior and churn
* Inventory systems with Markovian demand
* Epidemic models (simplified)

---

### 3.3 Inventory Theory

**What it studies:** Control of **stock levels** under uncertain demand and lead times.

**Classic models:**

* EOQ (Economic Order Quantity)
* (Q, R) policies (order quantity, reorder point)
* (s, S) policies (order-up-to)
* Multi-echelon inventory, base-stock policies

**Methods:**

* Stochastic dynamic programming
* Renewal theory
* Approximation and asymptotic analysis

**Applications:**

* Retail and e-commerce inventory control
* Spare parts and maintenance stocks
* Pharmaceutical and perishable goods management

---

### 3.4 Reliability & Maintenance

**What it studies:** System/component **failure behavior** and maintenance policies.

**Key topics:**

* Failure time distributions, hazard rate
* Series/parallel systems, k-out-of-n systems
* Preventive maintenance and replacement policies

**Methods:**

* Renewal processes
* Markov and semi-Markov models
* Reliability block diagrams, fault trees

**Applications:**

* Power plants and industrial equipment
* Aircraft and vehicle fleets
* IT infrastructure and data centers

---

## 4. Simulation

**What it studies:** Complex systems that are **too messy for closed-form analysis**, often stochastic.

**Types of simulation:**

* Discrete-event simulation (DES)
* Monte Carlo simulation
* Agent-based simulation

**Key elements:**

* Random number generation and variance reduction
* Model validation and sensitivity analysis
* Design of experiments (DOE) on the simulator

**Applications:**

* Evaluating new hospital layout or staffing plans
* Testing logistics network configurations
* Risk analysis in finance and project management
* Planning and stress-testing manufacturing systems

---

## 5. Decision Analysis & Game Theory

### 5.1 Decision Theory / Decision Analysis

**What it studies:** **Individual decision-making** under risk and uncertainty.

**Core concepts:**

* Decision trees and influence diagrams
* Utility theory and risk preferences
* Value of information (EVPI, EVPPI)
* Multi-criteria decision analysis (MCDA)

**Methods:**

* Expected utility maximization
* Analytic Hierarchy Process (AHP) and variants
* Sensitivity analysis on decision models

**Applications:**

* R&D and investment decisions
* Medical treatment choice under uncertainty
* Policy choices with trade-offs (environment vs. cost)

---

### 5.2 Game Theory

**What it studies:** **Strategic interactions** among multiple decision-makers.

**Main topics:**

* Normal-form and extensive-form games
* Nash equilibria (pure/mixed)
* Cooperative games and bargaining
* Repeated games, evolutionary games

**Applications:**

* Pricing and competition in markets
* Auctions and procurement
* Defense and security, adversarial planning
* Network routing with selfish agents (traffic, data networks)

---

## 6. Dynamic Programming & Stochastic Control

**What it studies:** Multi-stage decisions where the **current decision affects future states**.

**Core framework:**

* State, decision, transition, cost, horizon
* Bellman equations and optimality principle

**Variants:**

* Deterministic dynamic programming
* Stochastic dynamic programming
* Markov Decision Processes (MDPs)
* Partially Observable MDPs (POMDPs)
* [Bellman Equation](https://en.wikipedia.org/wiki/Bellman_equation)

**Methods:**

* Value iteration, policy iteration
* Linear programming formulations
* Approximate dynamic programming, reinforcement learning links

**Applications:**

* Optimal inventory and capacity expansion decisions
* Asset replacement and maintenance scheduling
* Revenue management and dynamic pricing
* Robot motion planning and path control

---

## 7. Heuristics & Metaheuristics

**What it studies:** **Approximate methods** for hard problems where exact optimization is too slow.

**Constructive & local search heuristics:**

* Greedy algorithms
* Local search, hill climbing
* Tabu search

**Metaheuristics:**

* Simulated annealing
* Genetic algorithms / evolutionary algorithms
* Ant colony optimization
* Particle swarm optimization
* GRASP, VNS, etc.

**Applications:**

* Large-scale scheduling (airlines, railways, manufacturing)
* Complex routing (VRP with many side constraints)
* Timetabling, layout design, cutting and packing

---

## 8. Data-Driven & Robust OR

### 8.1 Robust Optimization

**What it studies:** Optimization under **uncertainty without precise distributions**, controlling worst-case outcomes.

**Key ideas:**

* Uncertainty sets (box, ellipsoidal, polyhedral)
* Robust counterparts of LP/MIP
* Adjustable robust optimization (two-stage decisions)

**Applications:**

* Power systems and unit commitment with uncertain demand
* Portfolio optimization with uncertain returns
* Supply chain planning under demand variability

---

### 8.2 Stochastic Programming

**What it studies:** **Optimization with explicit random variables** and often multiple stages.

**Models:**

* Two-stage recourse models
* Multi-stage stochastic programs
* Chance-constrained programming

**Methods:**

* Scenario generation
* Benders decomposition, L-shaped algorithms
* Sample average approximation (SAA)

---

### 8.3 Integration with Statistics & Machine Learning

**Interactions:**

* Predict-then-optimize pipelines (use ML forecasts inside OR models)
* Prescriptive analytics (directly optimize decisions given data)
* Inverse optimization (infer preferences/costs from observed decisions)

**Applications:**

* Personalized pricing and recommendations
* Demand-driven inventory and staffing
* Dynamic control using RL + OR structure

---

## 9. Applications by Domain (Very High-Level)

* **Supply Chain & Logistics**

  * Network design, facility location
  * Transportation and routing, inventory and warehousing
  * Vendor selection and contracts

* **Manufacturing & Services**

  * Production planning, lot sizing
  * Job scheduling, maintenance planning
  * Service system design (call centers, healthcare)

* **Finance & Economics**

  * Portfolio and risk optimization
  * Asset-liability management
  * Pricing and revenue management (airlines, hotels, car rentals)

* **Energy & Utilities**

  * Unit commitment and dispatch
  * Hydro-thermal scheduling
  * Renewable integration and storage operation

* **Healthcare & Public Sector**

  * Hospital operations (OR scheduling, bed management)
  * Emergency response and disaster logistics
  * Policy analysis, epidemic response strategies

* **Telecom & Computing**

  * Network routing and capacity planning
  * Cloud resource allocation and scheduling
  * Load balancing and congestion control

---

## 10. Extensions & Related Fields

* **Constraint Programming (CP):** Logical constraints and search for combinatorial problems; often combined with OR.
* **System Dynamics:** Feedback loops and differential equation models at an aggregate level.
* **Control Theory:** Continuous-time dynamic systems, overlapping with dynamic programming and stochastic control.
* **Human factors & Behavioral OR:** Incorporating real human behaviors and bounded rationality into models.
* **Multi-objective Optimization:** Pareto fronts, trade-off analysis.

---

## Courses

1. [Optimization Methods in Management Science](https://ocw.mit.edu/courses/15-053-optimization-methods-in-management-science-spring-2013/)

## Videos

### Algorithms

1. [COMP 285: Analysis of Algorithms Lectures](https://youtube.com/playlist?list=PL0KKKLEqGOyJR1-dEOKq9QRdCMX0Ho8hu&si=nIVKuZyI9SfYrnJK)
2. [MIT 6.006 Introduction to Algorithms, Spring 2020](https://youtube.com/playlist?list=PLUl4u3cNGP63EdVPNLG3ToM6LaEUuStEY&si=VnwRXl0m1Bnc7cM7)

### Game Theory Introduction

1. [Game Theory 1: Introduction to Game Theory](https://youtube.com/playlist?list=PLcrc6i6xwaQQGOK095_Im781aFOQ1BFix&si=-S1JOc9k5NzMzcX8)
2. [Game Theory 2 (Basic Solution Concepts and Applications): Strategic Dominance, Best Response, Rationalizability](https://youtube.com/playlist?list=PLcrc6i6xwaQQGTAVXv25E3KP-cU5J9zLV&si=U9bJfJKAFwKPyLtK)
3. [Game Theory 3: Nash Equilibrium](https://youtube.com/playlist?list=PLcrc6i6xwaQTbWV-ayb4lky14yR6VqtAQ&si=2fTBXzQZ7Q9cFj_S)
4. [Game Theory 4: Mixed Strategy Nash Equilibrium](https://youtube.com/playlist?list=PLcrc6i6xwaQQAbAPvrhpFsKPvcx_3sF-q&si=4NBWK_P6D0IQtOZh)
5. [Game Theory 5: Contracts](https://youtube.com/playlist?list=PLcrc6i6xwaQQqoZarpUJW2G3lfLFMan1U&si=gVsenNZi434OA7iG)
6. [Game Theory 6: Extensive Form Games with Perfect Information and Subgame Perfect Nash Equilibrium (SPNE)](https://youtube.com/playlist?list=PLcrc6i6xwaQTZI1YXJj4q_ndfEzMaPOZf&si=VIPiOTaUgn8csRH7)
7. [Game Theory 7: Extensive Form Games with Imperfect Information and Subgame Perfect Nash Equilibrium](https://youtube.com/playlist?list=PLcrc6i6xwaQRU-5Q_zRTu6GCiQSaKWJ-1&si=7Ipy5wblWz6YdNkh)
8. [Game Theory 8: Introduction to Repeated Games](https://youtube.com/playlist?list=PLcrc6i6xwaQSbYxbSoY2JINrz5kb7-fGp&si=PgRrhwEJkpKqVmDW)
9. [Game Theory 9: Bayesian Nash Equilibrium](https://youtube.com/playlist?list=PLcrc6i6xwaQT6eIKWHkTXWz9zSFDpkTZm&si=tZR65hOB8VQmw6_R)
10. [Game Theory 10: Perfect Bayesian Nash Equilibrium](https://youtube.com/playlist?list=PLcrc6i6xwaQRP-e4fCBAnOmkbn860TX1_&si=xgdikJz5bogmoqs0)
11. [Game Theory 11: Principal Agent Models](https://youtube.com/playlist?list=PLcrc6i6xwaQRa1ZsTG5-7a1AUltDvo-wS&si=hUkng59Gev0iz0pO)

### Game Theory Advanced

1. [Advanced Game Theory 1: Strategic Form Games with Complete Information](https://youtube.com/playlist?list=PLcrc6i6xwaQRyvwICKDdh8zmvmXBcNaYg&si=tEFpubKV6cEiS9le)
2. [Advanced Game Theory 2: Extensive Form Games](https://youtube.com/playlist?list=PLcrc6i6xwaQTlpwcoyC0m52oCPsWnAQ0t&si=TxobTXCGN7y19P9s)
3. [Advanced Game Theory 3: Solving Extensive Form Games and Their Applications](https://youtube.com/playlist?list=PLcrc6i6xwaQSY7I2-UZxcQt_SodDN-L2r&si=n6MM5JGeu1WjvuQr)
4. [Advanced Game Theory 4: Introduction to Cooperative Game Theory and Its Solution Concepts](https://youtube.com/playlist?list=PLcrc6i6xwaQSw8553tgt1p8XOMFEdQCbl&si=bCzz0NMDWhaxLGOz)
5. [Advanced Game Theory 5: Cooperative (Nash) Bargaining Problem](https://youtube.com/playlist?list=PLcrc6i6xwaQRcbvlbqNS94dRnF-UH1AZw&si=0NtLe5IMgtYSq_rB)
6. [Advanced Game Theory 6: Bankruptcy Problem](https://youtube.com/playlist?list=PLcrc6i6xwaQQo2li8WHSWiDnSnYaAH-g5&si=5dJjKYS-ma8e4VGA)
7. [Advanced Game Theory 7: Matching Theory](https://youtube.com/playlist?list=PLcrc6i6xwaQTmyz-hqitTB2WUI6eZiMIg&si=h3NyqBJwhDxMrJ1F)
8. [Advanced Game Theory 8: Voting](https://youtube.com/playlist?list=PLcrc6i6xwaQTw1cDHdu8iEjo8nuYJG245&si=983gnsVsHCt03Bbw)
9. [Advanced Game Theory 9: Bayesian Games](https://youtube.com/playlist?list=PLcrc6i6xwaQSqqMfgqSYKITGV4i6RK9WI&si=_L6j19cDCxmUu5nO)
10. [Advanced Game Theory 10: Auction Theory](https://youtube.com/playlist?list=PLcrc6i6xwaQT52YtKdIpdARVZ4BTFOrQP&si=ovYw4PqVAEa2U75B)
11. [Advanced Game Theory 11: Mechanism Design](https://youtube.com/playlist?list=PLcrc6i6xwaQQWi7prJYkI9SoRzDXEV01X&si=KjVqLrpZFe8eXMz4)

## Github Resources

1. [awesome-ml4co](https://github.com/Thinklab-SJTU/awesome-ml4co)
2. [Maro](https://github.com/microsoft/maro)
3. [or-gym](https://github.com/hubbs5/or-gym)
4. [ALNS](https://github.com/N-Wouda/ALNS)
5. [csp](https://github.com/emadehsan/csp)
6. [feloopy](https://github.com/ktafakkori/feloopy)
7. [stockpyl](https://github.com/LarrySnyder/stockpyl)
8. [PyHygese](https://github.com/chkwon/PyHygese)
9. [shift-scheduling](https://github.com/lbiedma/shift-scheduling)
10. [VRPLIB](https://github.com/leonlan/VRPLIB)
11. [optimization-tutorial](https://github.com/ekhoda/optimization-tutorial)
12. [pyworkforce](https://github.com/rodrigo-arenas/pyworkforce)
13. [picking-route](https://github.com/samirsaci/picking-route)
14. [pdptw-instances](https://github.com/cssartori/pdptw-instances)
15. [scheduling-optimization-ortools](https://github.com/giangstrider/scheduling-optimization-ortools)
16. [Operations-Research-Theory](https://github.com/tanmoyie/Operations-Research-Theory)
17. [or-tools](https://github.com/google/or-tools)
18. [operations-research](https://github.com/je-suis-tm/operations-research)
19. [Operations-Research](https://github.com/YashBansod/Operations-Research)
20. [open-optimization-or-book](https://github.com/open-optimization/open-optimization-or-book)
21. [respy](https://github.com/OpenSourceEconomics/respy)
22. [pomdp-py](https://github.com/h2r/pomdp-py)
23. [dorado-scheduling](https://github.com/nasa/dorado-scheduling)
24. [schedulinglab](https://github.com/simonseo/schedulinglab)
25. [Scheduling Algorithms](https://github.com/IBM/stomp)
26. [Genetic Algorithm Scheduling](https://github.com/lg-li/Genetic-Algorithm-Flexible-Job-Shop-Scheduling-Problem)
27. [Operations Research](https://github.com/YashBansod/Operations-Research)
28. [queueing-theory](https://github.com/joelparkerhenderson/queueing-theory)
29. [edX-queueing-theory](https://github.com/guanzgrace/edX-queueing-theory)
30. [OpenQTSim](https://github.com/TUDelft-CITG/OpenQTSim)
31. [queueing-modelsim](https://github.com/AbdeltwabMF/queueing-modelsim)
32. [M-M-1-Queue-Simulator](https://github.com/kargaranamir/M-M-1-Queue-Simulator)
33. [birdepy_project](https://github.com/birdepy/birdepy_project)
34. [kalasim](https://github.com/holgerbrandl/kalasim)
35. [Ciw](https://github.com/CiwPython/Ciw)
36. [network-opt](https://github.com/google/network-opt)
37. [PathPlanning](https://github.com/zhm-real/PathPlanning)
38. [PythonRobotics](https://github.com/AtsushiSakai/PythonRobotics)
39. [Taskpacker](https://github.com/Edinburgh-Genome-Foundry/Taskpacker)
40. [scikit-decide](https://github.com/airbus/scikit-decide)
41. [awesome-ml4co](https://github.com/Thinklab-SJTU/awesome-ml4co)
42. [pyomo](https://github.com/Pyomo/pyomo)
43. [optimization-demo-files](https://github.com/bruscalia/optimization-demo-files)
44. [pulp](https://github.com/coin-or/pulp)
45. [Pyomo](https://github.com/OptimizationExpert/Pyomo)
46. [Mosek Tutorials](https://github.com/MOSEK/Tutorials)