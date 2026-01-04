Graph Path-likeness ≤ 2 Recognition – Investigathon 2025
📌 Competition Context
This project was developed for Investigathon 2025, a two-week intensive research competition in graph theory. Our team tackled the problem of recognizing graphs that admit specific vertex orderings with limited colorings while avoiding forbidden patterns.

🎯 Problem Statement
Given a graph G, determine whether there exists:

A vertex ordering <

A 2-coloring of vertices
Such that the pair avoids two specific forbidden colored patterns:

Pattern (i): E = {(1,3)}, N = ∅, C = {1,2}

Pattern (ii): E = {(1,3)}, N = ∅, C = {2,3}

Where the patterns represent constraints on triples of vertices in the ordering, with colored vertices requiring the same color.

🧠 Our Theoretical Framework
We introduced the concept of "caminitud" (path-likeness) to characterize admissible graphs:

Key Characterization Theorem
A graph has caminitud ≤ 2 if and only if for every edge (u,v), either:

u and v are consecutive in the global ordering, OR

u and v have the same color AND are consecutive in the ordering restricted to that color

Structural Properties Discovered
Planarity: All caminitud ≤ 2 graphs are planar

Degree Bound: Maximum degree ≤ 4

Cycle Structure: Graphs decompose into a linear chain of induced cycles

Cycle Space: Induced cycles form an 𝔽₂-basis for the cycle space H₁(G,𝔽₂)

🏗️ Graph Structure Characterization
Core Components
Induced Cycles: Form a basis of the cycle space

Cycle Hypergraph: Must be a simple path

Connection Constraints:

Cycles share at most one edge

Triangle constraints for certain connections

Tree attachments follow specific rules

Attachment Rules
Internal cycle nodes: No tree attachments allowed

External cycle nodes: Limited tree attachments (at most one per side)

Connection nodes: Strict restrictions based on connection type

Path connections: Allow specific branching patterns

⚡ Algorithm Design
We developed a linear-time O(n+m) recognition algorithm:

Algorithm Steps
text
1. Decompose graph into connected components
2. For each component:
   a. If no cycles: Check tree conditions
   b. Find all induced cycles
   c. Verify cycles form an 𝔽₂-basis
   d. Construct cycle hypergraph
   e. Check hypergraph is a path
   f. Validate all connection conditions
   g. Construct valid ordering and coloring if exists
3. Return recognition result with certificate
Key Features
Certifying: Provides counterexample when false

Linear Complexity: O(n+m) time and space

Constructive: Builds valid ordering and coloring when possible

🔬 Implementation Approach
Cycle Detection
Use modified DFS to find induced cycles

Maintain cycle space basis over 𝔽₂

Hypergraph Construction
Vertices: Induced cycles

Edges: Cycle connections (shared edges, hinge nodes, or connecting paths)

Validation Checks
Basis verification in cycle space

Path structure in hypergraph

Attachment condition compliance

Coloring consistency

📊 Complexity Analysis
Time Complexity: O(|V| + |E|)

Space Complexity: O(|V| + |E|)

Basis Computation: Linear via Gaussian elimination over 𝔽₂

Hypergraph Operations: Linear traversal

🎨 Coloring and Ordering Construction
We developed systematic rules for constructing valid 2-colorings and orderings:

Coloring Rules
Start/end vertices same color

Path between same-colored vertices maintains color

Tree attachments follow degree-3 node paths

Connection nodes follow opposite color rules

Ordering Rules
Follow hypergraph path order

Respect connection constraints

Handle edge-sharing cycles specially

Append tree attachments appropriately

🧪 Testing Methodology
Verified on known admissible/non-admissible graphs

Tested edge cases: cycles, trees, combinations

Validated against brute-force for small graphs

Ensured planarity and degree bounds

📈 Extensions and Future Work
Generalization: k-coloring recognition

Optimization: Minimum coloring algorithm

Applications: Graph drawing, scheduling

Theoretical: Complete characterization of admissible graphs

👥 Team & Acknowledgments
Team: Matching Perfecto
Members: Noelia Falczuk, Demián Fraiman
Competition: Investigathon 2025
Date: December 10, 2025
