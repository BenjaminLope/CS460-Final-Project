# The Torchbearer

**Student Name:** Benjamin Lopez
**Student ID:** 825274015
**Course:** CS 460 – Algorithms | Spring 2026

> This README is your project documentation. Write it the way a developer would document
> their design decisions , bullet points, brief justifications, and concrete examples where
> required. You are not writing an essay. You are explaining what you built and why you built
> it that way. Delete all blockquotes like this one before submitting.

---

## Part 1: Problem Analysis

> Document why this problem is not just a shortest-path problem. Three bullet points, one
> per question. Each bullet should be 1-2 sentences max.

- **Why a single shortest-path run from S is not enough:**
  A single shortest path run from S does not always guarantee visiting every relic chamber. As a result we need the shortest path from every chamber.

- **What decision remains after all inter-location costs are known:**
  After all inter-location costs are known the decision that remains is the order of visiting chambers.

- **Why this requires a search over orders (one sentence):**
  Different routes and orders cost different fuel amounts, so to find the most optimal route we must check over all the orders

---

## Part 2: Precomputation Design

### Part 2a: Source Selection

> List the source node types as a bullet list. For each, one-line reason.

| Source Node Type | Why it is a source |
|---|---|
| _Entrance_ | _We need the distance from the entrance to every relic chamber since its the starting point for the torchbearer_ |
| _Relic Chamber_ | _We need the distance from every relic chamber to every other and to the exit_ |

### Part 2b: Distance Storage

> Fill in the table. No prose required.

| Property | Your answer |
|---|---|
| Data structure name | Dictionary |
| What the keys represent | Source and destination nodes |
| What the values represent | Distance from source to destination |
| Lookup time complexity | O(1) |
| Why O(1) lookup is possible | Hashing allows direct look up time in memory |

### Part 2c: Precomputation Complexity

> State the total complexity and show the arithmetic. Two to three lines max.

- **Number of Dijkstra runs:** k + 1, since we search from k relic chambers, as well as starting entrance
- **Cost per run:** O((V + E)log n), where V is number of vertices and E is number of edges
- **Total complexity:** O((k + 1)((V + E)log V)) -> O(k(V + E)log V)
- **Justification (one line):** We run Dijkstra from the start and every relic chamber, and each run takes O((V + E)log V)

---

## Part 3: Algorithm Correctness

> Document your understanding of why Dijkstra produces correct distances.
> Bullet points and short sentences throughout. No paragraphs.

### Part 3a: What the Invariant Means

> Two bullets: one for finalized nodes, one for non-finalized nodes.
> Do not copy the invariant text from the spec.

- **For nodes already finalized (in S):**
  It means that we know the true set in stone shortest distance to the node

- **For nodes not yet finalized (not in S):**
  It means that we know a short path to the node, but not if its the true shortest yet as it only goes through finalized nodes so far.

### Part 3b: Why Each Phase Holds

> One to two bullets per phase. Maintenance must mention nonnegative edge weights.

- **Initialization : why the invariant holds before iteration 1:**
   Before the first iteration the start is initalized to 0 and every other node to infinity, with an empty S.
   The invariant holds, as the shortest true path to yourself is 0, and every other node is unknown so it remains infinity

- **Maintenance : why finalizing the min-dist node is always correct:**
   Since the edge weights are nonnegative you can only ever add more, and the minimum node will ensure alwasy the minimum most cost/path is added.
   That means it is the shortest possible path, so its correct fo finalize.

- **Termination : what the invariant guarantees when the algorithm ends:**
   The algorithm guaranteess all reachable nodes will be in the finalized set S. 
   Thus it guarentees that the true shortest path to each node has been caluclated.

### Part 3c: Why This Matters for the Route Planner

> One sentence connecting correct distances to correct routing decisions.

 Without a correct distance, the torchbearer cannot find the exit, or would make a choice that wastes fuel and could lead to a suboptimal route.

---

## Part 4: Search Design

### Why Greedy Fails

> State the failure mode. Then give a concrete counter-example using specific node names
> or costs (you may use the illustration example from the spec). Three to five bullets.

- **The failure mode:** Greedy will always choose the next cheapest cost relic chamber, which could potentially block a global optimal route
- **Counter-example setup:** For the counterexample, we will use the following dungeon mapping:
| From \ To | B   | C   | D   | T   |
|-----------|-----|-----|-----|-----|
| S         | 1   | 2   | 2   | --  |
| B         | --  | 100 | 100 | 1   |
| C         | 1   | --  | 100 | 1   |
| D         | 1   | 1   | --  | 100 |
- **What greedy picks:** Greedy would choose the cheapest route available at each point, leading to a selection of S->B->D->C->T and a total cost of 103
- **What optimal picks:** Optimal would choose the optimal route, leading to a selection of S->D->C->B->T, and a cost of 5
- **Why greedy loses:** Greedys choice of local optimum locks it out from the global optimal choice, and in this case makes it total cost significantly higher than the optimal path

### What the Algorithm Must Explore

> One bullet. Must use the word "order."

- Since the final answer depends on the global best path between all relics, the algorithm must explore every order of relic chamber visits to find the most opitimal path

---

## Part 5: State and Search Space

### Part 5a: State Representation

> Document the three components of your search state as a table.
> Variable names here must match exactly what you use in torchbearer.py.

| Component | Variable name in code | Data type | Description |
|---|---|---|---|
| Current location | | | |
| Relics already collected | | | |
| Fuel cost so far | | | |

### Part 5b: Data Structure for Visited Relics

> Fill in the table.

| Property | Your answer |
|---|---|
| Data structure chosen | |
| Operation: check if relic already collected | Time complexity: |
| Operation: mark a relic as collected | Time complexity: |
| Operation: unmark a relic (backtrack) | Time complexity: |
| Why this structure fits | |

### Part 5c: Worst-Case Search Space

> Two bullets.

- **Worst-case number of orders considered:** _Your answer (in terms of k)._
- **Why:** _One-line justification._

---

## Part 6: Pruning

### Part 6a: Best-So-Far Tracking

> Three bullets.

- **What is tracked:** _Your answer here._
- **When it is used:** _Your answer here._
- **What it allows the algorithm to skip:** _Your answer here._

### Part 6b: Lower Bound Estimation

> Three bullets.

- **What information is available at the current state:** _Your answer here._
- **What the lower bound accounts for:** _Your answer here._
- **Why it never overestimates:** _Your answer here._

### Part 6c: Pruning Correctness

> One to two bullets. Explain why pruning is safe.

- _Your answer here._

---

## References

> Bullet list. If none beyond lecture notes, write that.

- _Your references here._
