# GenAI_Hands_on_Session-11-Business-Problems-with-GenAI-
This repository contains an intermediate hands-on that can be used in Understanding and Structuring Business Problems for Generative AI Solutions

### Hands-On 1: Identifying the Core Issue through Data Analysis

#### Part 1: Analyzing a Company Facing Declining Sales

1. **Data Loading and Exploration:**
   - Load the sales data of the company.
   - Perform exploratory data analysis (EDA) to understand the trends and identify potential issues.

**Code Example:**
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the sales data
sales_data = pd.read_csv("sales_data.csv")

# Display the first few rows of the dataset
print(sales_data.head())

# Perform basic statistics on the dataset
print(sales_data.describe())

# Plot sales trends over time
plt.figure(figsize=(12, 6))
sns.lineplot(data=sales_data, x='Date', y='Sales')
plt.title('Sales Trend Over Time')
plt.xlabel('Date')
plt.ylabel('Sales')
plt.show()
```

2. **Identifying Core Issues:**
   - Use data visualization techniques to identify periods of declining sales.
   - Analyze potential reasons for the decline (seasonality, market changes, etc.).

**Code Example:**
```python
# Identify periods of declining sales
sales_data['Date'] = pd.to_datetime(sales_data['Date'])
sales_data.set_index('Date', inplace=True)
sales_data['Sales_Diff'] = sales_data['Sales'].diff()

# Plot the differences in sales to highlight declines
plt.figure(figsize=(12, 6))
sns.lineplot(data=sales_data, x='Date', y='Sales_Diff')
plt.title('Sales Changes Over Time')
plt.xlabel('Date')
plt.ylabel('Sales Difference')
plt.show()
```

#### Part 2: Stakeholder Analysis for a New Product Launch

1. **Conduct Stakeholder Analysis:**
   - Identify and list stakeholders involved in a new product launch.
   - Map out their interests and impacts.

**Code Example:**
```python
# List of stakeholders
stakeholders = [
    {'Name': 'Product Manager', 'Interest': 'High', 'Impact': 'High'},
    {'Name': 'Marketing Team', 'Interest': 'Medium', 'Impact': 'High'},
    {'Name': 'Sales Team', 'Interest': 'High', 'Impact': 'Medium'},
    {'Name': 'Customers', 'Interest': 'High', 'Impact': 'High'},
    {'Name': 'Suppliers', 'Interest': 'Medium', 'Impact': 'Medium'}
]

# Convert to DataFrame for easy manipulation
stakeholders_df = pd.DataFrame(stakeholders)

# Display the stakeholder analysis
print(stakeholders_df)
```

### Hands-On 2: Setting SMART Objectives

1. **Create SMART Objectives:**
   - Define Specific, Measurable, Achievable, Relevant, and Time-bound objectives for improving customer satisfaction through an AI chatbot.

**Code Example:**
```python
# Define SMART objectives
smart_objectives = {
    'Specific': 'Implement an AI chatbot to handle customer inquiries',
    'Measurable': 'Achieve a customer satisfaction score of 90%',
    'Achievable': 'Develop and deploy the chatbot within 6 months',
    'Relevant': 'Reduce response time and improve customer experience',
    'Time-bound': 'Complete the project by the end of Q4'
}

# Display the SMART objectives
for key, value in smart_objectives.items():
    print(f"{key}: {value}")
```

### Hands-On 3: Applying Problem-Solving Frameworks

#### Part 1: SWOT Analysis for a Health Tech Startup

1. **Conduct a SWOT Analysis:**
   - Apply SWOT Analysis to a health tech startup considering AI solutions.

**Code Example:**
```python
# Define SWOT analysis
swot_analysis = {
    'Strengths': ['Innovative technology', 'Experienced team', 'Strong R&D capabilities'],
    'Weaknesses': ['Limited market reach', 'High operational costs'],
    'Opportunities': ['Growing demand for health tech', 'Expansion into new markets'],
    'Threats': ['Regulatory challenges', 'Competitive market']
}

# Display the SWOT analysis
for category, factors in swot_analysis.items():
    print(f"{category}:")
    for factor in factors:
        print(f" - {factor}")
```

### Hands-On 4: Using ChatGPT for Problem Articulation

1. **Problem Articulation with ChatGPT:**
   - Use ChatGPT to articulate business problems and propose solutions.

**Code Example:**
```python
import openai

# Set up the OpenAI API key
openai.api_key = 'your-api-key-here'

# Define a function to use ChatGPT for problem articulation
def articulate_problem(problem_description):
    response = openai.Completion.create(
        engine="text-davinci-003",
        prompt=f"Articulate the following business problem and propose a potential AI solution: {problem_description}",
        max_tokens=150
    )
    return response.choices[0].text.strip()

# Example problem description
problem_description = "The company is facing declining sales due to increased competition and changing customer preferences."

# Use ChatGPT to articulate the problem and propose a solution
articulated_problem = articulate_problem(problem_description)
print(articulated_problem)
```

### Final Project Submission

**Deliverables:**
1. **Jupyter Notebook:**
   - Containing all code implementations, functions, and outputs for each part of the project.

2. **Project Report:**
   - A comprehensive document summarizing the entire project, including explanations of concepts, the approach taken, the results obtained, and discussions on the limitations and potential improvements.

3. **Presentation:**
   - A presentation highlighting key parts of the project, demonstrating the functionalities implemented, and discussing the insights gained.
