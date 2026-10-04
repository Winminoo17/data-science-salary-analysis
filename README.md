Global Data Science Salary & Skill Requirements Analysis
An end-to-end exploratory data analysis (EDA) project focusing on salary structures, geographic discrepancies (Asia vs. United States), data cleaning pipelines, and the most demanded skill ecosystems for Data Science and Machine Learning roles.
Project Structure
• solution.ipynb: The primary Jupyter Notebook containing missing value treatment (MICE), scale subplots, and statistical distributions.
• data.csv: The underlying data science job marketplace dataset (933 corporate observations).
Data Engineering Pipeline & Missing Value Treatment
To ensure robust analytical models without losing data rows, the tracking workflow utilizes a clean missing value treatment pipeline:
1. Outlier Mitigation: Evaluated continuous columns using the Interquartile Range (IQR) method. Switched from structural row deletion to Capping/Winsorization (clipping data at the 95th/99th percentiles) to perfectly preserve all 933 data observations.
2. Feature Synchronization: Cleaned trailing column spaces using .str.strip() to eliminate KeyError exceptions across dynamic slicing masks.
3. MICE Imputation: Leveraged IterativeImputer(estimator=RandomForestRegressor()) to elegantly fill highly skewed features like corporate revenue without distorting the salary vector targets.
Key Insights & Visualizations
1. The Geographic Salary Divide
• The analysis shows a massive macroeconomic divide between the United States and Asia.
• The United States market holds a median salary of approximately $145,000, with an entry floor starting near $100,000.
• Conversely, the continuous box structure for Asia remains tightly compressed near the baseline, hovering around a median of $35,000.
2. Multi-Variable Interaction (Hierarchy Grid)
• Corporate Scale Framework: Remote structures mapped inside Public Corporations systematically yield the highest structural compensation premiums across all seniority tiers, frequently bypassing regional constraints.
• On-Site Limitations: Traditional On-site / Private settings anchor the far left margin, yielding the lowest earning distributions within matching career levels.
3. Top Demanded Skill Ecosystem
The baseline frequency trend maps Python (452), Machine Learning (412), and SQL (312) as the mandatory core stack required by modern global enterprises. Deep Learning applications remain split evenly between the TensorFlow (111) and PyTorch (102) framework engines.
Technologies Used
• Languages: Python
• Libraries: Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn (IterativeImputer)
