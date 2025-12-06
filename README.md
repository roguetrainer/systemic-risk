# Systemic Risk

**"In a crisis, correlations go to one."**

An umbrella repository for systemic risk research, documentation, and quantitative implementations. This repo serves as the central hub for understanding financial contagion, network collapse, and the deep plumbing of modern market-based finance.

## Overview

Before 2008, quantitative finance treated the financial system as a stable background. The Global Financial Crisis revealed that **network topology is not a detail—it is the primary driver of catastrophe**. This collection of repositories explores the mechanisms through which localized shocks become global collapse.

## Documentation

### Core Concepts

- [Systemic Risk Overview](docs/systemic-risk-overview.md) - A comprehensive introduction to systemic risk models, covering:
  - The Four Ls: Loss, Leverage, Liquidity, and Linkages
  - Direct and indirect contagion mechanisms
  - The Money View and shadow banking plumbing
  - Key thinkers who predicted the 2008 crisis
  - Modern systemic risk metrics (CoVaR, SRISK, DIF)

- [The GPU-Financial Complex](docs/gpu-financial-complex.md) - A 2025 case study examining whether history is repeating itself with compute-backed collateral

## Related Repositories

### Core Projects

- [**systemic-risk-metrics**](https://github.com/roguetrainer/systemic-risk-metrics) - Jupyter notebooks demonstrating various types of models for systemic financial risk, including indicator back-testing, network construction, network analytics, statistical stress-testing, and economic models. Implementations in Python and R covering ABCE agent-based modeling, GARCH models, Bayesian network reconstruction, and time series filtering for early warning indicators.

- [**systemic-risk-intro**](https://github.com/roguetrainer/systemic-risk-intro) - Guest lecture materials from the University of Toronto Masters in Finance & Insurance program (March 2022), including presentation slides and code demonstrations bridging theoretical concepts with hands-on programming examples.

- [**silicon-subprime**](https://github.com/roguetrainer/silicon-subprime) - Quantitative risk models examining structural vulnerabilities in AI infrastructure financing. Simulates systemic risks from asset-liability mismatches in GPU-backed private credit markets, including Monte Carlo analysis of LTV covenant breaches and network contagion across credit syndicates. Models the "refinancing wall" scenario where rapidly depreciating GPU collateral fails to support 5-year debt structures.

### Applied Research & Tools

- [**too-big-to-teraflop**](https://github.com/roguetrainer/too-big-to-teraflop) - Interactive economic simulation game demonstrating Hyman Minsky's Financial Instability Hypothesis through AI infrastructure investment. Players trade alongside AI agents through the five bubble stages, illustrating how stable periods encourage excessive risk-taking. Standalone HTML application with full React source code.

- [**rusty-quant**](https://github.com/roguetrainer/rusty-quant) - Umbrella project and roadmap for modernizing quantitative finance practices post-2008. Addresses counterparty risk & XVA integration, computational scaling through deep learning, and high-dimensional modeling beyond traditional Monte Carlo. Functions as a curated reference guide organizing recommendations across yield curve construction, XVA frameworks, and systemic risk analysis.

- [**around-the-world-in-81-repos**](https://github.com/roguetrainer/around-the-world-in-81-repos) - Demonstration of rapid numerical research acceleration through human-AI collaboration. Quick-and-dirty explorations across quantum computing (Qiskit, PennyLane), economic modeling, statistical physics, and financial analysis. Showcases effective AI collaboration practices rather than production-ready code.

## The Mechanisms of Contagion

Modern systemic risk models recognize multiple transmission channels:

1. **Default Cascades** - Direct counterparty failures through interbank lending
2. **Fire Sales** - Forced asset liquidation driving price spirals
3. **Portfolio Overlap** - Contagion via common asset holdings (cosine similarity)
4. **Informational Contagion** - Market updating on hidden common factors
5. **Funding Freezes** - Precautionary hoarding in the interbank market
6. **Liquidity Spirals** - The deadly feedback loop between market and funding liquidity

## Key Frameworks

### The Money View

Understanding systemic risk requires looking beyond balance sheets to the **nature of money itself**:

- **Perry Mehrling** - Money cannot be separated from finance; liquidity is the ability to roll over short-term funding
- **Zoltan Pozsar** - Mapped the shadow banking system as structured transformation of risky assets into safe, money-like claims
- **Gary Gorton** - The 2008 crisis was a "run on repo," manifesting as a haircut spiral rather than traditional bank withdrawals
- **Daniela Gabor** - Central Banks forced to become "Market Maker of Last Resort," backstopping collateral prices

### The Cassandras

Those who saw 2008 coming:

- **William White** (BIS) - Warned that "cleaning up after bubbles" creates dangerous imbalances
- **Steve Keen** - Applied Minsky's Financial Instability Hypothesis, focusing on private debt-to-GDP
- **Rick Bookstaber** - Identified complexity and tight coupling as making crises inevitable; pioneered Agent-Based Models at the OFR

## Contributing

This is an active research area. Contributions, corrections, and extensions are welcome across all related repositories.

## Bibliography

The [overview document](docs/systemic-risk-overview.md) contains a comprehensive bibliography including:

- **The Classics**: Eisenberg-Noe (2001), Cifuentes et al. (2005), Brunnermeier-Pedersen (2009)
- **The Money View**: Gorton, Pozsar, Mehrling, Gabor
- **Network Models**: Caccioli et al. (2018), Hurd (2016)
- **Agent-Based Approaches**: Bookstaber (2017)

## Tribute

This work stands on the shoulders of **Professor Tom Hurd** (McMaster University, 1955-2022), whose book *Contagion! Systemic Risk in Financial Networks* unified disparate contagion mechanisms into a coherent mathematical framework. His rigorous application of network science to finance remains the gold standard.

## License

See individual repositories for specific licensing information.

---

**roguetrainer** | [GitHub Profile](https://github.com/roguetrainer)
