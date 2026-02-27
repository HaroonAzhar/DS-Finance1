1. Purpose & Overview
    Identify fraudulent credit card transactions on corporate/personal credit cards as part of the annual company audit. This case study considers the scenario where companies auto approve expenses within certain thresholds. 
    Alternatively, this could be a model used to detect whether a transaction is fraudulent as part of the auto-approval process.

    Dataset: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data

2. Goals & Objectives
    a. Detect credit card fraud prior to approving the employee reimbursment 

3. Techniques & Technologies
    TBD - Week 2 - See Guiding Questions

4. Key Findings 
    TBD - Week 2 

5. Setup Instructions
    TBD - Week 2 

6. Visuals
    TBD - Week 2 

7. Guiding Questions
a. Who is the intended audience for your project?
    Corporate Finance & Internal Audit departments

b. What is the question you will answer with your analysis?
    Whether or not a corporate credit card transaction is fraudulent.

c. What are the key variables and attributes in your dataset?
    - V1–V28: anonymized PCA components (numerical). 
    - Time: seconds elapsed since the first transaction in the dataset (two‑day window in Sept 2013).
    - Amount: transaction amount (EUR); useful for cost‑sensitive learning.
    - Class: target; 1 = fraud, 0 = genuine. 
    - Size & imbalance: 284,807 rows; 492 frauds (≈0.172%). 

d. Do you need to clean your data, and if so what is the best strategy?
    - Minimal basic cleaning: dataset is already numeric and reports no missing values. Validate dtypes, duplicates, and outliers. 
    - Scale Amount (e.g., StandardScaler/RobustScaler) to align with PCA‑scaled features; optionally log‑scale for skew.
    - Class imbalance handling: use class weights, threshold tuning, under/oversampling (e.g., SMOTE/undersample) on the train set only; evaluate with AUPRC (recommended by dataset authors). 
    - Data leakage checks: split by time (train on earlier Time, test on later) to mimic production streaming.

e. How can you explore the relationships between different variables?
    - Univariate: histograms/KDE for Amount, Time; compare fraud vs. non‑fraud.
    - Correlation: heatmap for all features; note that PCA makes V1–V28 approximately orthogonal, so correlations should be near zero (useful sanity check).
   -  Bivariate: scatter/hexbin of (Amount,Time) colored by Class; box/violin plots of Amount by Class.

f. What types of patterns or trends are in your data?
    This will be determined as part of the final project

g. Are there any specific libraries or frameworks that are well-suited to your project requirements?
    - Data & viz: pandas, numpy, matplotlib, seaborn, plotly (interactive).
    - Modeling: scikit‑learn (logistic regression)
    - Imbalance: imbalanced-learn (SMOTE, under/over‑sampling, pipelines).
    - Interpretability: shap (feature attributions).
    - Model selection: sklearn’s StratifiedKFold, time‑based splits.

i. How can you tailor the visualizations to effectively communicate with your audience?
    1. Match complexity to audience expertise. In this case we will be presenting to executives as such, high‑level summaries, KPIs, trends, simple visuals would be most appropriate. 
    2. Fccus on what's important to the audience i.e. what decision will this visual help them make
    3. 
j. What type of visualization best suits your data and objectives (e.g., bar chart, scatter plot, heatmap)?

k. How can you iterate on your design to address feedback and make improvements?
    1. Start with a rough draft
    2. test multiple times
    3. test for clarity of content and easy of understanding multiple times/with a test audience
    4. ask questions early and solicit feedback

l. What best practices can you follow to promote inclusivity and diversity in our visualization design?
    1. Colorblind friendly palettes e.g. Virdis
    2. Provide descriptive alt text.
    3. Use neutral, respectful labels
    4. Avoid grouping categories that reinforce bias
    5. Provide multiple modes of interpretation (i.e. patterns, textures, readable in grayscale)
    6. Ensure legibility (i.e. font size, style)

m. How can you ensure that your visualization accurately represents the underlying data without misleading or misinterpreting information?
    i.   Select the visual appropriate for the specific data structure. Best practices are      
         described here: https://www.atlassian.com/data/charts
    ii.  Use appropriate scaling (i.e. liner v. log, equal intervals)
    iii. Start axes at 0 (where applicable)
    iv.  Show full context (i.e. don't cherry pick ranges or categories)
    v.   Label clearly and completely

n. Are there any privacy concerns or sensitive information that need to be addressed in your visualization?
    Given the objective of the model is to identify corporate credit card fraud, employee data would not qualify as Personal Information, therefore there are no privacy concerns.
    It is unlikely there is sensitive data in the above scenario, except for if there are occurences of fraud. Corporate credit cards should only be used for authorized work expenses. However, depending on the employee and the company, for example a CEO at a crown corporation, any data on spending habits, could be potentially sensitive if leaked to the public and cause reputational damage. 
    As such, employee names will not be included in visuals, and specific job titles (especially senior or executive leadership) maybe summarized/categorized at a higher level for larger audiences.



Authors: 
Raghavendra Uppilisrinivasan, Purushottam Kumar, Haroon Azhar Khan, Baruni Prabaharan

