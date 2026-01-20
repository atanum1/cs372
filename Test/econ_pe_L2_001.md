# Economics Causal Scenario — Price Elasticity (L2)

**Case ID:** PE-L2-01  
**Bucket:** T3_ECON_PRICE_ELASTICITY  
**Pearl Level:** L2 — Intervention  
**Domain:** Economics (D5)  
**Difficulty:** Medium  

---

## Scenario

A city mandates a **15% increase in taxi fares**. After the policy is implemented, the **number of taxi rides declines only slightly**.  
A policy analyst concludes that **taxi demand is price inelastic**.

---

## Claim

> The fare increase caused taxi demand to be price inelastic.

---

## Label

- **Decision:** NO  
- **Label Name:** FLAWED  
- **Ambiguous:** No  

---

## Trap Classification

- **Trap Type:** CONF (Confounding)  
- **Subtype:** Concurrent Demand Shock  
- **Explanation:**  
  Unobserved demand conditions may influence both the timing of the fare increase and the observed number of taxi rides.

---

## Variables

- **X (Intervention):** Taxi fare increase  
- **Y (Outcome):** Number of taxi rides  
- **Z (Confounder):** Urban mobility demand shock  

---

## Causal Structure (DAG)

**Edges:**
- Z → X  
- Z → Y  
- X → Y  

**Interpretation:**  
A demand shock (Z) affects both pricing decisions (X) and ride volume (Y), confounding the observed effect of the fare increase.

---

## Temporal Structure (L2 Requirement)

- **Timestamp Type:** Relative timing between intervention and confounder  

**Conditional Answers:**
- If **t(X) < t(Z)** → **NO**  
- If **t(Z) < t(X)** → **MAYBE**

**Explanation:**  
If the demand shock occurs after the fare increase, the weak response may reflect true inelasticity.  
If the demand shock precedes the intervention, the observed stability in rides is confounded.

---

## Key Insight

Intervening on price does not identify true price elasticity unless **the timing of demand shocks relative to the intervention is established**.

---

## Gold Rationale

The analyst’s conclusion is flawed because the intervention coincides with unobserved demand conditions that affect both prices and quantity.  
Without isolating the price change from concurrent demand shocks, the observed response cannot be interpreted as causal evidence of inelastic demand.

---

## Annotation Metadata

- **Author:** Atanu Mukherjee  
- **Annotators:** 1  
- **Agreement:** 1.0  
- **Adjudicated:** No  
- **Wise Refusal:** False  

---

## Notes

This is a well-posed **L2 causal intervention case** with explicit DAG structure and timestamp-conditioned reasoning.  
The ambiguity is resolvable through temporal ordering, so refusal is not appropriate.
