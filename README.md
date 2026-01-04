# Graph Path-likeness ≤ 2 Recognition  
### Investigathon 2025

This repository documents the theoretical and algorithmic results developed for
**Investigathon 2025**, a two-week intensive research competition in graph theory.

The project studies a graph recognition problem based on **vertex orderings,
2-colorings, and forbidden patterns**, leading to a complete structural
characterization of the admissible graphs and a linear-time recognition
strategy.

---

## 📌 Competition Context

**Investigathon 2025** is a short, high-intensity research competition where
teams address open theoretical problems under time constraints.

Our team focused on recognizing graphs that admit a vertex ordering and a
2-coloring avoiding specific forbidden colored patterns on triples of vertices.

---

## 🎯 Problem Statement

Given a graph \( G \), determine whether there exist:

- a vertex ordering \( < \),
- a 2-coloring of the vertices,

such that the pair avoids the following forbidden colored patterns:

- **Pattern (i)**:  
  an edge between positions 1 and 3, with vertices 1 and 2 forced to have the
  same color;

- **Pattern (ii)**:  
  an edge between positions 1 and 3, with vertices 2 and 3 forced to have the
  same color.

These patterns impose local constraints on ordered triples of vertices that
translate into global structural restrictions on the graph.

---

## 🧠 Theoretical Framework: *Caminitud* (Path-likeness)

To analyze the problem, we introduced the notion of **caminitud**
(*path-likeness*), a measure of how close a graph is to a simple path under the
allowed ordering and coloring constraints.

### Key Characterization

A graph has **caminitud ≤ 2** if and only if for every edge \( (u,v) \):

- either \( u \) and \( v \) are consecutive in the global vertex ordering, or
- \( u \) and \( v \) share the same color and are consecutive in the ordering
  restricted to that color.

This characterization provides a simple local condition that completely
determines admissibility.

---

## 🔍 Structural Properties

Graphs with caminitud ≤ 2 satisfy strong global constraints:

- **Planarity**: every such graph is planar;
- **Degree bound**: the maximum degree is at most 4;
- **Cycle structure**: the graph decomposes into a linear chain of induced cycles;
- **Cycle space**: induced cycles form an \( \mathbb{F}_2 \)-basis of
  \( H_1(G,\mathbb{F}_2) \).

These properties rule out complex interactions between cycles and impose a
nearly path-like global structure.

---

## 🏗️ Structural Characterization

The admissible graphs admit a precise structural description:

- **Induced cycles** act as the fundamental building blocks;
- The **cycle hypergraph**, whose nodes are induced cycles and whose edges
  represent their connections, must form a simple path;
- Distinct cycles share at most one edge and only under strict conditions;
- Trees may be attached only at specific vertices and in a controlled manner.

This description allows the global structure of the graph to be recovered from
local constraints.

---

## 🎨 Coloring and Ordering Principles

The admissible ordering and 2-coloring follow systematic rules:

- vertices at the ends of the global ordering share the same color;
- paths between same-colored vertices preserve color consistency;
- connection vertices impose color alternation constraints;
- tree attachments must respect degree and ordering restrictions.

These rules ensure consistency with the forbidden pattern constraints.

---

## 📊 Algorithmic Consequences

The structural characterization leads directly to:

- a **cuadratic-time recognition strategy**;
- a **certifying procedure**, providing explicit obstructions when the graph is
  not admissible;
- a **constructive method** to build a valid ordering and coloring when one
  exists.

---

## 📈 Extensions and Future Work

Potential directions for further research include:

- recognition with more than two colors;
- optimization variants minimizing the number of colors;
- applications to graph drawing and constrained layouts;
- complete classification of admissible graphs for broader pattern sets.

---

## 👥 Team & Acknowledgments

- **Team**: *Matching Perfecto*  
- **Members**: Noelia Falczuk, Demián Fraiman  
- **Competition**: Investigathon 2025  
- **Date**: December 10, 2025

---

This repository focuses on the **conceptual and theoretical contribution** of
the project. Implementation details are intentionally omitted.

