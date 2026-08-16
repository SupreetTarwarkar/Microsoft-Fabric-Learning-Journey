# HR Attrition Analysis using Microsoft Fabric

## Project Overview

The **HR Attrition Analysis** project is an end-to-end HR analytics solution developed using **Microsoft Fabric** and **Power BI** to analyze employee attrition patterns across departments, job roles, salary bands, demographics, business travel, and overtime.

The solution uses **Dataflow Gen2** and **Power Query** for data preparation, a **Fabric Lakehouse** for analytical storage, a **Semantic Model** for reporting logic, and **Power BI** for interactive HR attrition analysis.

---

## Business Problem

Employee attrition can create recruitment costs, knowledge loss, productivity disruption, and workforce planning challenges. HR teams need a centralized analytical view to understand where attrition is concentrated and which employee segments show comparatively higher attrition rates.

This project analyzes workforce data to identify important attrition patterns and support more informed HR investigation and workforce planning.

---

## Project Objectives

- Measure the overall employee attrition rate and number of employees leaving the organization.
- Compare attrition across departments and job roles.
- Evaluate attrition across different salary bands.
- Analyze demographic patterns across age groups, gender, education field, and marital status.
- Examine attrition patterns associated with business travel and overtime.
- Provide interactive filtering for deeper workforce analysis.
- Build an end-to-end HR analytics workflow using Microsoft Fabric and Power BI.

---

## Solution Architecture

```text
GitHub-hosted HR Dataset
        ↓
Dataflow Gen2
        ↓
Power Query Transformation
        ↓
Fabric Lakehouse
     (lh_HR)
        ↓
HR_Employees Table
        ↓
Semantic Model
   (HR Semantic)
        ↓
Power BI Report
(HR Attrition Analysis)
        ↓
Interactive HR Insights
```

**OneLake Security** was also explored for controlling access to the Lakehouse data.

---

## Tech Stack

- **Microsoft Fabric** : End-to-end analytics platform used for data preparation, storage, semantic modeling, security, and reporting.
- **Dataflow Gen2** : Used to ingest and transform the HR employee dataset.
- **Power Query** : Used for data cleaning, type changes, derived columns, and value standardization.
- **Fabric Lakehouse** : Used to store the transformed `HR_Employees` table.
- **OneLake** : Underlying Fabric data storage layer for the Lakehouse.
- **Semantic Model** : Used as the analytical layer between the Lakehouse data and Power BI report.
- **Power BI** : Used to develop the interactive HR Attrition dashboard.
- **DAX** : Used for KPI and attrition-related business calculations.
- **Data Modeling** : Used to organize the analytical structure for reporting.
- **Column-Level Security (CLS)** : Tested through OneLake Security to restrict access to selected data.

---

## Data Source

The project uses an HR employee dataset provided through a GitHub-hosted CSV source.

**Source provided for the project:**

https://raw.githubusercontent.com/the-mansi-goel/FABRIC/refs/heads/main/sales_data.csv

The analysis covers:

- **1,470 employees**
- Employee attrition status
- Age
- Department
- Job Role
- Monthly Income
- Business Travel
- Education Field
- Gender
- Marital Status
- Overtime
- Employee tenure-related information
- Additional HR attributes used for workforce analysis

---

## Data Preparation & Transformation

Data preparation was performed using **Dataflow Gen2 and Power Query** before loading the transformed data into the Fabric Lakehouse.

Key transformation activities included:

- Promoting and standardizing column headers.
- Correcting data types.
- Creating report-ready derived columns.
- Preparing employee segmentation fields used in the dashboard.
- Standardizing categorical values.
- Replacing business travel values with cleaner reporting labels.
- Preparing Age Group and Salary Band categories for analytical reporting.
- Loading the transformed data into the `HR_Employees` Lakehouse table.

One visible example of value standardization was converting:

`Travel_Frequently` → `Frequently`

This made categorical values easier to understand in the final report.

---

## Data Model / Semantic Model

A dedicated semantic model named **`HR Semantic`** was created for the Power BI reporting layer.

The model is centered on the **`HR_Employees`** table and contains the employee attributes required for attrition analysis.

The analytical model supports:

- Employee headcount analysis
- Employees-left calculations
- Attrition rate calculations
- Average income analysis
- Attrition segmentation
- Dashboard filtering
- DAX-based KPI calculations

The semantic model acts as the analytical layer between the Fabric Lakehouse and the Power BI dashboard.

---

## Dashboard Walkthrough

### Home Page

The Home page provides an introduction to the HR Attrition dashboard and separates the analysis into two major areas:

**Overview**

- Department
- Job Role
- Salary Band
- Headcount
- Employees Left

**Deep Dive**

- Age Group
- Gender
- Education Field
- Marital Status
- Business Travel
- Overtime

The page also highlights key questions such as:

- What is the overall attrition rate?
- Which departments are losing the most employees?
- How does attrition vary across pay and age groups?

---

### Overview

The Overview page provides the primary HR attrition KPIs and organizational breakdowns.

#### Main KPIs

- Attrition Rate
- Employees Left
- Total Headcount
- Average Monthly Income
- Average Tenure of Leavers
- Overall Attrition Distribution

#### Analysis

- Attrition Rate by Department
- Attrition Decomposition
- Attrition by Job Role
- Attrition by Salary Band

#### Interactive Filters

- Department
- Gender
- Salary Band
- Clear All Slicers

---

### Deep Dive

The Deep Dive page provides employee-level segmentation analysis across several HR dimensions.

#### Analysis Areas

- Attrition by Age Group
- Attrition by Gender
- Attrition by Education Field
- Attrition by Marital Status
- Attrition by Business Travel
- Attrition by Overtime

The page helps identify employee groups showing comparatively higher or lower attrition rates.

---

## KPIs / Key Metrics

| KPI | Value |
|---|---:|
| Total Headcount | 1,470 |
| Employees Left | 237 |
| Employees Stayed | 1,233 |
| Attrition Rate | 16.1% |
| Average Monthly Income | 6,503 |
| Average Tenure of Leavers | 5.1 |

---

## Key Business Insights

- The organization recorded an overall **16.1% attrition rate**, with **237 employees leaving out of 1,470 employees**.

- **Sales** showed the highest departmental attrition rate at **20.6%**, followed by **Human Resources at 19.0%** and **Research & Development at 13.8%**.

- The **Sales Representative** role showed the highest visible job-role attrition rate at **39.8%**, followed by **Laboratory Technician at 23.9%** and **Human Resources at 23.1%**.

- Employees in the **Under 3K salary band** recorded the highest salary-based attrition rate at **28.6%**, compared with only **8.9%** among employees earning **Above 10K**.

- Employees aged **18–25** showed the highest age-group attrition rate at **35.8%**, while employees aged **36–45** recorded a substantially lower rate of **9.2%**.

- Employees working **overtime** showed an attrition rate of **30.5%**, compared with **10.4%** for employees who did not work overtime.

- Employees who traveled **frequently for business** recorded a **24.9% attrition rate**, compared with **15.0%** for employees who traveled rarely and **8.0%** for non-travel employees.

- **Single employees** recorded a **25.5% attrition rate**, compared with **12.5% for married employees** and **10.1% for divorced employees**.

These findings show associations within the workforce data and highlight employee segments that may warrant further HR investigation; they do not by themselves establish causation.

---

## Security Implementation

**OneLake Security** was practically explored as part of the project.

A **DefaultReader** Lakehouse role was used to test data access, and **Column-Level Security (CLS) constraints** were applied to the `HR_Employees` table.

This demonstrated how access to sensitive HR information can be controlled at the data level within Microsoft Fabric.

---

## Dashboard Screenshots

### Home Page

![Home Page](Screenshots/22b92b72-7a76-40cc-90f4-396062041daa.jpg)

### Overview

![Overview](Screenshots/2.%20Over%20View(1).jpg)

### Deep Dive

![Deep Dive](Screenshots/3.%20Deep%20Drive(1).jpg)

### Column-Level Security

![Column-Level Security](Screenshots/4.%20CLS(1).jpg)

### Microsoft Fabric Workspace

![Microsoft Fabric Workspace](Screenshots/5.%20Workspace_HR(1).jpg)

### Fabric Lakehouse

![Fabric Lakehouse](Screenshots/6.%20Lakehouse_HR(1).jpg)

### Semantic Model

![Semantic Model](Screenshots/7.%20Semantic%20Model(1).jpg)

### Dataflow Gen2

![Dataflow Gen2](Screenshots/8.%20Data%20flow%20gen%202(1).jpg)

---

## Dataset

The project uses the HR employee dataset analyzed across **1,470 employees**.

The dataset contains employee-level information covering areas such as:

- Attrition
- Age
- Department
- Job Role
- Income
- Education
- Gender
- Marital Status
- Business Travel
- Overtime
- Employee tenure

The source dataset was provided through GitHub and is intended to be maintained in the project's **Dataset** folder.

---

## Microsoft Fabric Implementation

The project demonstrates an end-to-end Microsoft Fabric workflow.

### Dataflow Gen2

Dataflow Gen2 was used to connect to the source data and perform Power Query-based transformations.

### Fabric Lakehouse

The transformed employee data was loaded into the **`lh_HR`** Lakehouse.

The primary analytical table is:

`HR_Employees`

### OneLake

The Lakehouse data is stored within the broader Microsoft Fabric OneLake architecture.

### Semantic Model

The **`HR Semantic`** model was created on top of the employee data to support Power BI analysis and DAX calculations.

### OneLake Security

OneLake Security was explored using Lakehouse roles and Column-Level Security constraints to control access to HR data.

### Power BI

The final report, **`HR Attrition Analysis`**, was created in Power BI and organized into:

- Home
- Overview
- Deep Dive

This completed the analytical workflow from source data to business insight.

---

## Power BI Report

The Power BI report file for this project is:

`HR Attrition Analysis.pbix`

The report contains:

- Interactive HR dashboard pages
- Attrition KPIs
- DAX calculations
- Employee segmentation analysis
- Dashboard slicers
- Semantic-model-based reporting
- Interactive visualizations

The project repository contains a dedicated **PowerBI** folder for report-related files.

---

## Project Walkthrough Video

A complete project walkthrough is available at:

https://drive.google.com/file/d/14C08ETxHqKhELwHhBPkMjArpU0i3gC5C/view?usp=sharing

The walkthrough demonstrates the major components of the solution, including:

- Dataflow Gen2
- Power Query transformations
- Fabric Lakehouse
- Semantic Model
- OneLake Security
- Power BI dashboard
- HR attrition analysis

---

## Repository Structure

```text
HR-Attrition/
│
├── Dataset/
├── PowerBI/
├── Screenshots/
├── Video/
└── README-PROJECT
```

---

## Skills Demonstrated

- Microsoft Fabric
- Dataflow Gen2
- Power Query
- Fabric Lakehouse
- OneLake
- Semantic Modeling
- DAX
- Power BI
- Data Modeling
- KPI Development
- HR Analytics
- Data Visualization
- Dashboard Storytelling
- Column-Level Security

---

## Acknowledgements

Special thanks to **Mansi Goel** for creating and sharing the structured Microsoft Fabric learning series, practical demonstrations, and guided project content that supported this learning journey.

---

## Author

**Supreet Tarwarkar**

- GitHub: https://github.com/SupreetTarwarkar
- LinkedIn: https://www.linkedin.com/in/supreettarwarkar/
