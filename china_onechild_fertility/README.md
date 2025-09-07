## Research Questions 📝

- Did the One-Child policy *cause* a significant decline in China’s fertility rates?
- Would fertility trends have been similar without the policy? 

## Background 👥
Concerns about overpopulation peaked in the late 1960s, when biologist Paul Ehrlich warned in his famous book *The Population Bomb* that rapid population growth would lead to resource scarcity, creating a sense of urgency around population control. As cultural attitudes toward fertility shifted—driven in part by the sexual "liberation" movement and expanded access to contraception—some governments adopted more interventionist approaches to managing reproduction.

One of the most infamous examples is **China’s One-Child Policy**, implemented in 1979 by the National Population and Family Planning Commission. This policy was enforced both implicitly—through propaganda about being a “responsible citizen”—and explicitly, through fines, forced sterilizations, and abortions. Although rare exceptions were made (such as allowing a second child if the first was a girl), the long-term consequences were severe: a heavily skewed gender ratio, psychological strain on women, and labor shortages due to a shrinking youth population.

As China faced severe demographic decline and growing human rights criticism, the policy was relaxed: first to two children in 2016, and then to three in 2021. Meanwhile, fertility rates have declined globally—including in nearby countries like Vietnam and South Korea, which share regional and demographic similarities with China but did not implement similarly strict fertility controls.

This project explores whether the One-Child Policy uniquely *caused* a significant decline in China’s fertility rates beyond what we would have expected based on regional and demographic trends. The primary method used is **Synthetic Control**, which constructs a weighted combination of countries that closely match China’s pre-policy characteristics. This approach helps isolate the policy’s causal effect from broader social and economic shifts. Ultimately, the goal is to inform broader discussions about the effectiveness of state-led family planning interventions, independent of their ethical implications.

## Data 📊
*Source: World Bank Group*
#### Primary Outcome 
- Measuring: Fertility rate, total (births per woman) 
- Time Span: 1960–2023.
- Policy implementation year: 1979 (China only)

#### Covariates 

- GDP per capita (USD)
- Infant mortality rate (per 1,000 live births)
- Female educational attainment (upper secondary completion; data begins ~1970)
- Contraception prevalence (% of married women using any method; data begins ~1961)
- Urban population (% of total population)

## Methodology 🧪
- Cleaned and reformatted time series fertility data for consistency across countries
- Visualized fertility trends with line plots across three countries
- Applied log transformation and Moving Averages smoothing technique to linearize exponentially declining fertility patterns for OLS modeling

- Performed a Difference-in-Differences (DiD) analysis comparing pre- and post-1979 fertility trends in China (treatment) vs. Vietnam and South Korea (controls)
- Used matrix-form OLS regression with treatment, post-policy, and interaction (DiD) terms

## Assumptions ⚖️
- Fertility in China would have followed the **same trajectory** as Vietnam/South Korea in the absence of the policy

- Vietnam and South Korea are **appropriate counterfactuals** (due to comparable economic, regional, and demographic characteristics) in Part 1

- Heterogeneous effects (e.g., rural vs. urban, voluntary vs. forced compliance) are not taken into account 

## Project Structure 🌳

- `part1_EDA_regression.ipynb` — Part 1 of notebook with data cleaning, visualization, and regression analysis.
- `part2_synthetic_control.ipynb` - Part 2 of notebook with synthetic control method and regression.
- `fertility_rates.csv` — Cleaned dataset for the analysis.
- `OneChildPolicy.pdf` — Summary of the model, findings, and broader policy implications.

## Tools Used ⚙️

- Python (`pandas`, `numpy`, `statsmodels`, `matplotlib`, `seaborn`)
- Jupyter Notebook
- Difference-in-Differences methodology using OLS regression
- Synthetic Control Method 

## How to Run ✅

1. Open the Jupyter notebooks `part1_EDA_regression.ipynb` and `part2_synthetic_control.ipynb` in VS Code or Jupyter Lab.
2. Load the cleaned `fertility_rates.csv` dataset or retrieve the raw dataset from World Bank Group. 
3. Run the notebook cells sequentially to reproduce the plots and analysis.


## Key Findings & Future Work 📌

- Fertility rates declined sharply across all countries after 1979.
  
- The estimated causal effect of the One-Child Policy on fertility is a modest additional decline beyond these general trends, and thus not statistically significant (P > 0.05).

- Future Directions:
    1. Capture underlying pattern through better model fits or multivariate DiD approaches
    2. Graph and control for other demographic or socioeconomic trends across countries
    3. Use additional data sources to uncover heterogeneous effects (e.g., rural vs. urban, income levels)
---
