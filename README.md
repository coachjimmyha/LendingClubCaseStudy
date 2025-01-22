# LendingClubCaseStudy
Using EDA to solve business problems of a Lending Club 

## General Information
### Business problems:
When the company receives a loan application,    the company has to make a decision for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:
  -If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
  -If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company
When a person applies for a loan, there are two types of decisions that could be taken by the company:
- Loan accepted: If the company approves the loan, there are 3 possible scenarios described below:
  - Fully paid: Applicant has fully paid the loan (the principal and the interest rate)
  - Current: Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.
  - Charged-off: Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has defaulted on the loan 
- Loan rejected: The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)

### Business Objectives:
The company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment. 
### Dataset overview:
The dataset contains the complete loan data for all loans issued through the time period 2007 t0 2011, with 39717 rows and 111 columns
- 54 Empty Columns
- 9 columns with only 1 unique value across rows 
- 14 unnecessary fields
- 4 fields with value 0 in most rows and some outliers
- 2 fields with more than 90% null values
## Inferences:
### Inferences - Categorical univariate analysis
- 'Term' attribute: more people loan for 36 months (73.3%) than those for 60 months (26.7%)
- 'grade' attribute: most borrowers are at high grades (B: 30.3%, A: 25.4% and C: 20.4%)
- 'home_ownership'attribute: most people do not own a house. They are renting or their houses are under mortgage.
- 'verification_status' attribute: 42.6% of them are not verified
- 'loan_status' attribute: most of the borrowers (82.96) could pay their loan.
- 'purpose' atttribute: most people (46.7%) borrowed to pay other debts
- 'addr_state' atttribute: most people live in California (17.87%), Newyork (9.6%) and Florida (7.22%)
### Inferences - Categorical Bivariate analysis:
- Term: the longer the loan is, the more possibility of default. Specifically, the default rate of 60 months is 22.60%, and of 36 months is 11.09%
- grade: borrowers graded from D(21.07%) to G (31.96%) have higher probability of defaulting
- home_ownership: home ownership doesn't seem to influence much on the rate of default (13.18-15.02%)
- verification_status: unverified borrowers have less probability of defaulting ==> THIS IS SO STRANGE. WE MUST INVESTIGATE THE PROCESS OF VERIFYING
- purpose: borrowers running small businesses have the highest probability of default
- addr_state: borrowers from NE-Nebraska have the highest probability of default
- emp_length: emp_length does not influence much on the default rate.
- inq_last_6mths: the more inquiries the higher probability of default it is (top 3: 6, 7 and 8)
### Inferences on datetime variables:
- Total loan amount increases by year, highest in 2011
- Loan amount is higher in the second half of the year than the other
### Inferences about quantitative bivariate analysis:
- 'loan_amnt', 'funded_amnt','funded_amnt_inv' in the range of (3500, 11000) have the highest number of defaulters
- 'int_rate' in the range of (9.7, 16.1) has the highest number of defaulters. 
- 'installment' in the range of (117, 320) has the highest number of defaulters 
- 'annual_inc' in the range of (21626, 74504) has the highest number of defaulters. The higher 'annual_inc' the fewer defaulters
- 'dti' in the range of (11.246, 22.492) has the highest number of defaulters
- 'revol_util': the higher 'revol_util', the more defaulters 
- 'open_acc': the number of open accounts in the range of (6, 10) has the highest number of defaulters
### Inferences for segmented analysis: 
- 'loan_amnt' vs. 'term': borrowers in term of greater than 60 months have higher loan amount than the other
- 'loan_amnt' vs. 'grade': borrowers from grades E, F, G seem to have higher loans than the others
- 'int_rate' vs. 'grade': borrowers in grade D/E/F/G are subject to a high interest rate
- 'revol_util' vs. 'grade': borrowers in grade A use the lowest amount of credit relative to all available revolving credit.
- 'loan_amnt' vs. 'verification_status': verified borrowers have higher loan amounts than others
- 'revol_util' vs. purpose: borrwers for credit cards have the highest amount of credit relative to all available revolving credit.
## Contact:
Perform by Jimmy Ha (https://github.com/coachjimmyha) and Mrunmai Khedekar
