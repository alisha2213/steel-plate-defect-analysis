# Steel Plate Defect Analysis

Pareto analysis, root cause analysis (fishbone and 5 Why) and SPC control charts on steel plate inspection data, built in Excel.

## Objective
Find which fault types drive most defects, investigate the largest specific fault, and check how a key measurement behaves on X-bar/R control charts.

## Dataset
Steel Plates Faults, UCI Machine Learning Repository: 1,941 inspection records with 7 fault categories (Pastry, Z_Scratch, K_Scratch, Stains, Dirtiness, Bumps, Other_Faults). Each record has exactly one fault label.

## Tools
Excel (formulas such as SUM, VLOOKUP, AVERAGEIFS, COUNTIFS, SUMIFS; combo and line charts) and draw.io-style fishbone.

## Method
1. Data check: 1,941 records, fault counts sum to the total.
2. Pareto: counted and sorted faults, calculated cumulative %.
3. Data check for Bumps: compared Bump rate by steel type and compared measurement averages.
4. Root cause: fishbone and 5 Why for Bumps.
5. SPC: X-bar and R charts on Steel_Plate_Thickness, 25 subgroups of 5 consecutive records.

## Key Findings
| Fault | Count | Share | Cumulative |
|---|---|---|---|
| Other_Faults | 673 | 34.7% | 34.7% |
| Bumps | 402 | 20.7% | 55.4% |
| K_Scratch | 391 | 20.1% | 75.5% |
| Z_Scratch | 190 | 9.8% | 85.3% |
| Pastry | 158 | 8.1% | 93.5% |
| Stains | 72 | 3.7% | 97.2% |
| Dirtiness | 55 | 2.8% | 100% |

- Top 3 categories account for 75.5% of faults.
- Other_Faults is a catch-all, so Bumps is the largest specific fault.
- Bump rate is 35.9% on A300 steel vs 10.6% on A400, about 3.4 times higher.
- Bumps cover a much smaller area than other faults on average, so they are small surface defects.
- SPC: X-bar limits 60.9 to 138.6, R limits 0 to 142.4, [N] subgroups outside limits.

## Charts
![Pareto](images/pareto_chart.png)
![Fishbone](images/fishbone_bumps.png)
![X-bar](images/xbar_chart.png)
![R chart](images/r_chart.png)

## Limitations
- The A300 link is an association, not proof of cause. Other fishbone causes are hypotheses.
- The records are not a live time series. Thickness is set by each plate order, so the control-chart signals mostly reflect changes between product orders. A real study would chart deviation from target within one product type.
- Other_Faults limits how specific the conclusions can be.

## Files
- `Defect_Analysis.xlsx`: data, Pareto, Bumps check, 5 Why, SPC and summary sheets
- `images/`: chart images

## Data source
UCI Machine Learning Repository, Steel Plates Faults dataset.

## Author
Alisha Mariyam Hussain, B.Tech ECE, BIT Mesra | alishamariyamh@gmail.com
