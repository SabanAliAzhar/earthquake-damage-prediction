Earthquake Damage Prediction using Decision Trees

Linkedin: https://www.linkedin.com/posts/saban-ali-azhar_datascience-realestateanalytics-machinelearning-activity-7340679548113457153-Iy2t?utm_source=share&utm_medium=member_desktop&rcm=ACoAACVVYIwByh5BR1h4pC5qtm1963ga1EwOzN0

📌 Table of Contents
- [📊 Problem Statement](#-problem-statement)
- [🧰 Tools & Technologies](#-tools--technologies)
- [📂 Project Structure](#-project-structure)
- [⚙️ Workflow](#️-workflow)
- [📈 Results](#-results)
- [📷 Visualizations](#-visualizations)
- [🚀 How to Run](#-how-to-run)
- [✅ Requirements](#-requirements)
- [🤝 Acknowledgments](#-acknowledgments)
- [📬 Contact](#-contact)

- 📊 Problem Statement

After a natural disaster, understanding building vulnerabilities is critical. In this project, we aim to:
Predict whether a building will suffer severe damage (Grade 4 or 5) based on its structural attributes.
This binary classification model aids urban planning, resource allocation, and disaster mitigation efforts.

🧰 Tools & Technologies

- Python 
- SQLite – for structured relational data
- Pandas & NumPy – for data wrangling
- Scikit-learn – for machine learning models & pipelines
- Category Encoders – for ordinal encoding of categorical features
- Matplotlib – for data and model visualization
- Jupyter Notebook – for interactive development

⚙️ Workflow

 🔍 1. Data Wrangling
- Connected to the SQLite database
- Merged tables: `id_map`, `building_structure`, and `building_damage`
- Filtered data by `district_id = 4`
- Dropped:
  - Post-earthquake features (`post_eq`)
  - High-cardinality columns (e.g., `building_id`)
  - Multicollinear features (e.g., `count_floors_pre_eq`)

 🧪 2. Feature Engineering
- Created a new binary target: `severe_damage` = 1 if damage grade > 3
- Used `OrdinalEncoder` for categorical variables

 🤖 3. Modeling
- Built a `Pipeline` with:
  - OrdinalEncoder
  - `DecisionTreeClassifier` with `max_depth=6`
- Evaluated using:
  - `accuracy_score`
  - Train/Test split
  - Model `.score()` method

 📊 4. Interpretation
- Visualized top levels of the decision tree using `plot_tree`
- Plotted **feature importances** based on Gini Index
