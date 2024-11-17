# Airline Data Analysis & Predictive Modeling Project

## Overview
This project, completed as part of the Forage virtual experience, involved two main tasks focused on web scraping, data analysis, and predictive modeling using Python. The primary goal was to derive actionable insights from airline review data and develop a model to predict customer booking behavior.

## Task 1: Web Scraping and Data Analysis

### 1.1 Data Collection
- **Objective**: Scrape review data from Skytrax, specifically focusing on reviews about airlines.
- **Methodology**: Utilized Python and Jupyter Notebook for data scraping.
- **Approach**:
  - Used web scraping libraries (e.g., BeautifulSoup, requests) to collect large amounts of review data.
  - Stored collected data in a structured format within a dedicated "data" folder for easy access.

### 1.2 Data Cleaning and Preparation
- **Challenges**: The raw data was unstructured and required extensive cleaning.
- **Steps**:
  - Removed unwanted characters, HTML tags, and performed text normalization.
  - Tokenized text and removed stopwords for efficient analysis.

### 1.3 Analysis and Insights
- **Techniques**:
  - **Sentiment Analysis**: Used Python libraries like `TextBlob` and `NLTK` to assess the overall sentiment of the reviews.
  - **Topic Modeling**: Implemented `Latent Dirichlet Allocation (LDA)` to identify recurring themes in customer feedback.
  - **Word Clouds**: Created visual representations to highlight frequently mentioned keywords.
- **Presentation**: Summarized key findings and created visualizations, compiling them into a concise PowerPoint slide for presentation.

### Outcome
Provided a comprehensive overview of customer sentiments and identified key topics of interest within the reviews, which could inform strategic decisions for improving customer satisfaction.

## Task 2: Predictive Modeling for Customer Booking

### 2.1 Data Exploration and Preparation
- **Initial Exploration**:
  - Explored the dataset provided in the "Getting Started" Jupyter Notebook to understand columns and basic statistics.
  - Identified key features that might influence customer booking behavior.
- **Feature Engineering**:
  - Created new features and optimized existing ones to enhance model performance.
  - Conducted data normalization and handled missing values to ensure a clean dataset.

### 2.2 Model Training
- **Algorithm Used**: Trained a **Random Forest Classifier** due to its robustness and ability to provide feature importance.
- **Approach**:
  - Split the data into training and test sets.
  - Conducted hyperparameter tuning for improved performance.

### 2.3 Model Evaluation
- **Techniques**:
  - Performed cross-validation to validate the model’s reliability.
  - Evaluated metrics such as **accuracy, precision, recall, and F1 score**.
  - Visualized feature importance to understand the impact of each variable on the model's predictions.

### Outcome
Presented a summary of the model’s performance and key findings in a PowerPoint slide, highlighting the most influential features and model accuracy.

## Tools and Technologies Used
- **Languages**: Python
- **Libraries**: BeautifulSoup, requests, pandas, numpy, scikit-learn, NLTK, TextBlob, matplotlib, seaborn
- **Notebook**: Jupyter
- **Presentation**: PowerPoint

## Key Learnings
- Advanced data scraping and cleaning techniques to handle unstructured data.
- Implementing and interpreting sentiment analysis and topic modeling.
- Building, tuning, and evaluating machine learning models with feature interpretation.

## Conclusion
This project provided hands-on experience in data collection, analysis, and machine learning, offering valuable insights into customer feedback and predictive modeling to support business strategies.

