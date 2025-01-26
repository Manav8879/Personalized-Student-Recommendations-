##Quiz Data Analysis Project
##Overview
This project is designed to load, analyze, and generate insights from quiz data. The data is divided into two categories: current quiz data and historical quiz data. The main objective is to identify weak areas for users based on their quiz performance and suggest topics for improvement. The project leverages Python and various libraries such as pandas and requests for data processing and analysis.

##Requirements
To run this project, you'll need the following Python libraries:

pandas: For handling and manipulating data.
requests: For making HTTP requests to retrieve the quiz data.

##Project Approach
The project is divided into several key steps:

1. Data Loading
API Data Retrieval: The quiz data is fetched from two API endpoints: one for current quiz data and another for historical quiz data. The data is then converted from JSON to Pandas DataFrames using pd.json_normalize().
2. Data Inspection
After loading the data, a preview of the first few rows is printed to confirm the successful loading of the data.
3. Data Analysis
Current Quiz Data: We analyze the current quiz data to find topics with the lowest average response accuracy, which identifies areas where users are struggling.
Historical Quiz Data: The historical quiz data is analyzed by calculating the average score for each user. This helps identify users who consistently underperform.
4. User-Specific Weak Areas
The code identifies the weak topics for a specific user based on their response accuracy. Weak topics are those with an accuracy lower than 50%.
5. Recommendations
Based on the weak areas identified for a specific user, recommendations are provided. If no weak areas are found (i.e., the user performs well), the code informs the user of this.
6. Data Export
The processed DataFrames are saved as CSV files for further exploration or use.
