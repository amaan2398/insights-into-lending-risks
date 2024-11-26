# Insights into Lending Risks
> An exploratory data analysis project focused on risk analytics in banking and financial services. This project examines past loan applicant data to identify patterns of default, enabling data-driven decisions for loan approvals and minimizing financial losses.


## Table of Contents
- [Insights into Lending Risks](#insights-into-lending-risks)
  - [Table of Contents](#table-of-contents)
  - [General Information](#general-information)
  - [Conclusions](#conclusions)
  - [Technologies Used](#technologies-used)
  - [Acknowledgements](#acknowledgements)
  - [Contact](#contact)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
- This project is a demo, where the largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. Borrowers can easily access lower interest rate loans through a fast online interface.
- Identify these risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss.
*Q1: What is the background of your project?*

**A1:**
The project, titled "Insights into Lending Risks," focuses on risky applicant in banking and financial services. It involves analyzing historical loan data from the largest online loan marketplace, which facilitates personal and business loans, to identify patterns that can indicate default risk. The ultimate goal is to optimize loan approval decisions, minimize financial losses due to defaulters, and improve overall business outcomes.

*Q2: What is the business problem that your project is trying to solve?*

**A2:**
The project aims to address the financial losses incurred by the business due to loan defaults (referred to as "charged-off" loans). By identifying key indicators and trends associated with risky applicants, the business can refine its loan approval policies, improve credit risk assessment, and implement measures to reduce defaults.

*Q3: What dataset is being used for this analysis?*

**A3:**
The project uses two primary datasets:
- loan.csv: This contains historical loan data from 2007 to 2011, with details about borrowers, loan status, and financial metrics.
- Data_Directory.xlsx: This serves as a data dictionary, explaining the meanings and details of the variables present in the loan dataset.


*Q4: What is the primary objective of the analysis?*

**A4:**
The objective is to conduct exploratory data analysis (EDA) to identify the driving factors behind loan defaults. This includes understanding correlations, patterns, and trends in the data to assess portfolio risk, improve credit policies, and enhance decision-making during loan approvals.



<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions

*Q5: What preprocessing steps were performed on the dataset?*

**A5:**
- Missing values were handled through imputation or logical removal.
- Outliers were retained to study their impact on identifying risky borrowers.
- Log transformation was applied to skewed variables (e.g., annual_inc, total_rec_late_fee) to reduce skewness and improve interpretability.
- New features were engineered, such as `credit_history_length`, `time_since_last_payment`, and log-transformed variables like `log_annual_inc` etc.

*Q6: What statistical or visualization techniques were used?*

**A6:**
- Univariate Analysis: To understand the distribution of individual variables (e.g., loan_amnt, annual_inc).
- Bivariate Analysis: Examining the relationship between features and loan status (Fully Paid vs. Charged Off) using statistical tests (e.g., t-tests, chi-square) and visualizations.
- Visualizations: Bar plots, histograms, and boxplots to capture trends and highlight key risk factors.

*Q7: What were the key findings from the analysis?*

**A7:**
- High-risk indicators include
  - `loan_amnt`: 🟢Higher loan amount can lead to potential risky applicant
  - `int_rate`: 🟢Higher interest rate can lead to potential risky applicant
  - `annual_inc`: 🔻Lower annual income can lead to potential risky applicant
  - `dti`: 🟢Higher Debt to income ratio can lead to potential risky applicant
  - `revol_util`: 🟢Higher revolving line utilization rate can lead to potential risky applicant
  - `total_rec_late_fee`: 🟢Higher late fee received to date can lead to potential risky applicant
  - `credit_history_length`: 🔻Less credit history lead to potential risky applicant
  - `time_since_last_payment`: 🟢Higher duration since last payment lead to potential risky applicant
  - `time_since_last_credit_pull`: 🔻Less duration since last credit pull lead to potential risky applicant
  - `term`: 60 months term has higher defaulter % which can lead to potential risky applicant
  - `grade`, `sub_grade`: As grede value is increasing defaulter % incresing which can lead to potential risky applicant
  - `inq_last_6mths`: As inquery increases defaulter % incresing which can lead to potential risky applicant
  - `open_acc`: Higher open account lead to potential risky applicant
- Verified applicants showed higher default rates, suggesting potential *issues in the verification process*.
- State-specific risks were identified, with some states like Nebraska exhibiting significantly higher default rates.
- Small business loans had the highest percentage of defaults, *indicating a need for enhanced checks for this purpose*.

*Q8: What challenges did you encounter during the analysis?*

**A8:**
- Handling skewed distributions while preserving data integrity for risk analysis.
- Balancing between retaining outliers for risk insights and avoiding noise in the dataset.
- Interpreting categorical variables like grade and sub_grade to align with numerical trends.

*Q9: How do the findings impact business decision-making?*

**A9:**
The insights will help refine credit policies by identifying and flagging high-risk borrowers. Business processes such as loan approval and verification can be enhanced to minimize defaults. Furthermore, state-specific and purpose-specific validations can be implemented to address localized risks.

*Q10: What are the next steps for this project?*

**A10:**
- Use predictive modeling techniques (e.g., logistic regression, decision trees) to quantify and prioritize risk factors.
- Recommend policy changes based on findings, such as stricter approvals for loans with high-risk indicators or targeted improvements in the verification process.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


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

    ```bash
    python3 -m venv env
    source env/bin/activate  # Linux/macOS
    env\Scripts\activate.bat  # Windows
    pip install -r requirements.txt # Install Dependencies
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


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
