# BCG-GENAI-JoB-Simulation-TASK-1

📈 Financial Data Analysis: Tech Giants (2022-2024)
This project analyzes and compares the key financial performance metrics (Revenue, Net Income, and Operating Cash Flow) of three major tech companies—Microsoft, Tesla, and Apple—for the fiscal years 2022 through 2024.

The analysis is performed using Python with the pandas library for data manipulation and matplotlib for visualization.

🎯 Project Goal
To understand and visualize the financial trends and growth of Microsoft, Tesla, and Apple over a three-year period (2022-2024) and provide a concise summary of their financial health and momentum.

📁 Repository Structure
The project assumes the following structure:

financial-analysis-project/
├── three_companies_financials.xlsx  # Financial data source file
├── financial_analysis.ipynb          # Jupyter Notebook with the analysis
└── README.md                       # This file
⚙️ Prerequisites
Before running the analysis, you need to have Python and the following libraries installed:

pandas

matplotlib

openpyxl (Required by pandas to read .xlsx files)

You can install them using pip:

Bash
pip install pandas matplotlib openpyxl jupyter


🚀 Steps to Replicate the Analysis
Follow these steps to set up and run the financial analysis:

Step 1: Data Preparation
Download the Data: Ensure your financial data is saved in an Excel file named three_companies_financials.xlsx.

Load the Data: Use the pandas library to load the data into a DataFrame.

Python
import pandas as pd
# Assuming the file is in the same directory or adjust the path
file_path = 'three_companies_financials.xlsx'
df = pd.read_excel(file_path)
# Display the first few rows (as seen in your screenshot)
# print(df.head())

Step 2: Calculate Financial Growth Metrics
Calculate the year-over-year percentage growth for key financial metrics grouped by company.
Growth(%)=( Current Year Value−Previous Year Value / Previous Year Value )×100

Python

# Calculate Y-o-Y growth metrics using groupby and pct_change

df['Revenue Growth (%)'] = df.groupby(['Company'])['Total Revenue'].pct_change() * 100

df['Net Income Growth (%)'] = df.groupby(['Company'])['Net Income'].pct_change() * 100

df['Assets Growth (%)'] = df.groupby(['Company'])['Total Assets'].pct_change() * 100

df['Liabilities Growth (%)'] = df.groupby(['Company'])['Total Liabilities'].pct_change() * 100

df['Operating Cash Flow Growth (%)'] = df.groupby(['Company'])['Cash Flow from Operating Activities'].pct_change() * 100

Step 3: Visualize Financial Trends
Generate line plots to visualize the trends of Total Revenue, Net Income, and Operating Cash Flow from 2022 to 2024.

a. Total Revenue Trend Plot

Python
import matplotlib.pyplot as plt

df = df.sort_values(by=['Company', 'Year'])

plt.figure(figsize=(10,6))

for company in df['Company'].unique():
    company_data = df[df['Company'] == company]
    plt.plot(company_data['Year'], company_data['Total Revenue'], marker='o', label=company)

plt.title("Total Revenue Trend (2022–2024)")

plt.xlabel("Year")

plt.ylabel("Total Revenue (in millions USD)")

plt.legend()

plt.grid(True)

plt.show()

<img width="876" height="547" alt="output_10_1" src="https://github.com/user-attachments/assets/59a5431f-33b6-43c5-9715-c707c8f958ca" />

b. Net Income Trend Plot

plt.figure(figsize=(10,6))
for company in df['Company'].unique():
    company_data = df[df['Company'] == company]
    plt.plot(company_data['Year'], company_data['Net Income'], marker='o', label=company)

plt.title("Net Income Trend (2022–2024)")
plt.xlabel("Year")
plt.ylabel("Net Income (in millions USD)")
plt.legend()
plt.grid(True)
plt.show()


<img width="876" height="547" alt="output_11_0" src="https://github.com/user-attachments/assets/cf74e010-3eb3-4f8b-ad24-3dc6e318f454" />


c. Operating Cash Flow Trend Plot

plt.figure(figsize=(10,6))
for company in df['Company'].unique():
    company_data = df[df['Company'] == company]
    plt.plot(company_data['Year'], company_data['Cash Flow from Operating Activities'], marker='o', label=company)

plt.title("Operating Cash Flow Trend (2022–2024)")
plt.xlabel("Year")
plt.ylabel("Cash Flow (in millions USD)")
plt.legend()
plt.grid(True)
plt.show()


<img width="876" height="547" alt="output_12_0" src="https://github.com/user-attachments/assets/14ffa350-cb77-4cb2-9964-2db83b7c6b01" />

Step 4: Summarize Findings

Summary of Financial Trends (2022–2024)
Microsoft shows consistent revenue growth with strong net income expansion in 2024, driven by cloud and AI segments.

Tesla's revenue grew steadily, but its net income dropped in 2024, reflecting margin compression and higher production costs.

Apple's revenue fluctuated slightly, but its net income remained stable — indicating strong pricing power and efficient operations.

Overall, Microsoft shows the healthiest financial momentum, while Tesla displays high growth but greater volatility.

🤝 Contributing
Feel free to suggest improvements or expand the analysis to include more metrics or companies.

Fork the repository.

Create a new branch (git checkout -b feature/AmazingFeature).

Commit your changes (git commit -m 'Add some AmazingFeature').

Push to the branch (git push origin feature/AmazingFeature).

Open a Pull Request.
