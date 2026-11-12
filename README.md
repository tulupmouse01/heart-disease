# Heart Failure Clinical Records: Statistical Analysis

## Project Overview
This project analyzes clinical records from 299 patients with heart failure to examine patient survival outcomes and the relationship between mortality and common comorbidities. Using Python, the project calculates mortality percentages, identifies the prevalence of comorbidities among deceased patients, and presents the findings through data visualizations.

## Research Question
Among the 299 patients with heart failure in the dataset:
- What percentage of patients died?
- What percentage of patients who died had at least one of the following comorbidities: smoking, diabetes, anemia, or high blood pressure?

## Dataset
The project uses the **Heart Failure Clinical Records Dataset**, which contains clinical information for 299 patients.

The analysis focuses on the following variables:
- **Death Event:** Indicates whether a patient died during the follow-up period.
- **Anemia:** Indicates whether a patient had anemia.
- **Diabetes:** Indicates whether a patient had diabetes.
- **High Blood Pressure:** Indicates whether a patient had high blood pressure.
- **Smoking:** Indicates whether a patient was a smoker.

## Methods and Analysis
The program uses Python to read and analyze the dataset.

1. **Data Processing:** The CSV module reads the dataset and iterates through each patient's clinical record.
2. **Mortality Calculation:** Counts the total number of patients and the number of deceased patients to calculate the overall mortality percentage.
3. **Comorbidity Analysis:** Among deceased patients, the program counts the presence of anemia, diabetes, high blood pressure, and smoking.
4. **Comorbidity Classification:** Deceased patients are grouped according to the number of identified comorbidities (zero, one, two, three, or four).
5. **Percentage Calculation:** Calculates the percentage of deceased patients who had at least one of the four selected comorbidities.

## Data Visualizations
The project generates three visualizations using Matplotlib and Pandas:

- **Patient Survival vs. Death:** A pie chart showing the percentage of patients who survived compared with those who died.
- **Patient Death with Comorbidities vs. Without Comorbidities:** A pie chart comparing deceased patients with at least one identified comorbidity against those without any of the four selected comorbidities.
- **Number of Comorbidities Among Deceased Patients:** A bar graph showing the distribution of deceased patients according to the number of identified comorbidities.

## Technologies Used
- **Python:** Primary programming language.
- **Pandas:** Organizes and processes data for visualization.
- **Matplotlib:** Creates pie charts and bar graphs.
- **CSV:** Reads and accesses clinical records from the dataset.

## How to Run
1. Download the Heart Failure Clinical Records Dataset.
2. Install the required Python libraries:
   ```bash
   pip install pandas matplotlib
   ```
3. Update the CSV file path in the Python script to match the location of the downloaded dataset.
4. Run the Python script.
5. View the calculated percentages and generated visualizations.

## Project Purpose
The purpose of this project is to apply programming and statistical analysis to a real-world clinical dataset. By examining mortality and the prevalence of selected comorbidities among deceased patients, this project demonstrates how programming can be used to organize, analyze, and visualize healthcare data.

**Note:** This project examines associations within the dataset and does not establish that any individual comorbidity caused a patient's death.
