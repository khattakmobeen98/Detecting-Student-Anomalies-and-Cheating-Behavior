# Detecting-Student-Anomalies-and-Cheating-Behavior

## Project Overview
This project uses machine learning to identify potentially suspicious student behavior, which may be indicative of cheating. The analysis combines data from multiple sources, including student information, assessment scores, and virtual learning environment (VLE) clicks, to build a comprehensive profile for each student. The goal is to flag students with anomalous behavioral patterns for further investigation.

## Methodology
The project follows these key steps:

1.  **Data Integration**: Multiple datasets (`assessments.csv`, `courses.csv`, `studentAssessment.csv`, `studentInfo.csv`, `studentRegistration.csv`, `studentVle.csv`, `vle.csv`) are loaded and merged into a single dataframe, with one row per student.
2.  **Feature Engineering**: Key features are engineered from the raw data.
    * **`avg_score`**: The student's average assessment score.
    * **`assessment_attempts`**: The total number of assessment attempts.
    * **`total_clicks`**: The total number of clicks a student made in the VLE.
    * **`avg_clicks`**: The average number of clicks per VLE activity.
    * **`late_registration`**: A binary flag indicating if a student registered late.
3.  **Anomaly Detection**: An **Isolation Forest** model is trained on the prepared features to identify outliers. The model is configured to detect a `contamination` rate of 5%.
4.  **Suspicious Students Identified**: The model flags students who exhibit anomalous behavior, which could be an indicator of cheating.

## Technologies & Libraries
* **Python**: The core programming language for the project.
* **Pandas**: Used for data loading, cleaning, and merging.
* **Scikit-learn**: Provides the `IsolationForest` model for anomaly detection and `StandardScaler` for feature scaling.
* **Jupyter Notebook**: The analysis is contained within a Jupyter Notebook, providing a step-by-step walkthrough of the process.
