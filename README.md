# Insights into Lending Risks
> An exploratory data analysis project focused on risk analytics in banking and financial services. This project examines past loan applicant data to identify patterns of default, enabling data-driven decisions for loan approvals and minimizing financial losses.


## Table of Contents
- [Insights into Lending Risks](#insights-into-lending-risks)
  - [Table of Contents](#table-of-contents)
  - [Repo structure](#repo-structure)
  - [General Information](#general-information)
  - [Conclusions](#conclusions)
  - [Technologies Used](#technologies-used)
      - [Linux/macOS](#linuxmacos)
      - [Windows](#windows)
  - [Acknowledgements](#acknowledgements)
  - [Contact](#contact)

## Repo structure
```plaintext
.
├── data
│   └── raw
│       ├── loan.csv                # Primary dataset containing loan details (2007-2011)
│       ├── Data_Dictionary.xlsx    # Data dictionary explaining variable definitions
│       └── mapping.json            # JSON file for mapping categories or attributes
│
├── docs
│   ├── Case_study-Insights_into_Lending_Risks.pdf  # Presentation explaining analysis and results
│   └── Case_study-Insights_into_Lending_Risks.pptx # PowerPoint version of the presentation
│
├── notebook
│   └── eda.ipynb                  # Jupyter Notebook containing all EDA code and visualizations
│
├── .gitignore                     # Files and folders to exclude from Git version control
├── .pre-commit-config.yaml        # Configuration file for pre-commit hooks
├── pyproject.toml                 # Configuration for project dependencies and tools
├── requirements.txt               # Python dependencies required for the project
└── README.md                      # Project description and repository details
```
## General Information
- This project is a demo, where largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. Borrowers can easily access lower interest rate loans through a fast online interface.
- Identify these risky loan applicants, then such loans can be reduced thereby cutting down amount of credit loss.


  *Q1: What is the business problem that your project is trying to solve?* <hr>

  **Ans 1:**
  Project aims to address financial losses incurred by business due to loan defaults (referred to as `charged-off` loans).
  By identifying key indicators and trends associated with risky applicants and implement measures to reduce defaults.

  <hr style="height:2px;border-width:0;color:gray;background-color:gray">

  *Q2: What dataset is being used for this analysis?* <hr>

  **Ans 2:**
  Project uses two primary datasets:
  - loan.csv: Historical loan data from 2007 to 2011, with details about borrowers, loan status, and financial metrics.
  - Data_Directory.xlsx: Explaining meanings and details of variables present in loan dataset.

  <hr style="height:2px;border-width:0;color:gray;background-color:gray">

  *Q3: What is primary objective of this analysis?* <hr>

  **Ans 3:**
  Objective is to conduct exploratory data analysis (EDA) to identify driving factors behind loan defaults.

## Conclusions
  -
    <hr style="height:2px;border-width:0;color:gray;background-color:gray">

    *Q5: What preprocessing steps were performed on dataset?* <hr>

    **A5:**
    - Missing values were handled through imputation or logical removal.
    - Outliers were retained to study their impact on identifying risky borrowers.
    - Log transformation was applied to skewed variables (e.g., annual_inc, total_rec_late_fee) to reduce skewness and improve interpretability.
    - New features were engineered, such as `credit_age`,`credit_history_length`, `time_since_last_payment`, `time_since_last_credit_pull`.

    <hr style="height:2px;border-width:0;color:gray;background-color:gray">

    *Q6: What statistical or visualization techniques were used?*<hr>

    **A6:**
    - Univariate Analysis: To understand distribution of individual variables (e.g., loan_amnt, annual_inc).
    - Bivariate Analysis: Examining relationship between features and loan status (Fully Paid vs. Charged Off) using statistical tests (e.g., t-tests, chi-square) and visualizations.
    - Visualizations: Bar plots, histograms, and boxplots to capture trends and highlight key risk factors.

    <hr style="height:2px;border-width:0;color:gray;background-color:gray">

    *Q7: What were the key findings from analysis?* <hr>

    **A7:**
    - High-risk indicators include
      - `loan_amnt`: 🔺Higher loan amount
      - `int_rate`: 🔺Higher interest rate
      - `annual_inc`: 🔻Lower annual income
      - `dti`: 🔺Higher Debt to income ratio
      - `revol_util`: 🔺Higher revolving line utilization rate
      - `total_rec_late_fee`: 🔺Higher late fee received to date
      - `credit_history_length`: 🔻Less credit history
      - `time_since_last_payment`: 🔺Higher duration since last payment
      - `time_since_last_credit_pull`: 🔻Less duration since last credit pull
      - `term`: 60 months term has higher defaulter %
      - `grade`, `sub_grade`: As grade value is increasing defaulter % increasing
      - `inq_last_6mths`: As inquiry increases defaulter % increasing
      - `open_acc`: Higher open account
    - Verified applicants showed higher default rates, suggesting potential *issues in verification process*.
    - State-specific risks were identified, with some states like Nebraska exhibiting significantly higher default rates.
    - Small business loans had highest percentage of defaults, *indicating a need for enhanced checks for this purpose*.

    <hr style="height:2px;border-width:0;color:gray;background-color:gray">

    *Q8: What challenges did you encounter during analysis?* <hr>

    **A8:**
    - Handling skewed distributions persist post-transformation while preserving data integrity for risk analysis.
    - Balancing between retaining outliers for risk insights and avoiding noise in dataset.
    - Interpreting categorical variables like grade and sub_grade to align with numerical trends.

    <hr style="height:2px;border-width:0;color:gray;background-color:gray">

    *Q9: How do findings impact business decision-making or Recommendations to business?* <hr>

    **A9:**
    Revise credit approval policies for
    - High loan amounts or interest rates or DTI ratio.
    - Higher number of open accounts or inquiries
    - Short credit history
    - Longer-term loans

    Strengthen and Implement stricter checks for Business processes such as loan approval and verification can be enhanced to minimize defaults.
    Furthermore, state-specific and purpose-specific validations can be implemented to address localized risks.

    <hr style="height:2px;border-width:0;color:gray;background-color:gray">

    *Q10: What are next steps for this project?* <hr>

    **A10:**
    - Use predictive modeling techniques (e.g., logistic regression, decision trees) to quantify and prioritize risk factors.
    - Recommend policy changes based on findings, such as stricter approvals for loans with high-risk indicators or targeted improvements in verification process.


## Technologies Used
**Data Analysis:**

* **pandas (2.2.3):** Essential library for data manipulation, analysis, and cleaning.
* **matplotlib (3.9.2):** Versatile library for creating various visualizations.
* **seaborn (0.13.2):** High-level data visualization library built on matplotlib, offering attractive and informative plots.
* **scikit-learn (1.5.2):** Comprehensive library for machine learning tasks like classification, regression, and clustering.
* **statsmodels (0.14.4):** Statistical modeling library for time series analysis, regression, and statistical tests.
* **spacy (3.8.2):** SpaCy modeling library is for natural language processing tasks.

**Development Tools:**

* **black (24.10.0):** Enforces a consistent code formatting style.
* **flake8 (7.1.1):** Static code analysis tool for style violations and potential bugs.
* **isort (5.13.2):** Automatically sorts imports for better readability.
* **pre-commit (4.0.1):** Framework for managing pre-commit hooks to ensure code quality checks before commits.

**Installation:**

* **Recommended:** Create a virtual environment to isolate project dependencies 🐍:

  #### Linux/macOS
    ```bash
    python3 -m venv env
    source env/bin/activate
    pip3 install -r requirements.txt
    ```
  #### Windows
    ```bash
    python -m venv env
    env\Scripts\activate.bat
    pip install -r requirements.txt
    ```


## Acknowledgements
* **Subject matter understanding referral links**
  - What Is a Loan Commitment? Definition, How it Works, and Types [click](https://www.investopedia.com/terms/l/loan-commitment.asp)
  - Principal: Definition in Loans, Bonds, Investments, and Transactions [click](https://www.investopedia.com/terms/p/principal.asp)
  - Loan Grading: What it is and how it Works [click](https://www.investopedia.com/terms/l/loan-grading.asp)
  - What Does a Charge-Off Mean? [click](https://www.investopedia.com/terms/c/chargeoff.asp)
  - What is Debt to Income Ratio and How is it Calculated? [click](https://www.homecredit.co.in/en/paise-ki-paathshala/detail/what-is-debt-to-income-ratio-and-how-is-it-calculated#:~:text=DTI%2C%20or%20Debt%2Dto%2D,lenders%20when%20evaluating%20loan%20applications.)
  - How Can I Use a Line of Credit? [click](https://www.investopedia.com/terms/l/lineofcredit.asp)
  - What Is the Interest Coverage Ratio? [click](https://www.investopedia.com/terms/i/interestcoverageratio.asp)
  - Dot-com bubble [click](https://en.wikipedia.org/wiki/Dot-com_bubble)
  - Market crash 2000 to 2008 [click](https://en.wikipedia.org/wiki/Stock_market_crashes_in_India#:~:text=As%20per%20the%20latter%20definition,January%2C%20May%20and%20June%202008.)
  - US State Abbreviations [click](https://www.bu.edu/brand/guidelines/editorial-style/us-state-abbreviations/)


## Contact
Created by [@amaan2398](https://github.com/amaan2398) 💻 - Let's connect!

You can also find me on LinkedIn: [amaan2398](https://www.linkedin.com/in/amaan2398/) 💼
