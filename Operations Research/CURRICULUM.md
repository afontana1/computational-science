
---

## 0. Setup (first few weeks)

**Goals**

* Pick your main tools and “spine” books.
* Light refresh on any gaps (probability, linear algebra).

**Tools**

* **Language**: Python

  * `numpy`, `pandas`, `scipy`, `networkx`
  * Optimization: `pulp` or `pyomo`, plus `ortools`
  * Solver: HiGHS (via SciPy or OR-Tools), or Gurobi/CPLEX if you can get an academic license.

**Spine textbooks & core courses**

* **Hillier & Lieberman – *Introduction to Operations Research*** as a broad OR overview (LP, networks, dynamic programming, integer, nonlinear, metaheuristics, game theory, decision analysis, queueing, etc.). ([Google Books][1])
* Optionally, **Bertsimas & Tsitsiklis – *Introduction to Linear Optimization*** for deeper LP/IP theory. ([Amazon][2])
* **MIT 15.093J – Optimization Methods (OCW)** for a unified optimization course (linear, robust, network flows, discrete, dynamic, nonlinear). ([MIT OpenCourseWare][3])

If you’re rusty on probability, skim a solid probability text for a few weeks; you’ll need random variables, conditioning, Markov chains basics.

---

## Year 1 – Core OR “toolbox”

### Q1 (Months 1–3): OR modeling + Linear Programming

**Goals**

* Learn to translate verbal problems → LP models.
* Get comfortable with simplex, duality, and sensitivity analysis.

**Core topics**

* OR modeling cycle: formulate, solve, validate, implement.
* Linear programming formulation: standard/canonical forms, constraints, slack/surplus. ([Wikipedia][4])
* Simplex method (geometry, tableau, degeneracy).
* Duality, shadow prices, sensitivity analysis.
* Basic modeling in Python with a solver.

**Primary resources**

* Hillier & Lieberman, ch. 1–7 (intro + LP, simplex, duality, sensitivity). ([Google Books][1])
* MIT 15.093J lectures 1–9 (applications, geometry of LP, simplex, duality, sensitivity, intro robust). ([MIT OpenCourseWare][5])
* (Optional deeper LP) Bertsimas & Tsitsiklis – *Introduction to Linear Optimization* (geometry, polyhedra, duality). ([Massachusetts Institute of Technology][6])

**Practice / project idea**

* Build and solve several LP models end-to-end:

  * Production planning, blending, workforce scheduling.
* For one problem, do:

  * Hand simplex on a small instance.
  * Then code the model (PuLP/Pyomo) and perform sensitivity analysis (vary capacities, costs).

---

### Q2 (Months 4–6): Integer Programming & Network Flows

**Goals**

* Handle discrete decisions (0–1, integer) and graph-structured problems.
* Understand branch-and-bound and core network algorithms.

**Core topics**

* Integer and mixed-integer programming:

  * Modeling with binary variables (logical conditions, fixed charges, big-M).
  * Branch-and-bound, branch-and-cut ideas.
* Network models:

  * Shortest paths, minimum spanning trees, max flow, min-cost flow, assignment.
  * Network simplex, reductions between network problems.

**Primary resources**

* Hillier & Lieberman, ch. 8 (transportation & assignment), 9 (network optimization), 11 (integer programming). ([Google Books][1])
* Ahuja, Magnanti & Orlin – *Network Flows: Theory, Algorithms, and Applications* (deep dive on network flow algorithms and applications). ([Root Site][7])

**Practice / project ideas**

* Implement:

  * Shortest path and max-flow algorithms yourself (e.g., Dijkstra, Edmonds–Karp) and compare with `networkx`.
  * A simple branch-and-bound for 0–1 knapsack or small MILP.
* Mini-project: design a distribution network (warehouses → customers) with:

  * A min-cost flow model for routing.
  * An IP for facility location (open/close warehouses, fixed costs).

---

### Q3 (Months 7–9): Stochastic Models – Markov Chains, Queueing, Inventory

**Goals**

* Move from deterministic to stochastic modeling.
* Understand how congestion, waiting, and uncertainty shape decisions.

**Core topics**

* Markov chains (discrete and continuous-time): transition matrices, stationary distributions, hitting times.
* Queueing theory:

  * Kendall notation (M/M/1, M/M/c, M/G/1, etc.).
  * Birth–death processes, utilization, Little’s law, performance metrics.
* Basic inventory models:

  * EOQ, (Q,R), (s,S) policies in simple settings.

**Primary resources**

* Hillier & Lieberman chapters on queueing systems and inventory theory (later chapters; they cover standards like M/M/1, multi-server queues, and basic inventory policies). ([Google Books][1])
* Leonard Kleinrock – *Queueing Systems, Vol. I: Theory* for deeper queueing math. ([Wiley][8])

**Practice / project ideas**

* Analyze an M/M/1 queue by hand (derive (L, L_q, W, W_q)), then compare with simulation.
* Build a small simulation in Python for:

  * A call center (multi-server queue)
  * Or a checkout line with variable service times.
* Implement a basic inventory model and simulate stockouts vs. holding costs under Poisson demand.

---

### Q4 (Months 10–12): Simulation & Intro Metaheuristics

**Goals**

* Learn to simulate complex systems you can’t treat analytically.
* Get exposure to metaheuristics for hard optimization problems.

**Core topics**

* Monte Carlo simulation:

  * Random number and variate generation, variance reduction.
* Discrete-event simulation (DES) for queues, manufacturing, logistics.
* Input modeling, validation, output analysis.
* Intro metaheuristics: simulated annealing, tabu search, genetic algorithms for hard combinatorial problems.

**Primary resources**

* Law – *Simulation Modeling and Analysis* (discrete-event simulation, input/output analysis, variance reduction; widely used in OR). ([McGraw Hill][9])
* Hillier & Lieberman’s simulation chapter + metaheuristics chapter (e.g., tabu search, simulated annealing, GA). ([Google Books][1])

**Practice / project ideas**

* Build a DES model (with SimPy or custom event loop) of:

  * An ED triage system or a warehouse picking process.
* Apply a metaheuristic (SA or GA) to:

  * TSP or VRP instance and compare results/solve time to exact MILP.

---

## Year 2 – Advanced Topics & Specialization

### Q5 (Months 13–15): Nonlinear & Convex Optimization

**Goals**

* Move beyond LP to nonlinear problems, with a strong convex optimization core.
* Understand gradient-based algorithms and KKT conditions.

**Core topics**

* Smooth unconstrained optimization:

  * Gradient descent, Newton, quasi-Newton, line searches.
* Constrained optimization:

  * KKT conditions, Lagrangians.
* Convex optimization:

  * Convex sets/functions, duality.
  * Quadratic programming, conic programs (SOCP, SDP – at least at a conceptual level).

**Primary resources**

* Hillier & Lieberman, nonlinear programming chapter (KKT, quadratic, separable, convex). ([Google Books][1])
* Boyd & Vandenberghe – *Convex Optimization* (foundational text on convex sets, functions, duality, interior-point methods, with many applications). ([Stanford University][10])
* MIT 15.084J / convex optimization OCW material (related to Boyd’s book) if you want lectures. ([Stanford University][11])

**Practice / project ideas**

* Implement gradient descent and Newton’s method on:

  * Logistic regression, regularized least squares.
* Formulate and solve:

  * A portfolio optimization QP; experiment with different risk measures (variance, CVaR approximations).
* Identify a nonconvex OR problem and see how far you can get by convexifying/relaxing it.

---

### Q6 (Months 16–18): Dynamic Programming, MDPs & Stochastic Programming (Intro)

**Goals**

* Internalize the Bellman perspective on multi-stage decisions.
* Learn core MDP algorithms and see how uncertainty enters planning models explicitly.

**Core topics**

* Dynamic programming:

  * Principle of optimality, deterministic and stochastic DP.
* Markov Decision Processes (MDPs):

  * Finite-state/action MDPs, value iteration, policy iteration, linear programming approaches.
* Intro to stochastic programming:

  * Two-stage recourse models, scenario trees, sample average approximation (SAA).

**Primary resources**

* Hillier & Lieberman, dynamic programming chapter (deterministic and probabilistic DP). ([Google Books][1])
* Puterman – *Markov Decision Processes: Discrete Stochastic Dynamic Programming* (canonical MDP text). ([Amazon][12])
* Birge & Louveaux – *Introduction to Stochastic Programming* (standard intro to two-stage and multi-stage SP). ([Springer][13])

**Practice / project ideas**

* Implement value iteration and policy iteration for:

  * Inventory control (order-up-to policy) or machine replacement.
* Build a very small two-stage stochastic LP:

  * First-stage capacity decision, second-stage recourse with a handful of scenarios (demand states).
* Compare:

  * “Optimize-then-simulate” vs. “simulate-first naive policy” on one problem to see value of OR.

---

### Q7 (Months 19–21): Decision Analysis, Game Theory, Robust & Data-Driven OR

**Goals**

* Connect OR with decision theory & game-theoretic thinking (nice synergy with your econ).
* Learn robust optimization and basics of data-driven / prescriptive analytics.

**Core topics**

* Decision analysis:

  * Decision trees, value of information, utility, risk attitudes, multi-criteria decision making.
* Game theory in OR context:

  * Two-player zero-sum games, LP formulations, simple auctions, competitive facility location.
* Robust optimization:

  * Uncertainty sets (box, ellipsoidal, polyhedral), robust counterparts for LP/MILP, adjustable robustness.
* Data-driven OR:

  * Predict-then-optimize pipelines.
  * Basic integration with ML (e.g., forecast demand, then optimize supply).

**Primary resources**

* Hillier & Lieberman, chapters on game theory and decision analysis (two-person zero-sum games, decision trees, utility). ([Google Books][1])
* MIT 15.093J robust optimization lectures for an intro to uncertainty sets and robust counterparts. ([MIT OpenCourseWare][5])
* For data-driven OR, you can dip into Bertsimas’s books/notes (e.g., *Machine Learning Under a Modern Optimization Lens* – optional, but nicely bridges OR + ML). ([Wikipedia][14])

**Practice / project ideas**

* Draw and solve a decision tree for a real decision you care about (career, investment, product launch), with explicit utilities.
* Model a simple two-player game as an LP to compute a Nash equilibrium in mixed strategies.
* Take a real dataset (e.g., demand over time), fit a forecast model, then embed the predictions into an inventory or pricing optimization model.

---

### Q8 (Months 22–24): Capstone & Specialization

**Goals**

* Pull everything together in 1–2 substantive projects.
* Go deeper in domains you care about (e.g., supply chains, health, energy, tech platforms).

**Specialization options (pick 1–2)**

* **Supply chain & logistics**: vehicle routing, production planning, multi-echelon inventory.
* **Revenue management & pricing**: airline/hotel RM, dynamic pricing, assortment optimization.
* **Energy systems**: unit commitment, economic dispatch, renewables integration.
* **Healthcare operations**: OR scheduling, patient flow, capacity planning.
* **Tech / platforms**: ad auctions, ride-sharing matching, content recommendation from an OR lens.

**How to specialize**

* Use syllabi & course lists from top OR programs (e.g., MIT ORC’s course offerings) to identify advanced electives and topics you like, then self-study the relevant subset. ([Operations Research Center][15])
* Read a mix of:

  * Advanced textbooks/monographs in your area.
  * Survey papers + 2–3 recent research papers.

**Capstone project (important)**

By the end of the 2nd year, do at least **one substantial project** that:

1. Starts from a messy real problem (ideally from your work domain).
2. Goes through:

   * Problem framing and stakeholder goals
   * Data exploration & preprocessing
   * Choice of modeling paradigm (LP/MIP, DP/MDP, simulation, or hybrid)
   * Implementation in code with a solver/simulator
   * Scenario & sensitivity analysis
   * Clear writeup and visualization of policy recommendations.

This becomes a nice “proof-of-work” portfolio piece if you later apply to OR/analytics roles or programs.

---

## How to Work Week-to-Week

A rough weekly pattern that tends to work well:

* **Concept (30–40%)**: reading textbook sections + watching 1–2 lectures.
* **Exercises (30–40%)**: pencil-and-paper problems, *especially* formulations.
* **Implementation (20–40%)**: coding models in Python + solvers, plus small experiments.

---


[1]: https://books.google.com/books/about/Introduction_to_Operations_Research.html?hl=de&id=NvE5PgAACAAJ& "Introduction to Operations Research"
[2]: https://www.amazon.com/Introduction-Linear-Optimization-Scientific-Computation/dp/1886529191? "Introduction to Linear Optimization (Athena Scientific ..."
[3]: https://ocw.mit.edu/courses/15-093j-optimization-methods-fall-2009/? "Optimization Methods | Sloan School of Management"
[4]: https://en.wikipedia.org/wiki/Linear_programming? "Linear programming"
[5]: https://ocw.mit.edu/courses/15-093j-optimization-methods-fall-2009/pages/lecture-notes/? "Lecture Notes | Optimization Methods | Sloan School of ..."
[6]: https://www.mit.edu/~dbertsim/books.html? "Professor Dimitris Bertsimas"
[7]: https://mitmgmtfaculty.mit.edu/jorlin/network-flows/? "Network Flows: Theory, Algorithms, and Applications"
[8]: https://www.wiley.com/en-us/Queueing%2BSystems%2C%2BVolume%2BI-p-9780471491101? "Queueing Systems, Volume I"
[9]: https://www.mheducation.com/highered/product/simulation-modeling-and-analysis-law.html? "Simulation Modeling and Analysis, 5th Edition"
[10]: https://stanford.edu/~boyd/cvxbook/? "Convex Optimization – Boyd and Vandenberghe"
[11]: https://web.stanford.edu/~boyd/cvxbook/bv_cvxslides.pdf? "Convex Optimization"
[12]: https://www.amazon.com/Markov-Decision-Processes-Stochastic-Programming/dp/0471727822? "Markov Decision Processes: Discrete Stochastic Dynamic ..."
[13]: https://link.springer.com/book/10.1007/978-1-4614-0237-4? "Introduction to Stochastic Programming - Springer Link"
[14]: https://en.wikipedia.org/wiki/Dimitris_Bertsimas? "Dimitris Bertsimas"
[15]: https://orc.mit.edu/academics/course-offerings/? "Course Offerings - Operations Research Center - MIT"
