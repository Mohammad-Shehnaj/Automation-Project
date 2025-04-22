# Insurance Claim Eligibility Check Automation

## Technologies Used

- Python: For rule-based logic and ML classification
- UiPath Studio: For automating user interface workflows and file Input/output
- CSV Files: used for claims, policies and output logs


## Installation

Before running the Python script, install the required packages:

pip install -r requirements.txt


## Config File

json:
{
  "required_documents": ["ID.pdf", "Bill.pdf", "ClaimForm.pdf"]
}


## How to Run the Project

### 1. Run Python Logic
- Open 'Python.ipynb'
- Run all cells
- Make sure it creates 'claim_eligibility_results.csv'

### 2. Run UiPath Workflow
- Open UiPath Studio
- Run 'Automate Insurance Claim Eligibity Check.xaml'
- This will process the result file and generate 'ui_claim_eligibility_results.csv' and 'audit_log.csv'


## How It Works

### Python Logic
1. Loads input data (claims + policies)
2. Applies rule-based eligibility checks:
   - Policy is active
   - Claim amount is valid
   - Required documents are submitted from 'config.json'
3. ML model classifies the claim
4. Saves results to 'claim_eligibility_results.csv'


### UiPath Automation
1. Reads 'claim_eligibility_results.csv'
2. Generates final output in 'ui_claim_eligibility_results.csv'


## Output

- Eligibility Report: Final decision in 'ui_claim_eligibility_results.csv'
- Audit Log: Entry for each processed claim in 'audit_log.csv'
