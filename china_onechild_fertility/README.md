## Research Questions 📝

- Did the One-Child policy *cause* a significant decline in China’s fertility rates?
- Would fertility trends have been similar without the policy? 

## Background 👥
Concerns about overpopulation peaked in the late 1960s with Paul Ehrlich’s *The Population Bomb*, sparking widespread worry about resource scarcity and population control. Alongside cultural shifts like contraception access and the rise of the "sexual liberation" movement, some governments adopted more direct approaches to managing fertility.

One of the most infamous examples is **China’s One-Child Policy**, implemented in 1979 by the National Population and Family Planning Commission. This policy was enforced both implicitly—through propaganda about being a “responsible citizen”—and explicitly, through fines, forced sterilizations, and abortions. Although rare exceptions were made (such as allowing a second child if the first was a girl), the long-term consequences were severe: a heavily skewed gender ratio, psychological strain on women, and labor shortages due to a shrinking youth population.

As China faced severe demographic decline and growing human rights criticism, the policy was relaxed: first to two children in 2016, and then to three in 2021. Meanwhile, fertility rates have declined globally—including in nearby countries like Vietnam and South Korea, which share regional and demographic similarities with China but did not implement similarly strict fertility limits.

This project explores whether the One-Child Policy uniquely *caused* a significant decline in China’s fertility rates relative to these neighboring countries. It aims to contribute to a broader conversation about the effectiveness of governmental intervention in family planning, separate from moral or ethical considerations.


## Data Sources 📊

- **World Bank Group**: Fertility rate, total (births per woman) from China, Viet Nam, and Korea Rep.
- Time Span: 1960–2023.
- Policy implementation year: 1979 (China only)

## Methodology 🧪
- Cleaned and reformatted time series fertility data for consistency across countries
- Visualized fertility trends with line plots across three countries
- Applied log transformation to linearize exponentially declining fertility patterns for OLS modeling

- Performed a Difference-in-Differences (DiD) analysis comparing pre- and post-1979 fertility trends in China (treatment) vs. Vietnam and South Korea (controls)
- Used matrix-form OLS regression with treatment, post-policy, and interaction (DiD) terms

## Assumptions ⚖️
- Fertility in China would have followed the **same trajectory** as Vietnam/South Korea in the absence of the policy

- Vietnam and South Korea are **appropriate counterfactuals** (due to comparable economic, regional, and demographic characteristics)

- Heterogeneous effects (e.g., rural vs. urban, voluntary vs. forced compliance) are not accounted for in this analysis


## Key Findings & Future Work 📌

- Fertility rates declined sharply across all countries after 1979.
  
- The estimated causal effect of the One-Child Policy on fertility is a modest additional decline beyond these general trends, and thus not statistically significant (P > 0.05).

- Future Directions:
1] Capture underlying pattern through better model fits or multivariate DiD approaches
2] Graph and control for other demographic or socioeconomic trends across countries
3] Use additional data sources to uncover heterogeneous effects (e.g., rural vs. urban, income levels)

## Project Structure 🌳

- `Comparative_Fertility_China.ipynb` — Main notebook with data cleaning, visualization, and analysis.
- `fertility_rates.csv` — Cleaned dataset for the analysis.
- `OneChildPolicy.pdf` — Summary of the model, findings, and broader policy implications.

## Tools Used ⚙️

- Python (`pandas`, `numpy`, `statsmodels`, `matplotlib`, `seaborn`)
- Jupyter Notebook
- Difference-in-Differences methodology using OLS regression

## How to Run ✅

1. Open the Jupyter notebook `Comparative_Fertility_China.ipynb` in VS Code or Jupyter Lab.
2. Load the cleaned `fertility_rates.csv` dataset or retrieve the raw dataset from World Bank Group. 
3. Run the notebook cells sequentially to reproduce the plots and analysis.
---
