---
layout: page
title: Course Plan
permalink: /plan/
---

### Week 0: Orientation Week

## Part 1: Foundations & Core Architectures

### Week 1: Graph Foundations & Traditional Embeddings
* Basic graph concepts (nodes, edges, adjacency/sparse matrix representation).
* Centrality measurements (Degree, Betweenness, PageRank, ...) and Graph kernels.
* Shallow embedding models: Random walk (DeepWalk, Node2Vec) and proximity-based models.

### Week 2: Message Passing & Graph Neural Networks
* Motivation from CNNs to GNNs.
* The Message Passing Neural Network (MPNN) framework.
* Graph Convolutional Networks (GCNs).

### Week 3: Theoretical Foundations & Expressivity
* The limitations of message passing.
* The Weisfeiler-Lehman (1-WL) Isomorphism Test.
* Higher-order GNNs and Subgraph GNNs.

### Week 4: Scalability of Graph Neural Networks
* Issues with large-scale graph training (neighborhood explosion).
* Node-wise sampling (GraphSAGE).
* Graph/Subgraph-wise sampling (ClusterGCN, GraphSAINT).

## Part 2: Bottlenecks, Scalability & Trust

### Week 5: Training Deeper GNNs
* What impedes deep GNNs?
* **Over-smoothing vs. Over-squashing.**
* **Under-Reaching**
* **Multi-hop Aggregation**:
    * Explicit hop-wise aggregation: MixHop, SIGN.
    * Adaptive hop propagation: GPR-GNN, APPNP.
    * Layer-wise / jump aggregation: Jumping Knowledge (JKNet).

### Week 6: Heterophily, Graph Structure Learning
* **Homophily** vs. **Heterophily**: revisiting the smoothness assumption; heterophily-aware GNNs (H2GCN, GPR-GNN).
* **Graph Structure Learning (GSL)**: jointly or adaptively learning graph topology and node representations.

### Week 7: Attentive GNNs and Graph Pooling
* Graph Attention Networks (GAT) and Attention in Heterogeneous graphs.
* Hierarchical Graph Pooling (DiffPool, SAGPool).

### Week 8: Mid-Term Exam

### Week 9: Explainability, Generalizability and Robustness
* Interpreting GNN predictions (GNNExplainer, PGExplainer).
* Adversarial attacks on graph data (modifying edges/features).
* Defenses and robust GNN architectures.

## Part 3: Advanced Architectures & Generative Models

### Week 10: Graph Transformers
* From Message Passing to Self-Attention.
* The necessity of Positional and Structural Encoding (PE/SE) in graphs.
* Representative models (Graphormer, SAN).

### Week 11: Generative Graph Models & Diffusion
* Variational Autoencoders for graphs (VGAE).
* Graph Diffusion Models (generating novel molecular structures or networks).

### Week 12: Spatio-temporal Graph Neural Networks (STGNN)
* Introduction to spatial + temporal dependencies.
* Applications: Traffic forecasting, weather modeling, and action recognition.

## Part 4: Cutting-Edge Applications & Synergies

### Week 13: GNNs for Recommendation & Molecular Structure Learning
* Bipartite graphs and user-item interactions; LightGCN and PinSage; RecSys evaluation metrics (condensed overview).
* Molecules as graphs; Equivariant GNNs (E(n) Equivariance for 3D modeling).
* Connections to AlphaFold and modern drug discovery.

### Week 14: Heterogeneous Graphs, KGs, and GraphRAG
* Knowledge Graph representation learning (TransE, RotatE).
* **Synergy with LLMs: Graph Retrieval-Augmented Generation (GraphRAG).**

### Week 15: Course Consolidation

### Week 16: Final Exam
