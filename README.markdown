# Statistical Analysis of Indian Cricket Team in One Day International (ODI)

## Project Overview
This project conducts a comprehensive statistical analysis of the Indian Cricket Team's performance in One Day International (ODI) matches, focusing on batting, bowling, and team outcomes from 2019 to 2023. Led by a team of NMIMS Mumbai students (Nidhi Karambelkar, Sean Minezes, Akshay Mirani, Jash Moze, Veer Shah) under Prof. Vaibhav Vasundekar, the study uses statistical tests and indices to evaluate player and team performance, propose an ideal ODI team, and uncover data-driven insights for strategic decision-making in cricket.

## Objectives
- Compare team batting performances between 2019 and 2022 using a t-test for two population means.
- Test equality of means of economy rates for spinners and pacers using a t-test.
- Evaluate Rohit Sharma’s captaincy (2019–2023) via a binomial test of single population proportion.
- Assess independence of venue and match outcome using a Chi-Square test.
- Assess independence of toss winning and match outcome using a Chi-Square test.
- Compare variances of batting performances (2019 vs. 2022) and economy rates (spinners vs. pacers) using F-tests.
- Select an ideal Indian ODI team based on batting, bowling, and all-rounder indices.

## Data Source
- **Source**: Secondary data from [ESPNcricinfo](https://stats.espncricinfo.com/ci/engine/stats/index.html).
- **Details**: Includes batting (e.g., runs, strike rate, average) and bowling (e.g., economy, wickets, maidens) statistics for 49 batters, 49 bowlers, and 28 all-rounders, covering ODI matches from 2019 to 2023.

## Methodology
The analysis employs statistical tests and custom indices, implemented in Python and R (assumed based on statistical rigor):

1. **Chi-Square Test of Independence**:
   - Tested independence of venue and match outcome, and toss winning and match outcome.
   - Assumptions: Categorical variables, independent observations.
   - Formula: \(\chi^2 = \sum \frac{(O_i - E_i)^2}{E_i}\), where \(O_i\) is observed frequency, \(E_i\) is expected frequency.

2. **Poisson Distribution Fitting**:
   - Fitted Poisson distribution to catches taken, validating with a Q-Q plot.
   - Assumptions: Events occur independently, constant rate.
   - Conclusion: P-value > 0.05, confirming Poisson fit.

3. **Binomial Test for Captaincy**:
   - Evaluated Rohit Sharma’s captaincy win proportion (2019–2023).
   - Assumptions: Binary outcomes (win/loss), independent trials, fixed trials.
   - Significance level: \(\alpha = 0.05\).

4. **F-Test for Variances**:
   - Compared variances of economy rates (spinners vs. pacers) and batting performances (2019 vs. 2022).
   - Assumptions: Normal distribution, independent populations, larger variance in numerator.

5. **T-Test for Means**:
   - Compared mean economy rates of spinners and pacers, and batting performances (2019 vs. 2022).
   - Assumptions: Independent samples, normal populations, equal/unequal variances.

6. **Team Selection**:
   - **Batters**: Selected via two rounds:
     - Round 1: Top 20 by strike rate, average, highest score (13 candidates).
     - Round 2: Batting Index = \( \text{Batting Average} \times \text{Strike Rate} \times \text{Consistency} \times \text{Weighted Centuries} \times \text{Weighted Half-Centuries} \times \text{Weighted Experience} \times \text{Weighted Hard-Hitting Ability} \).
     - Final: Rohit Sharma, Virat Kohli, Shreyas Iyer, Shubman Gill, Ishan Kishan (RR Pant excluded due to injury).
   - **Bowlers**: Selected via two rounds:
     - Round 1: Top 20 by economy, bowling average, strike rate (13 candidates).
     - Round 2: Bowling Index = \(\frac{\text{Weighted Maidens} \times \text{Weighted Wickets}}{\text{Weighted Economy} \times \text{Weighted Strike Rate} \times \text{Weighted Bowling Average}}\).
     - Final: Jasprit Bumrah, Mohammed Siraj, Kuldeep Yadav, Yuzvendra Chahal.
   - **All-Rounders**: Selected via:
     - Round 1: Common players in batting and bowling all-rounders (from 16 batting, 12 bowling).
     - Round 2: All-Rounder Index = \(\text{Batting Index} \times \text{Bowling Index}\).
     - Final: Hardik Pandya, Ravindra Jadeja.

## Key Findings
- **Independence**: Venue, toss outcome, and match outcome are independent, indicating the team’s adaptability (Chi-Square tests).
- **Captaincy**: Rohit Sharma’s win proportion is statistically consistent (Binomial test).
- **Economy Rates**: Spinners and pacers have equal mean economy rates, suggesting balanced bowling performance (T-test).
- **Batting Performance**: 2019 and 2022 batting performances have equal means but different variances, showing consistency but varied reliability (T-test, F-test).
- **Team Selection**: Proposed ideal ODI team includes 5 batters, 4 bowlers, and 2 all-rounders, balancing experience and performance.
- **Poisson Fit**: Catches taken follow a Poisson distribution, aiding fielding analysis.

## Setup Instructions
1. **Prerequisites**:
   - Python 3.8+ or R for statistical analysis.
   - Libraries: `pandas`, `numpy`, `scipy`, `statsmodels` (Python) or `stats` (R).
   - Dataset: Download from [ESPNcricinfo](https://stats.espncricinfo.com/ci/engine/stats/index.html) or use provided CSV (if available).

2. **Installation**:
   ```bash
   pip install pandas numpy scipy statsmodels
   ```

3. **Running the Analysis**:
   - Clone the repository:
     ```bash
     git clone https://github.com/SeanMinezes/Indian-Cricket-Team-ODI-Analysis.git
     cd Indian-Cricket-Team-ODI-Analysis
     ```
   - Run the analysis script (e.g., `analysis.py` or `analysis.R`):
     ```bash
     python analysis.py
     ```
   - View outputs (e.g., test results, Q-Q plots) in the `outputs/` folder.

4. **Data**:
   - Place the ESPNcricinfo dataset in the `data/` folder.
   - Expected format: CSV with columns for runs, wickets, economy, etc.

## Repository Structure
```
├── data/                    # ESPNcricinfo dataset (CSV)
├── scripts/                 # Analysis scripts (Python/R)
│   ├── analysis.py          # Main statistical tests and indices
│   ├── plots.py             # Q-Q plots and visualizations
├── outputs/                 # Test results, plots (e.g., Q-Q plot for catches)
├── images/                  # Presentation images (e.g., image1.png, image2.png)
├── Statistical_Analysis_ICT.pptx  # Project presentation
└── README.md                # This file
```

## Future Scope
- Analyze player impact across T20 and Test formats.
- Compare Indian team stats with other nations (e.g., Australia, England).
- Apply machine learning for predictive team selection and strategy optimization.
- Incorporate fielding statistics and multi-year data for holistic insights.

## Conclusion
This project demonstrates the power of statistical analysis in cricket, revealing the Indian Cricket Team’s consistency, adaptability, and balanced performance in ODIs. The proposed team selection, backed by rigorous indices, offers a data-driven approach to optimize line-ups. These insights set a precedent for sports analytics, applicable to roles like NIQ’s Junior ML Engineer, where data-driven decision-making is key.

## References
- Wikipedia Contributors, “One Day International,” Wikipedia, Oct. 29, 2023. [Link](https://en.wikipedia.org/wiki/One_Day_International)
- “Predicting Optimal Cricket Team Using Data Analysis,” Research Paper.
- ESPNcricinfo Stats. [Link](https://stats.espncricinfo.com/ci/engine/stats/index.html)

## Contributors
- Nidhi Karambelkar (A010)
- Sean Minezes (A015)
- Akshay Mirani (A016)
- Jash Moze (A017)
- Veer Shah (A020)
- Mentor: Prof. Vaibhav Vasundekar

## License
This project is licensed under the MIT License.