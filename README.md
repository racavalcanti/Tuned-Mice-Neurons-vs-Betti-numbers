# 📊 Topological Data Analysis of Neuronal Connectivity with a Finsler-Type Metric

This repository explores the use of **Topological Data Analysis (TDA)** to study neuronal connectivity as a function of **orientation selectivity**.

The approach combines **custom Finsler-type metrics** with **simplicial complexes and persistent homology** to analyze relationships between neurons under different visual stimuli.

The goal is to extract **topological signatures of neural organization**, revealing structures that are not easily detected using classical statistical methods.

---

# Motivation

Neuronal systems exhibit highly complex connectivity patterns, especially in the presence of structured stimuli such as visual orientations.

Traditional approaches rely on:

* correlation matrices  
* Euclidean distances  
* graph-based models  

However, these methods may fail to capture **higher-order geometric and topological structures**.

Topological Data Analysis provides tools to investigate:

* connectivity patterns  
* loops and cycles  
* higher-dimensional structures in neuronal data  

This project studies whether **topological invariants driven by orientation selectivity** can reveal meaningful organization in neural systems.

---

# Finsler-Type Metric

Instead of standard distances, we introduce a **Finsler-type metric** to encode anisotropy and directionality in neuronal interactions.

Given two vectors $p,q \in \mathbb{R}^n$, the distance is defined as

$$
M(p,q) =
\left(
\sum_{i=1}^{n}
f_{\mathrm{ref}}(p_i)\, |q_i - p_i|^{\alpha}
\right)^{\frac{1}{\alpha}}
+
\sum_{i=1}^{n}
g_{\mathrm{ref}}(\alpha, p_i)\,
f_{\mathrm{ref}}(p_i)^{\frac{1}{\alpha}}
(q_i - p_i)
$$

where

* $f_{\mathrm{ref}}$ is a weighting function depending on the reference neuron  
* $g_{\mathrm{ref}}$ introduces a directional correction  
* $\alpha > 0$ controls the generalized norm  

The first term represents a **weighted $L^\alpha$ distance**, while the second introduces **asymmetry**, leading to a **Finsler-type geometric structure**.

---

# Methodology

The workflow follows:

1. Load neuronal activity data  
2. Compute **correlation matrices** between neurons  
3. Incorporate **orientation selectivity (OSI)** information  
4. Compute pairwise distances using the **Finsler-type metric**  
5. Construct a **distance matrix**  
6. Build a **Vietoris–Rips simplicial complex**  
7. Compute **topological invariants**

This enables the analysis of:

* Betti numbers ($\beta_0, \beta_1, \beta_2$)  
* Euler characteristic  
* topological evolution across thresholds  
* differences across visual stimuli  

---

# Repository Structure

