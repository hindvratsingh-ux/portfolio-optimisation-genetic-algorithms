# Portfolio Optimisation using Genetic Algorithms

## Overview
This project explores the use of genetic algorithms (GAs) to optimize portfolio construction by balancing expected return and risk. The work was completed in R as part of an MSc assignment focused on financial optimization and evolutionary computation.

## Objective
The objective of this project was to develop a GA-based portfolio optimization framework that:
- identifies optimal portfolio weights for a selected set of assets,
- evaluates out-of-sample performance on unseen future data,
- compares optimized portfolios against equal-weight and random baselines,
- explores different return-risk preferences through alternative fitness weightings,
- and extends the approach to asset selection from a larger investment universe.

## Dataset
Historical daily adjusted closing prices were collected from Yahoo Finance for 50 assets covering the period from January 2018 to December 2020. The data was split into:
- Training period: 2018–2019
- Test period: 2020

A manually selected 10-asset portfolio was built from multiple sectors to improve diversification:
- Technology: AAPL, MSFT
- Financials: JPM, GS
- Healthcare: JNJ, PFE
- Consumer: WMT, PG
- Energy: XOM, CVX

## Tools and Libraries
- R
- GA
- quantmod
- PerformanceAnalytics
- ggplot2
- R Markdown

## Methodology

### 1. Portfolio weight optimisation
A real-valued genetic algorithm was used to optimize portfolio weights for the selected 10 assets. The fitness function balanced mean portfolio return against portfolio risk using an alpha parameter:

`fitness = alpha × mean_return - (1 - alpha) × risk`

This allowed the GA to search for allocations with a desirable risk-return trade-off.

### 2. Out-of-sample evaluation
The optimized portfolio weights found on the training data were applied unchanged to 2020 test data to evaluate whether the portfolio generalized to unseen market conditions.

### 3. Baseline comparison
The GA-optimized portfolio was compared against:
- an equal-weight portfolio,
- and the average performance of randomly generated portfolios.

This helped assess whether optimization produced a meaningful improvement over simple benchmark strategies.

### 4. Risk-return preference analysis
The GA was re-run with different alpha values (0.1, 0.5, and 0.9) to simulate different investor preferences, from risk-averse to return-seeking behaviour.

### 5. Asset selection using GAs
The project was extended in two ways:
- **Independent binary GA:** selected assets from a larger pool of 50 stocks.
- **Integrated nested GA:** used an outer GA for asset selection and an inner GA for weight optimization.

This allowed both asset choice and allocation to be optimized within the same broader framework.

## Key Outcomes
- Built a GA-based portfolio optimization system in R using financial market data.
- Evaluated portfolio performance on unseen test data rather than relying only on in-sample results.
- Benchmarked the optimized portfolio against equal-weight and random portfolios.
- Demonstrated how changing alpha changes the portfolio’s risk-return profile.
- Extended the solution from weight optimization to asset selection using binary and nested GAs.

## Repository Contents
- `finance-project.Rmd` — full R Markdown source code for the project
- `portfolio_optimisation_report.pdf` — final knitted report
- `README.md` — project summary and documentation

## Why This Project Matters
This project demonstrates practical skills in:
- financial data analysis,
- portfolio construction,
- optimization,
- out-of-sample evaluation,
- algorithm design,
- and quantitative modelling in R.

## Author
Hindvrat Singh Rao
