# Insulation Coordination & Overvoltage Protection of Distribution Transformers

This repository contains the study, modeling, and simulation of **insulation coordination** and overvoltage protection for medium-voltage (MV) distribution transformers ($150/20\text{ kV}$) and interconnected industrial/substation consumers. The analysis and transient simulations were performed using **EMTP/ATP (ATPDraw)**.

## 📌 Project Overview

The project focuses on protecting electrical infrastructure against transient overvoltages, specifically **Lightning Electromagnetic Pulses (LEMP)** and **Switching Surges**. By developing high-fidelity high-frequency models of transmission lines, towers, surge arresters, and substations, we evaluate the dielectric strength (BIL/BSL) of the insulation and optimize protection schemes.

### Core System Technical Data
* **Nominal Voltage:** $150\text{ kV}$ (Transmission) / $20\text{ kV}$ (Distribution)
* **Basic Insulation Level (BIL):** $150\text{ kV}$ or $30\text{ kV}$ depending on the consumer level
* **Software Tools:** EMTP/ATP, ATPDraw, statistical risk estimation toolsets.

---

## 🛠️ Key Engineering Tasks & Implementation

1. **High-Frequency Transmission Line Modeling:** Representation of overhead lines using frequency-dependent or constant-parameter distributed models (JMarti / LCC), including tower surge impedance and footing resistances.
2. **Lightning Surge Analysis (Direct & Indirect Strikes):** Simulation of lightning current waveforms ($1.2/50\ \mu\text{s}$ and $10/350\ \mu\text{s}$) hitting shields, towers, or phases directly, inducing fast-front overvoltages.
3. **Switching Overvoltage Simulation:** Analysis of slow-front transients caused by circuit breaker operations, line energization, and inductive load switching.
4. **Surge Arrester (MOV) Optimization:** Modeling non-linear Metal-Oxide Varistors ($ZnO$ surge arresters) using $V-I$ characteristics to evaluate their protective margins and energy absorption capabilities ($kJ$).
5. **Stochastic Risk of Failure Estimation:** Statistical evaluation of insulation breakdown probability by correlating peak surge current distributions (CIGRE/IEEE standards) with the calculated electric stress.

---

## 📊 Key Findings & Simulation Insights

Transient data simulated via the `.acp` models yielded critical insights into insulation margins:

### Overvoltage Profiles & Protective Margins

| Transients Scenario | Unprotected Peak Voltage | Protected Peak (with Arrester) | Target BIL | Status / Margin |
| :--- | :---: | :---: | :---: | :---: |
| **Direct Lightning Strike (30 kA)** | $>250\text{ kV}$ | $42.3\text{ kV}$ | $150\text{ kV}$ | Safe ($\text{Margin} > 70\%$) |
| **Secondary Consumer Line Transient** | $3.2\text{ kV}$ | $1.42\text{ kV}$ | $1.5\text{ kV}$ | Marginal Breakdowns |
| **Inductive Switching Surge** | $185\text{ kV}$ | $38.1\text{ kV}$ | $150\text{ kV}$ | Safe |

### 📈 Statistical Insulation Failure Analysis
* **Critical Current Evaluation:** For the secondary consumer's equipment (rated at $\text{BIL} = 1.5\text{ kV}$), insulation flashover occurs at lightning currents exceeding $30\text{ kA}$.
* **Probability of Occurrence:** According to cumulative statistical distributions, the probability of a local lightning strike exceeding $132.5\text{ kA}$ was calculated at **0.019%**, while the probability of exceeding the failure threshold ($30\text{ kA}$) is **26.49%**.

> ⚠️ **Engineering Verdict:** A failure probability of **26.49%** confirms that the baseline infrastructure layout without optimized surge protection at the secondary terminal is highly vulnerable. Relocating or resizing the MOV surge arresters closer to the transformer bush terminals is mandatory to satisfy insulation coordination criteria.

---
