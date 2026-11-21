# Steel Plate Defect Analysis

A quality-analysis project that applies Pareto analysis, root cause analysis (fishbone and 5 Why) and statistical process control to steel plate inspection data, built in Excel.

## Objective
To find out which fault types drive most defects in steel plate production, investigate the likely causes of the largest named fault, and check process stability using control charts.

## Dataset
- **Source:** Steel Plates Faults dataset, UCI Machine Learning Repository
- **Size:** 1,941 inspection records, 27 measurement features, 7 fault categories (Pastry, Z_Scratch, K_Scratch, Stains, Dirtiness, Bumps, Other_Faults)
- Each record is labelled with exactly one fault type.

## Tools
Excel (Excel for the web): formulas (`SUM`, `VLOOKUP`), combo charts, pivot tables. Fishbone drawn in draw.io.

## Method
1. **Data check:** confirmed 1,941 records and that fault counts sum to the total.
2. **Pareto analysis:** counted each fault type, sorted by frequency, and calculated cumulative % to find the vital few.
3. **Root cause analysis:** built a fishbone diagram and 5 Why chain for the largest named fault (Bumps). **[ADD LATER]**
4. **SPC:** built X-bar and R control charts on [measurement column] with subgroup size 5 to check process stability. **[ADD LATER]**

## Key Findings

| Fault type | Count | Share | Cumulative % |
|---|---|---|---|
| Other_Faults | 673 | 34.7% | 34.7% |
| Bumps | 402 | 20.7% | 55.4% |
| K_Scratch | 391 | 20.1% | 75.5% |
| Z_Scratch | 190 | 9.8% | 85.3% |
| Pastry | 158 | 8.1% | 93.5% |
| Stains | 72 | 3.7% | 97.2% |
| Dirtiness | 55 | 2.8% | 100% |

- The top 3 categories account for **75.5%** of all faults, and the top 4 for **85.3%**.
- **Other_Faults** is a catch-all category, so it cannot be investigated as a single defect. Finer classification would be needed.
- **Bumps** is the largest *specific* fault (20.7%), so it was chosen for root cause analysis.
- Fishbone and 5 Why results for Bumps: **[ADD LATER]**
- X-bar/R results: [N] out-of-control subgroups on [measurement]. **[ADD LATER]**

## Pareto Chart
![Pareto chart](images/pareto_chart.png)

## Fishbone Diagram **[ADD LATER]**
![Fishbone](images/fishbone_bumps.png)

## Limitations
- Causes on the fishbone are hypotheses from process knowledge, not proven causes, unless backed by the data comparison noted in the analysis.
- The data is a static snapshot, so the control charts treat consecutive records as a time sequence for demonstration, not as a live production process.
- Other_Faults limits how specific the conclusions can be.

## Files
- `Defect_Analysis.xlsx`: data, Pareto table, charts and summary
- `images/`: exported chart images

## Author
Alisha Mariyam Hussain | B.Tech ECE, BIT Mesra
[LinkedIn link] | alishamariyamh@gmail.com
