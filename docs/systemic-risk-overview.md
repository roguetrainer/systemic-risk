# **Systemic Risk Models in a Nutshell**

"In a crisis, correlations go to one."

## **The Pre-2008 Blind Spot**

Before the Global Financial Crisis (GFC) of 2008, quantitative finance was dominated by the "representative agent" view or the isolationist view. Quants optimized the risk of single institutions (Micro-prudential regulation) under the assumption that the "system" was simply a stable background against which idiosyncratic risks played out.

Network modelling was largely absent from the trading floor. The interconnectedness of balance sheets was treated as a second-order effect. The 2008 crash revealed that **network topology** is not a detail—it is the primary driver of catastrophe. When Lehman Brothers fell, it wasn't just a large loss; it was a node removal that triggered a phase transition in the global financial graph.

Post-2008, systemic risk modelling transitioned from an academic niche to a regulatory necessity.

## **The Mechanism of Doom: The Four Ls**

To understand how a localized shock becomes a global collapse, we look to the framework often summarized as the **Four Ls**.

### **1\. Loss (The Shock)**

The initial spark. A drop in asset values (e.g., subprime mortgages) that erodes the equity capital of one or more institutions.

* *Modelling:* Standard market risk models (VaR, Expected Shortfall).

### **2\. Leverage (The Amplifier)**

High leverage means thin equity buffers. When assets fall, leveraged institutions must deleverage to restore ratios.

* *The Mechanic:* A small % drop in asset value leads to a large % drop in equity.

### **3\. Liquidity (The Accelerant)**

When everyone tries to deleverage simultaneously, they sell liquid assets. This causes **Fire Sales**.

* *The Spiral:* Asset Price $\\downarrow$ $\\rightarrow$ Margin Calls $\\rightarrow$ Forced Selling $\\rightarrow$ Asset Price $\\downarrow\\downarrow$.  
* *Reference:* [silicon-subprime](https://github.com/roguetrainer/silicon-subprime) (Simulating liquidity crises and bank runs).

### **4\. Linkages (The Transmission)**

The direct connections between firms via interbank loans, derivatives, and cross-holdings.

* *The Result:* Default cascades. Bank A fails, causing a loss for creditor Bank B, pushing Bank B into insolvency.

## **Beyond Dominoes: The Invisible Linkages**

While "Default Cascades" (Dominoes) get the most attention, they are empirically rare. Real crises spread through **indirect** channels where banks destroy each other without ever lending to one another.

### **5\. Common Asset Holdings (Portfolio Overlap)**

Even if Bank A and Bank B have no direct business, they are linked if they hold the same assets.

* **Mechanism:** Bank A is forced to sell Asset X. The price of X drops. Bank B must mark Asset X to market, losing equity.  
* **Result:** Contagion via the price vector. The more similar the portfolios of the banking sector, the higher the systemic risk (even if diversification looks good individually).  
* **Key Metric:** Cosine similarity of asset vectors between institutions.

### **6\. Informational Contagion (The Wake-Up Call)**

Investors operate with imperfect information. When a specific bank fails, the market does not assume it is idiosyncratic; it treats it as a signal about a hidden common factor.

* **Mechanism:** Bank A fails due to "Duration Risk" (e.g., SVB 2023). Investors instantly screen for *other* banks with similar characteristics and run on them, regardless of their actual health.  
* **The logic:** "If it happened to them, it could happen to you."

### **7\. Precautionary Hoarding (Funding Contagion)**

In times of high uncertainty, banks stop lending to *anyone* (even solvent counterparties) to preserve their own liquidity buffer.

* **Mechanism:** A freeze in the interbank market. The "velocity of money" drops to zero. Solvent banks fail because they cannot roll over short-term funding.

### **8\. The Market-Funding Liquidity Spiral**

Defining the interaction between a trader's ease of trading and their ease of borrowing (Brunnermeier & Pedersen, 2009).

* **Loop:** Traders experience losses $\\rightarrow$ Margins increase (Funding Liquidity tightens) $\\rightarrow$ Traders must sell assets $\\rightarrow$ Market Liquidity dries up $\\rightarrow$ Volatility increases $\\rightarrow$ Margins increase further.

## **The Deep Plumbing: Money Creation & Shadow Banking**

To truly understand systemic risk, one must look beyond the banks' balance sheets to the **nature of money itself**.

### **Market-Based Finance (Shadow Banking)**

Traditional money creation happens when a commercial bank extends a loan, creating a deposit. In the modern "Shadow Banking" system (better termed **Market-Based Finance**), money is effectively created through **Repurchase Agreements (Repo)** and rehypothecation.

* **Perry Mehrling’s "Money View":** Mehrling argues that we cannot separate finance from money. In the modern system, liquidity is not just cash reserves; it is the ability to roll over short-term funding in the repo market. Solvency depends on liquidity.  
* **Zoltan Pozsar’s "Financial Plumbing":** Pozsar meticulously mapped the shadow banking system, revealing it not as a chaotic unregulated mess, but as a structured machine designed to transform risky assets into the "safe" money-like claims demanded by institutional cash pools. He highlights that **institutional cash pools** (sovereign wealth funds, corporate treasuries) are the dominant force, and their demand for safety drives the supply of shadow money.

### **The Safe Asset Shortage**

Why did the system load up on subprime mortgages? It wasn't just greed; it was a structural demand for collateral.

1. Global institutional cash pools needed a place to park cash safely (yielding \>0%).  
2. Repo contracts require **Safe Assets** (like US Treasuries) as collateral.  
3. There was a global shortage of US Treasuries relative to the demand for repo.  
4. **The Engineering Solution:** Wall Street "manufactured" safe assets by bundling risky subprime mortgages and tranching them until the top layer was rated **AAA**.

### **The Collateral Run**

The 2008 crisis was, at its heart, a run on this manufactured collateral. When the market realized the "AAA" MBS were not actually safe, the panic manifested differently than 1929:

* **Gary Gorton’s "Run on Repo":** In a traditional bank run, depositors line up to withdraw cash. In the GFC, the "depositors" were institutional lenders (like Money Market Funds) and the "withdrawal" was an **increase in haircuts**.  
  * *The Haircut Spiral:* If you lend $100 against collateral with a 0% haircut, you are fully funded. If the market demands a 20% haircut, you must suddenly post $20 cash or sell the asset.  
  * Gorton famously argued: *"The crisis was not a stock market crash; it was a run on the repo market."*  
* **Daniela Gabor’s Critical Macro-Finance:** Gabor highlights how the state (via Central Banks) is forced to become the "Market Maker of Last Resort," backstopping not just commercial banks, but the price of collateral itself to prevent the implosion of this market-based monetary system.


## **The Cassandras: Who Saw It Coming?**

While the mainstream consensus was that the "Great Moderation" had solved volatility, a few distinct voices correctly identified the building fragility.

* **William White (The Insider):** As Chief Economist at the **BIS**, White was one of the few high-level insiders to warn that the policy of "cleaning up after bubbles burst" rather than "leaning against the wind" was creating dangerous imbalances. His warnings were largely ignored by the Fed (Greenspan/Bernanke) at the time.  
* **Steve Keen (The Minsky Disciple):** An Australian economist who applied Hyman Minsky's **Financial Instability Hypothesis**. He focused intensely on the ratio of **Private Debt to GDP**. He argued that the rate of change of credit (the credit impulse) drives aggregate demand, and that a collapse in credit growth would cause a severe recession.  
* **Rick Bookstaber (The Practitioner):** A veteran risk manager (Morgan Stanley, Salomon). In *A Demon of Our Own Design*, he argued that **complexity** and **tight coupling** in financial markets make crises inevitable. Unlike academic economists, he understood the mechanical plumbing of derivatives.  
  * *Post-Crisis Contribution:* Bookstaber went on to the **Office of Financial Research (OFR)** where he pioneered the use of **Agent-Based Models (ABM)** to simulate systemic risk, moving away from equilibrium economics toward complex systems theory.

## **The Watchtowers: Key Systemic Risk Organizations**

In response to the GFC, the world created a new infrastructure to watch the watchers.

### **Global**

* **BIS (Bank for International Settlements):** The "Central Bank of Central Banks" in Basel. It hosts the **Basel Committee**, which sets global capital standards (Basel III/IV).  
* **FSB (Financial Stability Board):** Established to coordinate regulation internationally, monitoring the shadow banking sector and "Too Big To Fail" (G-SIB) lists.  
* **IOSCO (International Organization of Securities Commissions):** Sets standards for securities markets, increasingly focused on systemic risk in asset management and CCPs.

### **United States**

* **OFR (Office of Financial Research):** Created by the Dodd-Frank Act. A unique body dedicated to data collection and applied research on financial stability (home to Bookstaber's ABM work).  
* **FSOC (Financial Stability Oversight Council):** The political body (chaired by the Treasury Secretary) with the power to designate non-banks (like insurers) as systematically important (SIFIs).

### **Europe & UK**

* **ESRB (European Systemic Risk Board):** The macro-prudential oversight body of the EU.  
* **FPC (Financial Policy Committee):** The UK's dedicated macro-prudential regulator within the Bank of England, with the power to alter capital buffers counter-cyclically.

### **Japan**

* **BoJ (Bank of Japan):** The Financial System and Bank Examination Department publishes the semi-annual *Financial System Report*, closely monitoring the link between JGB yields and regional bank stability.

## **Standard Systemic Metrics**

Modern systemic risk is quantified using metrics that capture the *conditional* distress of the system.

* **CoVaR (Conditional Value at Risk):** The VaR of the financial system *conditional* on institution $i$ being in distress. It measures the contribution of a single firm to systemic risk.  
* **SRISK:** The expected capital shortfall of a firm conditional on a prolonged market decline (e.g., a 40% drop in the index over 6 months). It is a function of size, leverage, and correlation with the market.  
* **DIF (Distress Insurance Premium):** A market-based measure of the cost to insure the financial system against collapse.

## **Tribute: The Unification of Systemic Risk**

The field of systemic risk is fragmented, with distinct models for solvency contagion (Eisenberg-Noe) and liquidity contagion (Cifuentes et al.).

We must acknowledge the profound contributions of **Professor Tom Hurd** (McMaster University), a brilliant mathematician and distinguished quant who passed away in 2022\. Tom was a pioneer in applying rigorous network science to finance.

In his seminal book *Contagion\! Systemic Risk in Financial Networks*, Hurd sought to unify these disparate mechanisms into a coherent mathematical framework. He refused to let his skills become "rusty," constantly pushing the boundary where graph theory meets stochastic analysis. His work remains the gold standard for understanding how shocks propagate through the "neuronal" network of global banking.

## **Selected Bibliography & Surveys**

For the Rusty Quant looking to become a Systemic Risk expert, start here:

**The Classics**

* **Eisenberg, L., & Noe, T. H. (2001).** *Systemic Risk in Financial Systems.* Management Science.  
* **Cifuentes, R., Ferrucci, G., & Shin, H. S. (2005).** *Liquidity Risk and Contagion.* Journal of the European Economic Association.  
* **Brunnermeier, M. K., & Pedersen, L. H. (2009).** *Market Liquidity and Funding Liquidity.* Review of Financial Studies. (The Liquidity Spiral).

**The Money View & Plumbing**

* **Gorton, G., & Metrick, A. (2010).** *Securitized Banking and the Run on Repo.* Journal of Financial Economics. (Defining the crisis as a haircut spiral).  
* **Gorton, G. (2010).** *Slapped by the Invisible Hand: The Panic of 2007\.* Oxford University Press.  
* **Pozsar, Z., Adrian, T., Ashcraft, A., & Boesky, H. (2010).** *Shadow Banking.* Federal Reserve Bank of New York Staff Reports. (The famous "Map").  
* **Mehrling, P. (2011).** *The New Lombard Street.* Princeton University Press.  
* **Gabor, D. (2016).** *The (impossible) repo trinity.* Review of International Political Economy.

**Key Surveys**

* **Caccioli, F., Barucca, P., & Teramoto, T. (2018).** *Network Models of Systemic Risk: A Review.*  
* **Hurd, T. R. (2016).** *Contagion\! Systemic Risk in Financial Networks.* Springer.  
* **Bookstaber, R. (2017).** *The End of Theory: Financial Crises, the Failure of Economics, and the Sweep of Human Interaction.* Princeton University Press. (On Agent-Based Modelling).

**Implementation**

* [**silicon-subprime**](https://github.com/roguetrainer/silicon-subprime): An agent-based simulation of the 2023 Silicon Valley Bank run, demonstrating the speed of modern liquidity failures.