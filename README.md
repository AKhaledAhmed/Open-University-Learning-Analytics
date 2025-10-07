# 🎓 Open University Learning Analytics 

This project performs a comprehensive analysis of student engagement, academic performance, and learning behaviors using the **Open University Learning Analytics Dataset (OULAD)**. It combines advanced **Python-based data analysis and preprocessing** with **interactive Power BI dashboards** to uncover key relationships between student activity in the Virtual Learning Environment (VLE) and academic success.

-----

## 🚀 Project Overview

| Detail | Description |
| :--- | :--- |
| **Dataset** | Open University Learning Analytics Dataset (OULAD) |
| **Tools Used** | Python (Pandas, NumPy, Matplotlib, Seaborn, Plotly,sqlite3) & Power BI |
| **Objective** | Explore how students’ online interactions and assessment performance affect their final results (Pass, Fail, Distinction, Withdrawn). |

-----

## 📚 Data Sources
### Data link [https://analyse.kmi.open.ac.uk/open-dataset?utm_source=chatgpt.com]
The project utilizes seven interconnected CSV files from the OULAD:

| File | Description |
| :--- | :--- |
| `assessments.csv` | Details on module assessments (type, weight, due date). |
| `courses.csv` | Information on course modules and presentation lengths. |
| `studentInfo.csv` | Student demographic data and final academic results. |
| `studentRegistration.csv` | Dates of student registration and official withdrawal. |
| `studentVle.csv` | Log of individual student interactions (clicks per VLE material). |
| `vle.csv` | Details about the VLE activities (type, URL, activity name). |
| `studentAssessment.csv` | Student scores for individual assessments. |

-----

## ⚙️ Data Cleaning & Preprocessing

Data manipulation and preprocessing were critical steps performed in the Jupyter Notebook to prepare the data for analysis and visualization:

  * **Assessments Table:**
      * Missing assessment dates were imputed with `-1` (representing the final week of the course).
      * Assessment types were numerically encoded: **`TMA`** → 1, **`CMA`** → 0, **`Exam`** → 2.
      * Module codes (`AAA`–`GGG`) were numerically encoded (0–6).
  * **Courses Table:**
      * A derived column, `presentation_period`, was added to differentiate the cohorts: **B** (February start) vs. **J** (October start).
  * **Student Info Table:**
      * Handled null values and standardized categorical variables (`final_result`, `gender`, `age_band`, `region`, etc.).
  * **Student VLE Table:**
      * Grouped by `id_student` and `code_module` to calculate the total clicks (`sum_click`), serving as the primary measure of student engagement.
  * **Student Assessment Table:**
      * Merged with the `assessments` table to incorporate type and weight information.
      * Computed metrics like **average score** and **total assessment weight** per student.

-----

## 🔍 Exploratory Data Analysis (EDA)

Exploratory analysis was conducted in the Jupyter Notebook using visualization libraries like Matplotlib, Seaborn, and Plotly.

### Key Analysis Areas

1.  **Engagement Analysis:** Distribution of total VLE clicks segmented by final student result.
2.  **Course Performance:** Comparison of pass/fail rates across different modules and between presentation periods (B vs. J).
3.  **Assessment Breakdown:** Comparative analysis of average marks achieved across the three assessment types (TMA, CMA, Exam).
4.  **Student Demographics:** Analysis of how factors like `highest_education`, `age_band`, and `disability` correlate with final results.
5.  **Correlation Insights:** Determining the relationship between engagement metrics, `studied_credits`, and final academic outcomes.

-----

## 📊 Power BI Dashboards

This project includes **three interactive Power BI dashboards** designed to visualize insights from the Open University Learning Analytics Dataset (OULAD).  
Each dashboard focuses on a different analytical dimension — **student engagement, course performance, and learning outcomes** — providing a complete view of the online learning environment.

---

### 🎯 **1. VLE Dashboard (Virtual Learning Environment)**

<img width="1317" height="738" alt="Screenshot 2025-10-04 102736" src="https://github.com/user-attachments/assets/193741cd-b483-42ef-a64e-f97a74af9d17" />


**Purpose:**  
Analyzes student engagement patterns across different activity types and final academic results to understand how online interaction influences performance.

**Key Insights:**
- **Engagement vs. Final Result:** Over **60%** of total clicks come from students who **passed**, confirming that higher activity correlates with better outcomes.  
- **Activity Type Breakdown:** Most engagement occurs in *“oucontent”* (course materials), followed by *forum* and *quiz* interactions.  
- **Detailed Clicks:** A detailed view of click activity by site and module presentation supports micro-level engagement tracking.

**Use Case:**  
Helps educators and content designers identify which activities most effectively engage students.

---

### 📘 **2. Courses Dashboard**

<img width="1317" height="740" alt="Screenshot 2025-10-04 102746" src="https://github.com/user-attachments/assets/e7b4238e-6961-4ecb-9e6c-c2ab8013c37e" />


**Purpose:**  
Compares performance across different modules and presentations, focusing on **pass rates, assessment results,** and **student retention.**

**Key Insights:**
- **Pass Rate Analysis:** Visualizes differences across modules (`AAA`–`GGG`) and presentations (`2013J`, `2014B`, etc.).  
- **Assessment Comparison:** The *Average Score by Assessment Type* chart highlights performance differences between **exams**, **TMAs**, and **CMAs**.  
- **Retention Insights:** The *Count of Students by Status* chart tracks **completed vs. dropped** students for each course.  
- **Course Duration Effect:** The bubble chart correlates *module presentation length* with *pass rate* and *student count*.

**Use Case:**  
Supports academic coordinators in evaluating course effectiveness and identifying modules needing instructional improvement.

---

### 🧑‍🎓 **3. Students Dashboard**

<img width="1312" height="735" alt="Screenshot 2025-10-04 102755" src="https://github.com/user-attachments/assets/e4593b9f-994b-4d5a-9b6a-c6059476ac8d" />


**Purpose:**  
Explores demographic and behavioral factors affecting student outcomes, such as **education level, engagement level,** and **socioeconomic background.**

**Key Insights:**
- **Student Population:** Over **28.7K students** analyzed across modules and years.  
- **Engagement & Attempts:** Line and bar charts link **total VLE clicks** and **previous attempts** to academic success.  
- **Pass Rate by IMD Band:** Students from higher-income backgrounds (IMD 80–100%) show significantly higher pass rates.  
- **Education Level Impact:** Students with “HE Qualification” and “A Level” backgrounds perform best.  
- **Final Result Composition:** “Pass” and “Distinction” categories make up the majority of final outcomes.

**Use Case:**  
Empowers student support teams and policymakers to detect at-risk students and address equity gaps.

---

### 🧩 **Dashboard Integration**

Together, the three dashboards create a **comprehensive learning analytics ecosystem**:

> **Engagement (VLE Dashboard)** ➜ **Course Performance (Courses Dashboard)** ➜ **Student Outcomes (Students Dashboard)**

This integration enables educators and analysts to:
- Detect early signs of disengagement,  
- Compare course-level effectiveness, and  
- Improve student retention through data-informed strategies.

-----

## 💡 Insights & Findings

The analysis yielded several key insights into student success:

  * **Engagement is Key:** Students demonstrating **higher engagement (more VLE clicks)** achieved significantly **better outcomes**.
  * **Assessment Impact:** **TMAs (Tutor Marked Assignments) and Exams** showed the strongest correlation with a student's final result.
  * **Module Length:** Modules with **longer presentation lengths** (e.g., EEE, FFF) generally exhibited **higher pass rates**.
  * **Withdrawal Behavior:** Students who withdrew early typically exhibited **minimal early engagement** and low click activity.
  * **High-Performing Courses:** Courses `DDD` and `EEE` consistently demonstrated high average student performance.
  * **Activity Timing:** Engagement levels tend to drop gradually over the course timeline but peak sharply just before the deadlines for TMAs.

-----

## 📦 Requirements & Setup

To replicate the Python analysis in `project.ipynb`, install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn plotly sqlite3
```

**Note:** The Power BI dashboards require the Power BI Desktop application and the connection to the analyzed data files. Ensure all original OULAD CSV files are in the same directory as the Jupyter Notebook for smooth execution.
