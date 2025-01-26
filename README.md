# Quiz Data Analysis Project

## Overview

This project is designed to load, analyze, and generate insights from quiz data. The data is divided into two categories: **current quiz data** and **historical quiz data**. The main objective is to identify weak areas for users based on their quiz performance and suggest topics for improvement. The project leverages Python and various libraries such as `pandas` and `requests` for data processing and analysis.

## Requirements

To run this project, you'll need the following Python libraries:

- `pandas`: For handling and manipulating data.
- `requests`: For making HTTP requests to retrieve the quiz data.

  ## Project Approach

The project follows a step-by-step process to load, analyze, and generate insights from quiz data. Below is a detailed breakdown of each step:

### 1. Data Loading
- **API Data Retrieval**: The quiz data is fetched from two API endpoints:
  - **Current Quiz Data**: This data includes user performance in quizzes, focusing on the accuracy of their responses to each topic.
  - **Historical Quiz Data**: This data provides past scores for users, helping to assess their overall performance.

  The data is retrieved using the `requests` library, and upon successful retrieval, it is converted from JSON to Pandas DataFrames using `pd.json_normalize()`.

### 2. Data Inspection
- After loading the data, the script inspects the content of both datasets (`current_df` and `historical_df`) by displaying the first few rows using `head()`. This helps in verifying the structure of the data and ensures that the necessary columns (`user_id`, `topic`, `response_accuracy`, and `score`) are present.

### 3. Data Analysis
- **Current Quiz Data**: 
  - The average accuracy per topic is calculated using `groupby()` and `mean()` on the `response_accuracy` column. This allows us to identify which topics users are struggling with the most.
  - We focus on topics with lower accuracy, as these represent areas where improvement is needed.
  
- **Historical Quiz Data**:
  - The average score for each user is calculated using `groupby()` and `mean()` on the `score` column. This helps identify users with consistently lower performance.

### 4. User-Specific Weak Areas
- The code identifies weak topics for a specific user based on their performance (response accuracy). A weak topic is defined as one where the user’s accuracy is below 50%.
- For each user, we group the data by `topic` and calculate the average response accuracy. If a user’s average response accuracy for a topic is below the threshold, it is considered a weak area.

### 5. Recommendations
- Based on the weak areas identified for a specific user, the system generates recommendations for improvement. These recommendations consist of the topics where the user has struggled the most.
- If no weak areas are found (i.e., the user has a high accuracy), the system will inform the user that there are no significant weak topics.
  
### 6. Data Export
- The processed data is saved as CSV files (`current_quiz_data.csv` and `historical_quiz_data.csv`) for further analysis or exploration. This allows the user to download and investigate the data independently.

### Example Steps:
1. **Load the data** from external APIs.
2. **Analyze** the data to find weak topics based on accuracy scores.
3. **Generate recommendations** for users to improve on specific topics.
4. **Save the processed data** into CSV files for further exploration.
  
By following this approach, the project ensures that we can identify the areas where users need to improve and suggest the necessary steps for better performance in future quizzes.


