# FutureSecure-Insurance-Pricing-Automation

Project VBA 2: The NewCare Digital Transformation

Project Overview:
This project demonstrates the transition from legacy Excel-based workflows to modern, automated cloud-based pricing engines for an insurance product named "FutureSecure" (10-Year Renewable Term Assurance).

Purpose & Goal:
The objective is to price the FutureSecure product using synthetic mortality datasets and automate the process using Python to minimize manual errors associated with heavy Excel files.

Technical Workflow:
1.Phase A: Legacy Model (Excel)
i)Developed a dynamic Excel workbook where users can toggle between Base and Shocked mortality rates.
ii)Calculated Gross Premiums for ages 30, 40, and 50.
2.Phase B: Modern Workflow (Python & Cloud)
i)Database: Assumptions and mortality tables (qx_base vs qx_shocked) are hosted on Google Sheets.
ii)Engine: A Python script (Google Colab) fetches this data and calculates premiums programmatically.

Assumptions:
1.Interest Rate: 4% p.a..
2.Mortality: Specific synthetic dataset (qx_base & qx_shocked).
3.Expenses: As specified in the actuarial instructions.

Technical Stack:
1.Language: Python (Google Colab)
2.API: Google Sheets API (for data fetching)
3.Libraries: Pandas, Numpy, Gspread (for cloud integration)

How to Run: FutureSecure Digital Pricing System:
1. Setup the Database (Google Sheets & CSV)
i)Assumptions_Database.csv: Ensure this file is uploaded to your Google Drive or hosted on a Google Sheet. It must contain the mortality tables (qx_base and qx_shocked).
ii)Maybank Stock Sheet: If you are using your Maybank historical data as a benchmark for risk-free rates or market trends, ensure the sheet is formatted with clear headers (Date, Price, etc.).
iii)Permission: Set the Google Sheet sharing settings to "Anyone with the link can view" so the Python script can fetch the data.
2. Execute the Python Engine (FutureSecure_Pricing_Engine.ipynb)
i)Open in Google Colab: Upload and open your .ipynb file in Google Colab.
ii)Authentication: Run the first cell to authenticate your Google account (this allows Colab to access your Google Sheets database).
iii)Library Installation: Ensure you have the necessary libraries by running: pip install gspread pandas numpy
iv)Data Fetching: Run the code block that connects to your spreadsheet URL. It will pull the mortality rates and the 4% interest rate assumption.
v)Run Calculations: Execute the pricing logic cells. The script will calculate the Gross Premium for a 10-Year Renewable Term Assurance.
3. Perform the "Switching" Validation
i)Base vs. Shocked: In your Python script (or the "Input" tab of your Excel), toggle the mortality basis from qx_base to qx_shocked.
ii)Observe Changes: Re-run the engine to see how the Gross Premium updates automatically for ages 30, 40, and 50.
iii)Verification: Compare the Python output with your Excel Workbook (.xlsx) results to ensure the models are validated and consistent.
4. Review Results
i)Output Plots: The script should generate visualizations comparing the premium costs across different ages and mortality scenarios.
ii)Actuarial Memo: Once the runs are complete, record the final premiums for your Actuarial Memorandum (PDF) to be submitted to the Chief Actuary.
