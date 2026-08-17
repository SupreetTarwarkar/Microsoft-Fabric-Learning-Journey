# HR Attrition Analysis using Microsoft Fabric

## Project Overview

The **HR Attrition Analysis** project is an end-to-end HR analytics solution developed using **Microsoft Fabric** and **Power BI** to analyze employee attrition across departments, job roles, salary bands, demographics, business travel, and overtime.

The project transforms employee data into an interactive analytical solution that helps identify workforce segments showing comparatively higher attrition patterns.

- Built an end-to-end **HR Attrition Analytics solution** to analyze **1,470 employee records** across department, job role, salary, age, demographics, business travel, and overtime.

- Used **Microsoft Fabric, Dataflow Gen2, Power Query, Fabric Lakehouse, Semantic Model, DAX, Power BI, OneLake, and Column-Level Security** to ingest, transform, model, analyze, visualize, and secure HR data.

- Identified an overall **16.1% attrition rate**, with particularly high attrition among **Sales Representatives (39.8%)**, employees aged **18–25 (35.8%)**, employees working overtime **(30.5%)**, and employees in the **Under 3K salary band (28.6%)**.

---

## Business Problem

Employee attrition can create workforce planning challenges, recruitment costs, productivity disruption, and loss of organizational knowledge.

HR teams need a centralized analytical solution to understand where attrition is concentrated and which employee groups show comparatively higher attrition rates across factors such as department, job role, compensation, age, travel frequency, and overtime.

---

## Project Objectives

- Measure the overall employee attrition rate and number of employees leaving the organization.
- Compare attrition across departments and job roles.
- Evaluate employee attrition across different salary bands.
- Analyze attrition patterns across age groups, gender, education field, and marital status.
- Examine differences in attrition based on business travel and overtime.
- Provide interactive filtering for deeper workforce analysis.
- Build an end-to-end HR analytics workflow using Microsoft Fabric and Power BI.

---

## Solution Architecture

```text
HR Employee Dataset
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
HR Attrition Insights
```

**OneLake Security** was also explored to control access to HR data stored within the Lakehouse.

---

## Tech Stack

- **Microsoft Fabric** : End-to-end analytics platform used to build and manage the HR analytics solution.
- **Dataflow Gen2** : Used for data ingestion and Power Query-based transformation.
- **Power Query** : Used for data cleaning, value standardization, data type management, and derived analytical fields.
- **Fabric Lakehouse** : Used to store the transformed `HR_Employees` table.
- **OneLake** : Used as the underlying Fabric data storage layer.
- **Semantic Model** : Used as the analytical layer between the Lakehouse data and Power BI report.
- **Power BI** : Used to develop the interactive HR Attrition dashboard.
- **DAX** : Used to create attrition-related KPIs and business calculations.
- **Data Modeling** : Used to organize the data for analytical reporting.
- **Column-Level Security (CLS)** : Tested through OneLake Security for controlling access to selected HR data.

---

## Data Source

The project uses an **HR employee attrition dataset** containing **1,470 employee records**.

The dataset includes employee-related information such as:

- Attrition Status
- Age
- Department
- Job Role
- Monthly Income
- Salary-related information
- Gender
- Education Field
- Marital Status
- Business Travel
- Overtime
- Employee Tenure
- Additional workforce attributes

The data was used to analyze both overall workforce attrition and segment-level differences.

---

## Data Preparation & Transformation

Data preparation was performed using **Dataflow Gen2** and **Power Query** before loading the transformed data into the Fabric Lakehouse.

Key transformation activities included:

- Promoting and standardizing column headers.
- Correcting column data types.
- Standardizing categorical values.
- Creating reporting-friendly derived columns.
- Creating employee **Age Groups** for demographic analysis.
- Creating **Salary Bands** for compensation-based attrition analysis.
- Preparing fields required for dashboard segmentation.
- Standardizing Business Travel values for clearer reporting.

For example:

```text
Travel_Frequently
        ↓
Frequently
```

The transformed dataset was then loaded into the **`HR_Employees`** Lakehouse table.

---

## Data Model / Semantic Model

A dedicated Semantic Model named **`HR Semantic`** was created for the reporting layer.

The model uses the **`HR_Employees`** table as the primary analytical table and contains the employee attributes required for workforce analysis.

The model supports:

- Total Headcount
- Employees Left
- Employees Stayed
- Attrition Rate
- Average Monthly Income
- Average Tenure of Leavers
- Department analysis
- Job Role analysis
- Salary Band analysis
- Demographic analysis
- Interactive report filtering

The Semantic Model provides the analytical layer between the **Fabric Lakehouse** and the final **Power BI report**.

---

## Dashboard Walkthrough

### Home Page

The Home page introduces the HR Attrition project and organizes the dashboard into two major analytical sections.

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

The page also highlights major analytical questions such as:

- What is the overall attrition rate?
- Which departments are experiencing higher attrition?
- How does attrition vary across salary and age groups?

### Overview

The Overview page provides the primary workforce KPIs and organizational attrition analysis.

**Main KPIs**

- Attrition Rate
- Employees Left
- Total Headcount
- Average Monthly Income
- Average Tenure of Leavers
- Overall Attrition Distribution

**Analysis Areas**

- Attrition Rate by Department
- Attrition Decomposition
- Attrition by Job Role
- Attrition by Salary Band

**Interactive Filters**

- Department
- Gender
- Salary Band

### Deep Dive

The Deep Dive page provides detailed employee segmentation analysis.

**Analysis Areas**

- Attrition by Age Group
- Attrition by Gender
- Attrition by Education Field
- Attrition by Marital Status
- Attrition by Business Travel
- Attrition by Overtime

This page helps identify workforce groups showing comparatively higher or lower attrition rates.

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

- The organization recorded an overall **16.1% attrition rate**, with **237 employees leaving out of a total workforce of 1,470 employees**.

- **Sales** recorded the highest departmental attrition rate at **20.6%**, followed by **Human Resources at 19.0%** and **Research & Development at 13.8%**.

- **Sales Representatives** showed the highest visible job-role attrition rate at **39.8%**, followed by **Laboratory Technicians at 23.9%** and **Human Resources roles at 23.1%**.

- Employees aged **18–25** recorded the highest age-group attrition rate at **35.8%**, compared with only **9.2%** among employees aged **36–45**.

- Employees in the **Under 3K salary band** recorded a **28.6% attrition rate**, compared with **8.9%** among employees earning **Above 10K**.

- Employees working **overtime** showed a **30.5% attrition rate**, nearly three times the **10.4% rate** among employees who did not work overtime.

- Employees who traveled **frequently for business** recorded a **24.9% attrition rate**, compared with **15.0%** for employees who traveled rarely and **8.0%** among non-travel employees.

- **Single employees** recorded a **25.5% attrition rate**, compared with **12.5% for married employees** and **10.1% for divorced employees**.

These results highlight associations within the workforce data and help identify employee groups that may require further HR investigation. They do not independently establish causation.

---

## Security Implementation

**OneLake Security** was practically explored as part of the project to understand how access to sensitive HR information can be controlled.

A Lakehouse **DefaultReader** role was used during security testing, and **Column-Level Security (CLS)** constraints were applied to the `HR_Employees` table.

This demonstrates how access to selected employee information can be restricted while maintaining access to other analytical data.

---

## Dashboard Screenshots

### Home Page

![Home Page](Screenshots/1.%20Home%20Page.jpg)

### Overview

![Overview](Screenshots/2.%20Over%20View.jpg)

### Deep Dive

![Deep Dive](Screenshots/3.%20Deep%20Dive.jpg)

### Column-Level Security

![Column-Level Security](Screenshots/4.%20CLS.jpg)

### Microsoft Fabric Workspace

![Microsoft Fabric Workspace](Screenshots/5.%20Workspace_HR.jpg)

### Fabric Lakehouse

![Fabric Lakehouse](Screenshots/6.%20Lakehouse_HR.jpg)

### Semantic Model

![Semantic Model](Screenshots/7.%20Semantic%20Model.jpg)

### Dataflow Gen2

![Dataflow Gen2](Screenshots/8.%20Dataflow%20Gen2.jpg)

---

## Dataset

The project uses an HR employee dataset containing **1,470 employee records**.

The dataset supports analysis across:

- Department
- Job Role
- Salary
- Age
- Gender
- Education Field
- Marital Status
- Business Travel
- Overtime
- Employee Attrition
- Employee Tenure

The dataset file is maintained within the project's **Dataset** folder.

---

## Microsoft Fabric Implementation

### Dataflow Gen2

**Dataflow Gen2** was used to connect to the source data and perform Power Query-based data preparation and transformation.

### Fabric Lakehouse

The transformed employee dataset was loaded into the Fabric Lakehouse:

`lh_HR`

The primary analytical table created inside the Lakehouse is:

`HR_Employees`

### OneLake

The Lakehouse participates in the broader **Microsoft Fabric OneLake architecture**, providing centralized analytical storage for the project.

### Semantic Model

The **`HR Semantic`** Semantic Model was created on top of the employee data to support DAX calculations and Power BI reporting.

### OneLake Security

OneLake Security was explored using Lakehouse security roles and Column-Level Security constraints for HR data access.

### Power BI

The final **HR Attrition Analysis** report was developed in Power BI with three report pages:

- Home
- Overview
- Deep Dive

The complete workflow connects data ingestion, transformation, storage, semantic modeling, security, and reporting within Microsoft Fabric.

---

## Power BI Report

The complete Power BI report file is:

`HR Attrition Analysis.pbix`

The report allows users to explore:

- HR Attrition KPIs
- Department-level attrition
- Job Role analysis
- Salary Band analysis
- Employee demographic patterns
- Business Travel patterns
- Overtime patterns
- Interactive slicers
- DAX calculations
- Semantic Model-based reporting

The report file is maintained in the project's **PowerBI** folder.

---

## Project Walkthrough Video

A complete walkthrough of the Microsoft Fabric and Power BI implementation is available at:

https://drive.google.com/file/d/14C08ETxHqKhELwHhBPkMjArpU0i3gC5C/view?usp=sharing

The walkthrough covers:

- Dataflow Gen2
- Power Query transformations
- Fabric Lakehouse
- Semantic Model
- OneLake Security
- Power BI dashboard development
- HR Attrition analysis

---

## Repository Structure

```text
HR-Attrition/
│
├── Dataset/
├── PowerBI/
├── Screenshots/
├── Video/
└── README.md
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
