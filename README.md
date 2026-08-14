# Microsoft Fabric Learning Journey

A structured learning journey focused on **Microsoft Fabric, data analytics, data engineering concepts, and Power BI integration**.

This repository documents my topic-wise learning, hands-on practice, technical notes, and guided project implementation using Microsoft Fabric.

---

## What I Learned

### Microsoft Fabric Fundamentals

* Microsoft Fabric overview and architecture
* Fabric workloads
* Workspaces and workspace roles
* Contributor role
* Fabric capacity and F SKUs
* Fabric trial and capacity concepts

### OneLake

* Microsoft OneLake
* Unified data lake concept
* Centralized data storage
* OneLake across Fabric workloads
* OneLake and Power BI integration
* Direct Lake

### Lakehouse

* Microsoft Fabric Lakehouse
* Lakehouse architecture
* Files and Tables
* Structured and unstructured data
* Medallion architecture
* Bronze, Silver and Gold layers

### Data Ingestion & Orchestration

* Data ingestion in Microsoft Fabric
* Data Pipelines
* Pipeline activities
* Pipeline orchestration
* Activity dependencies
* On Success
* On Failure
* On Completion
* On Skip

### Data Transformation

* Data preparation and transformation
* Data cleaning
* Bronze-to-Silver transformation
* Power Query transformations
* Data transformation workflows

### PySpark & Data Processing

* PySpark fundamentals
* PySpark DataFrames
* PySpark for large-scale data processing
* PySpark vs Pandas
* Data transformation using PySpark

### SQL

* SQL querying
* Filtering and aggregation
* Grouping and analysis
* SQL-based data transformation

### Power BI & Fabric Integration

* Power BI integration with Microsoft Fabric
* Lakehouse to Power BI workflow
* Semantic models
* Direct Lake
* Power BI report development
* Data visualization
* Business-oriented analysis

---

## Technologies & Tools

* Microsoft Fabric
* OneLake
* Lakehouse
* Dataflow Gen2
* Power Query
* Semantic Model
* SQL
* Power BI
* PySpark
* GitHub

---

## Learning & Implementation Approach

### Learn → Reinforce → Practice → Document → Build → Showcase

1. **Learn** — Studied Microsoft Fabric topics through a structured, topic-wise video learning series.
2. **Reinforce** — Reviewed important concepts and demonstrations more than once.
3. **Practice** — Created handwritten notes and practiced the concepts directly in Microsoft Fabric.
4. **Document** — Organized learning notes, practical work, screenshots and project documentation in GitHub.
5. **Build** — Applied the learned concepts through guided project implementation.
6. **Showcase** — Organized the project, dashboards, screenshots and demonstration for portfolio presentation.

---

# Guided Project — HR Attrition Analysis

As part of the learning journey, Microsoft Fabric concepts were applied through a **guided HR Attrition Analysis project** using Microsoft Fabric and Power BI.

The project demonstrates an end-to-end workflow from data preparation to analytical reporting.

## Project Workflow

```text
Source Data
     ↓
Dataflow Gen2
     ↓
Data Transformation
     ↓
Lakehouse
     ↓
Semantic Model
     ↓
Power BI Report
     ↓
Analysis & Visualization
```

## Fabric Components Used

### Dataflow Gen2

Used for data ingestion and data transformation within the Fabric environment.

### Lakehouse

Used to store and work with the prepared data.

### Semantic Model

Used to structure the data for analytical reporting.

### Power BI

Used to create interactive reports and visualize the analysis.

---

## Analysis Covered

The project explores employee attrition across different dimensions, including:

* Overall attrition
* Department
* Job role
* Salary band
* Age group
* Gender
* Education
* Marital status
* Business travel
* Overtime

The report includes KPI cards, filters, comparative analysis and detailed visualizations.

---

## Project Screenshots

### Power BI Report — Home

![HR Attrition Dashboard Home](Projects/HR-Attrition/Screenshots/Home.jpg)

### Power BI Report — Overview

![HR Attrition Overview](Projects/HR-Attrition/Screenshots/Over%20View.jpg)

### Power BI Report — Deep Dive

![HR Attrition Deep Dive](Projects/HR-Attrition/Screenshots/Deep%20Drive.jpg)

### Fabric Workspace

![Fabric Workspace](Projects/HR-Attrition/Screenshots/Workspace_HR.jpg)

### Lakehouse

![HR Lakehouse](Projects/HR-Attrition/Screenshots/Lakehouse_HR.jpg)

### Semantic Model

![HR Semantic Model](Projects/HR-Attrition/Screenshots/Semantic%20Model.jpg)

### Dataflow Gen2

![HR Dataflow Gen2](Projects/HR-Attrition/Screenshots/Data%20flow%20gen%202.jpg)

### CLS

![CLS](Projects/HR-Attrition/Screenshots/CLS.jpg)

---

## Project Files

The complete project documentation and supporting files are available in the project folder:

[HR Attrition Project](Projects/HR-Attrition/)

The folder contains:

* Project documentation
* Screenshots
* Dataset
* Power BI file
* Project demonstration link

---

## Dataset Source

The dataset used during the learning/project exercise:

[Sales Dataset — Raw CSV](https://raw.githubusercontent.com/the-mansi-goel/FABRIC/refs/heads/main/sales_data.csv)

---

## Project Demonstration

A demonstration video showing the project and Microsoft Fabric implementation:

[View Project Demonstration](https://drive.google.com/file/d/14C08ETxHqKhELwHhBPkMjArpU0i3gC5C/view?usp=sharing)

---

# Learning Resource & Reference

This learning journey was supported by the structured **Microsoft Fabric learning series by Mansi Goel**.

The concepts, demonstrations and guided project workflow were followed as part of the learning process. The notes, documentation, screenshots and project organization in this repository represent my learning and practice based on these resources.

### Primary Learning Resource

[Microsoft Fabric Learning Series — Mansi Goel](https://youtube.com/playlist?list=PLTrZQU5-tBf7Lp0bJWvcjLiwUiUS-iEDb&si=qS1q9ILYpDBtXBGB)

---

# Certifications

### Microsoft Certified: Power BI Data Analyst Associate — PL-300

[View Microsoft Credential](https://learn.microsoft.com/en-us/users/supreettarwarkar/credentials/b29f0f1736af0b52)

### Microsoft Certified: Fabric Analytics Engineer Associate — DP-600

[View Microsoft Credential](https://learn.microsoft.com/en-us/users/supreettarwarkar/credentials/63b7b94a00ef0870)

---

# Acknowledgement

Special thanks to **Mansi Goel** for creating and sharing the structured Microsoft Fabric learning series, practical demonstrations and guided project content that supported this learning journey.

[Microsoft Fabric Learning Series — Mansi Goel](https://youtube.com/playlist?list=PLTrZQU5-tBf7Lp0bJWvcjLiwUiUS-iEDb&si=qS1q9ILYpDBtXBGB)

---

# Author

**Supreet Tarwarkar**

Data Analytics | Microsoft Fabric | Power BI | SQL | Python | FinTech Analytics

---

> **Learn → Practice → Document → Build → Showcase**
