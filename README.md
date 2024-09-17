**Card Performance Analysis**

****Project Overview****

The Card Performance Analysis project is designed to analyze and evaluate the performance of various card types based on transaction data. The goal is to categorize cards, analyze transaction trends, and visualize performance metrics.

**Project Objectives**

**Data Aggregation:**  Combine transaction data from multiple CSV files.

**Data Cleaning:** Remove duplicates, handle missing values, and convert data types.

**Card Categorization:** Classify cards based on their BIN (Bank Identification Number).

**Monthly Performance Analysis:** Calculate and analyze monthly transaction trends and response codes.

**Visualization:** Generate plots to visualize performance metrics and response code distributions.


**1. Data Aggregation and Cleaning**
This section of the project focuses on aggregating and cleaning transaction data from multiple CSV files. The goal is to combine all relevant files into a single DataFrame, remove duplicates, and ensure the data is in the correct format for further analysis.

**Explanation**

**Setup and Initialization**

Folder Path: Specifies the directory where the CSV files are stored.
Log File: Keeps track of which files have already been processed to avoid reprocessing.
Log File Handling

Checks if the log file exists. If not, creates an empty log file.
Reads the log file to get a list of previously processed files.

**File Processing**

Iterates over each file in the specified folder.
For each file not in the log, attempts to read it into a DataFrame.
Handles potential CSV parsing errors and skips problematic lines.
Adds non-empty DataFrames to a list and updates the log with the processed file names.

**Data Concatenation**

Concatenates all DataFrames in the list into a single DataFrame.
If a combined DataFrame already exists, it appends the new data to it. Otherwise, it creates a new combined DataFrame.
Displays the first few rows of the combined DataFrame for verification.

**Log Update**

Updates the log file with the names of newly processed files.

**Notes
**
Error Handling: The code includes error handling for file reading issues, ensuring that the process continues even if some files are problematic.
Performance: The use of pd.concat() ensures efficient aggregation of multiple DataFrames.

**Usage**

Place your CSV files in the My Files folder.
Run the script to aggregate and clean the data. The combined data will be stored in combined_df, and the processed files will be logged.

**2. Data Cleaning and Transformation**

This section focuses on cleaning and transforming the aggregated data to prepare it for analysis. Key tasks include removing duplicates, converting date formats, and extracting relevant features. The date format was converted to the proper format to aid the analysis and also with the Month Name extraction.

**3. Card Categorization & Performance Analysis**

This section categorizes cards based on their BIN (Bank Identification Number). The categorization helps in analyzing the performance of different types of cards (e.g., Debit, Prepaid, Credit). The focus is on calculating the distribution of response codes by month and determining the percentage share of each response code. Intially, the analysis was on the whole card portfolio which showed a not so convincing performance. This necessitated the breakdown per card type to show where the issues may be.

**4. Visualization**

**Overview**

This section visualizes the performance of different response codes by card type, focusing on the top 5 response codes for each card type. The visualizations help in understanding the distribution and trends of response codes. We made use of custom colors for the specific codes. Data was filtered for the month of September and data was grouped by Card Type and Response Code determining the percentage of each code. The top 5 response codes were identified and plotted on a bar chart per card type.


![image](https://github.com/user-attachments/assets/fd2a8692-4d26-4e28-9f53-a3dcd4282f92)

![image](https://github.com/user-attachments/assets/33d465cd-57d9-4356-89c2-0be29a7366d6)


**Conclusion**

This project highlights the importance of managing different card types independently due to their distinct performance characteristics and challenges. The analysis revealed that Prepaid, Debit, and Credit cards each exhibit unique patterns in response codes, with varying frequencies of issues such as insufficient funds or transaction approvals. By examining these trends, financial institutions can better understand the performance of each card type and address specific issues effectively.

**Key findings include:**

Prepaid Cards: These often face different challenges compared to Debit Cards, potentially due to their usage patterns or limitations.

Debit Cards: May have specific issues related to approval rates or insufficient funds that differ from those observed with Prepaid and Credit cards.


Understanding these differences allows financial institutions to implement targeted improvements and strategies for each card type. By addressing the unique needs and challenges associated with each type, institutions can enhance overall card performance and customer satisfaction.

