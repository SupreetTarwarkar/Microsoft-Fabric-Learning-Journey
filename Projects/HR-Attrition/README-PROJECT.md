# HR Attrition Analysis using Microsoft Fabric

## Project Overview

The **HR Attrition Analysis** project is an end-to-end HR analytics solution developed using **Microsoft Fabric** and **Power BI** to analyze employee attrition across departments, job roles, salary bands, demographics, business travel, and overtime.

The solution processes **1,470 employee records** and transforms workforce data into an interactive analytical dashboard that helps identify employee segments showing comparatively higher attrition patterns.

---

## Business Problem

Employee attrition can create workforce planning challenges, recruitment costs, productivity disruption, and loss of organizational knowledge.

HR teams need a centralized analytical solution to understand where attrition is concentrated and identify workforce segments that may require further investigation across factors such as department, job role, compensation, age, business travel, and overtime.

---

## Project Objectives

- Measure the overall employee attrition rate and number of employees leaving the organization.
- Compare attrition across departments and job roles.
- Evaluate attrition across different salary bands.
- Analyze attrition patterns across age groups, gender, education field, and marital status.
- Examine differences in attrition based on business travel and overtime.
- Provide interactive filtering for deeper workforce analysis.
- Build an end-to-end HR analytics solution using Microsoft Fabric and Power BI.

---

## Solution Architecture

```text
 HR_Attrition.csv
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

---

## Tech Stack

| Technology | Usage in Project |
|---|---|
| **Microsoft Fabric** | End-to-end analytics platform for the project |
| **Dataflow Gen2** | Data ingestion and transformation |
| **Power Query** | Data cleaning, standardization, and derived columns |
| **Fabric Lakehouse** | Storage of transformed HR employee data |
| **OneLake** | Centralized Fabric data storage layer |
| **Semantic Model** | Analytical layer for reporting and DAX measures |
| **Power BI** | Interactive dashboard development and visualization |
| **DAX** | KPI and attrition measure development |

---

### Data Source & Dataset

| Dataset Detail | Description |
|---|---|
| **Dataset Type** | HR Employee Attrition Dataset |
| **Total Records** | 1,470 Employees |
| **Dataset File** | [View HR Employee Attrition Dataset](Dataset/HR-Employee-Attrition.csv) |
| **Fabric Table** | `HR_Employees` |
| **Lakehouse** | `lh_HR` |
| **Primary Target** | Employee attrition analysis |

The dataset contains employee-level information covering:

- Attrition Status
- Age
- Department
- Job Role
- Monthly Income
- Gender
- Education Field
- Marital Status
- Business Travel
- Overtime
- Employee Tenure
- Additional workforce attributes

---

## Data Preparation & Transformation

Data preparation was performed using **Dataflow Gen2** and **Power Query** before loading the transformed dataset into the Fabric Lakehouse.

| Transformation Area | Implementation |
|---|---|
| **Headers** | Promoted and standardized column headers |
| **Data Types** | Corrected column data types |
| **Age Segmentation** | Created Age Group categories for demographic analysis |
| **Income Segmentation** | Created Salary Band categories |
| **Categorical Values** | Standardized values for reporting |
| **Business Travel** | Converted technical values into cleaner business labels |
| **Reporting Fields** | Prepared reporting fields for dashboard analysis and segmentation |
| **Destination** | Loaded transformed data into `HR_Employees` |

Example of value standardization:

```text
Travel_Frequently
        ↓
Frequently
```

---

## Microsoft Fabric Implementation

### Dataflow Gen2

**Dataflow Gen2** was used to connect to the source data and perform Power Query-based data preparation and transformation.

![Dataflow Gen2](Screenshots/8.%20Data%20flow%20gen%202.jpg)

### Fabric Lakehouse

The transformed employee dataset was loaded into the Fabric Lakehouse:

`lh_HR`

The main analytical table created inside the Lakehouse is:

`HR_Employees`

![Fabric Lakehouse](Screenshots/6.%20Lakehouse_HR.jpg)

### Semantic Model

A dedicated Semantic Model named **`HR Semantic`** was created on top of the employee data.

The model supports:

- Total Headcount
- Employees Left
- Employees Stayed
- Attrition Rate
- Average Monthly Income
- Average Tenure of Leavers
- Department Analysis
- Job Role Analysis
- Salary Band Analysis
- Demographic Analysis
- Interactive Report Filtering

![Semantic Model](Screenshots/7.%20Semantic%20Model.jpg)

### OneLake

The Lakehouse uses **OneLake** as the centralized Fabric storage layer, allowing the transformed HR data to remain within the Microsoft Fabric analytics environment.

### Security / Column-Level Security

**OneLake Security** was practically explored to understand how access to sensitive HR information can be controlled.

A **DefaultReader** Lakehouse role was used during testing, and **Column-Level Security (CLS)** constraints were applied to the `HR_Employees` table.

![Column-Level Security](Screenshots/4.%20CLS.jpg)

---

## KPIs / Key Metrics

| KPI | Value |
|---|---:|
| **Total Headcount** | 1,470 |
| **Employees Left** | 237 |
| **Employees Stayed** | 1,233 |
| **Attrition Rate** | 16.1% |
| **Average Monthly Income** | 6,503 |
| **Average Tenure of Leavers** | 5.1 |

---

## Key Business Insights

- **Department & Job Role:** Sales recorded the highest departmental attrition rate at **20.6%**, followed by Human Resources at **19.0%** and Research & Development at **13.8%**. At the job-role level, **Sales Representatives showed the highest visible attrition rate at 39.8%**.

- **Age, Salary & Demographics:** Employees aged **18–25 recorded the highest age-group attrition at 35.8%**, compared with **9.2%** among employees aged 36–45. Employees in the **Under 3K salary band recorded 28.6% attrition**, versus only **8.9%** for employees earning Above 10K. Male employees recorded a 17.0% attrition rate compared with 14.8% for female employees.

- **Work & Employee Patterns:** Employees working **overtime showed 30.5% attrition**, compared with **10.4%** among employees not working overtime. Frequent business travelers recorded **24.9% attrition** versus **8.0%** among non-travel employees, while single employees recorded **25.5% attrition** compared with **12.5%** for married and **10.1%** for divorced employees.

---

## Dashboard Walkthrough, Screenshots & Report

### Power BI Report

The complete Power BI report file is available in the **PowerBI** folder.

[Download Power BI Report](PowerBI/HR%20Attrition%20Analysis.pbix)

A publicly accessible live report link is currently unavailable due to Power BI / Microsoft Fabric license limitations.

### Home Page

![Home Page](Screenshots/1.%20Home.jpg)

The Home Page introduces the HR Attrition dashboard and separates the analysis into two major areas:

| Analysis Area | Coverage |
|---|---|
| **Overview** | Department, Job Role, Salary Band, Headcount, Employees Left |
| **Deep Dive** | Age Group, Gender, Education Field, Marital Status, Business Travel, Overtime |

The page also highlights key analytical questions such as:

- What is the overall attrition rate?
- Which departments are experiencing higher attrition?
- How does attrition vary across salary and age groups?

### Overview

![Overview](Screenshots/2.%20Over%20View.jpg)

The Overview page provides the main workforce KPIs and organizational attrition analysis.

**Key Analysis Areas**

- Overall Attrition Rate
- Employees Left
- Total Headcount
- Average Monthly Income
- Average Tenure of Leavers
- Attrition Rate by Department
- Attrition Decomposition
- Attrition by Job Role
- Attrition by Salary Band

**Interactive Filters**

- Department
- Gender
- Salary Band

### Deep Dive

![Deep Dive](Screenshots/3.%20Deep%20Drive.jpg)

The Deep Dive page provides detailed employee segmentation analysis across:

- Age Group
- Gender
- Education Field
- Marital Status
- Business Travel
- Overtime

This page helps identify workforce segments showing comparatively higher or lower attrition rates.

### Project Walkthrough Video

A complete walkthrough of the Microsoft Fabric and Power BI implementation is available below:

[Watch Project Walkthrough](https://drive.google.com/file/d/14C08ETxHqKhELwHhBPkMjArpU0i3gC5C/view?usp=sharing)

The walkthrough covers the end-to-end implementation from data preparation and Fabric storage to semantic modeling, security, and final Power BI analysis.

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

| Skill | Demonstrated Through |
|---|---|
| **Data Preparation** | Cleaning and preparing HR data for analysis |
| **Data Transformation** | Power Query and Dataflow Gen2 transformations |
| **Data Modeling** | Semantic Model development |
| **DAX & KPI Development** | Attrition and workforce measures |
| **HR Analytics** | Workforce segmentation and attrition analysis |
| **Business Analysis** | Translating HR data into actionable analytical findings |
| **Data Visualization** | Interactive Power BI dashboard development |
| **Dashboard Storytelling** | Home, Overview, and Deep Dive report structure |
| **Data Security** | OneLake Security and Column-Level Security testing |

---

## Acknowledgements

Special thanks to **Mansi Goel** for creating and sharing the structured Microsoft Fabric learning series, practical demonstrations, and guided project content that supported this learning journey.

---

## Author

**Supreet Tarwarkar**

- GitHub: https://github.com/SupreetTarwarkar
- LinkedIn: https://www.linkedin.com/in/supreettarwarkar/
