<!-- PROJECT TITLE -->
<h1 align="center">💼 Salary Prediction Model</h1>
<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9%2B-blue.svg" alt="Python">
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License">
  <img src="https://img.shields.io/badge/ML-Regression-orange.svg" alt="ML">
  <img src="https://img.shields.io/badge/Scikit--learn-Modeling-lightgrey.svg" alt="sklearn">
</p>

<p align="center">
Predict employee salaries from features like <b>Age</b>, <b>Gender</b>, <b>Education Level</b>, <b>Job Title</b>, and <b>Years of Experience</b>.<br/>
Includes data cleaning, EDA, feature engineering, and model training with Linear Regression, Decision Tree, and Random Forest.
</p>

<hr/>

<!-- QUICK LINKS -->
<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#dataset">Dataset</a> •
  <a href="#project-structure">Project Structure</a> •
  <a href="#results">Results</a> •
  <a href="#roadmap">Roadmap</a> •
</p>

<hr/>

<h2 id="overview">🔎 Overview</h2>
<p>
This project builds a <b>supervised machine learning regression</b> pipeline to predict salaries. It covers:
</p>
<ul>
  <li>Data loading & validation</li>
  <li>Cleaning & preprocessing (missing values, encoding, rare-category handling)</li>
  <li>EDA with visualizations</li>
  <li>Feature engineering (ordinal & one-hot encoding)</li>
  <li>Modeling with <b>Linear Regression</b>, <b>Decision Tree Regressor</b>, and <b>Random Forest Regressor</b></li>
  <li>Hyperparameter tuning via <code>GridSearchCV</code></li>
  <li>Model evaluation using R², MSE, MAE, RMSE</li>
  <li>Feature importance analysis</li>
</ul>

<h2 id="dataset">🗂️ Dataset</h2>
<ul>
  <li><b>Rows:</b> 6,704</li>
  <li><b>Columns (6):</b> Age, Gender, Education Level, Job Title, Years of Experience, Salary</li>
</ul>
<p><b>Target:</b> Salary (continuous)</p>

<h3>Preprocessing Highlights</h3>
<ul>
  <li>Missing values dropped (small fraction of rows)</li>
  <li>Rare <b>Job Title</b> categories (&lt; 25 samples) grouped into <code>Others</code></li>
  <li><b>Education Level</b> mapped: High School → 0, Bachelor's → 1, Master's → 2, PhD → 3</li>
  <li><b>Gender</b> label-encoded</li>
  <li><b>Job Title</b> one-hot encoded</li>
  <li>Outliers in <b>Salary</b> checked via IQR; no extreme outliers detected</li>
</ul>

<h2 id="project-structure">📁 Project Structure</h2>
<pre><code>.
├── dataset/
│   └── Salary_Data.csv              
├── Edunet_Employee_Salary_Prediction.ipynb
├── Images/
│   └── Correlation Heatmap.png
    |__ Correlation.png
    └── Distribution.png
    └── Gender vs Education vs Salary.png
    └── Important Features.png
    └── Mean Salary of Top 10 Highest Paying Job.png
    └── Relationship.png
├── README.md
</code></pre>


<h2 id="eda">📊 EDA Highlights</h2>
<ul>
  <li>Workforce skewed male; Bachelor’s most common education</li>
  <li>Salary strongly increases with <b>Years of Experience</b> and <b>Age</b> (experience stronger)</li>
  <li>Higher education → higher pay (PhD &gt; Master’s &gt; Bachelor’s &gt; High School)</li>
  <li>Top-paying roles: Data Scientist / Engineer</li>
  <li>Gender shows weakest correlation with Salary; minor pay gap observed</li>
</ul>
<p>
  <i>Screenshot</i>
  <br/>
  <img src="Images/Mean Salary of Top 10 Highest Paying Job.png" alt="Top Jobs by Mean Salary" width="45%"/>
  <img src="Images/Important Features.png" alt="Feature Importance" width="45%"/>
</p>

<h2 id="modeling">🧠 Modeling</h2>
<ul>
  <li>Models: Linear Regression, Decision Tree, Random Forest</li>
  <li>Hyperparameter tuning: <code>GridSearchCV</code> (5-fold CV)</li>
  <li>Train/Test Split: 75% / 25% (<code>random_state=42</code>)</li>
  <li>Metrics: R², MSE, MAE, RMSE</li>
</ul>

<h2 id="results">🏁 Results</h2>
<table>
  <thead>
    <tr>
      <th>Model</th>
      <th>R²</th>
      <th>Comments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Linear Regression</td>
      <td>0.833</td>
      <td>Baseline; underfits non-linearities</td>
    </tr>
    <tr>
      <td>Decision Tree</td>
      <td>0.941</td>
      <td>Good fit; some overfitting risk</td>
    </tr>
    <tr>
      <td><b>Random Forest</b></td>
      <td><b>0.971</b></td>
      <td><b>Best overall; lowest errors</b></td>
    </tr>
  </tbody>
</table>

<h3>Top Feature Importance (Random Forest)</h3>
<ol>
  <li>Years of Experience</li>
  <li>Age</li>
  <li>Education Level</li>
  <li>Job Title (selected roles)</li>
  <li>Gender</li>
</ol>

<h2 id="design-decisions">🧩 Key Design Decisions</h2>
<ul>
  <li><b>Rare-category handling</b> for Job Title to reduce sparsity and overfitting</li>
  <li><b>Ordinal mapping</b> for Education Level (meaningful order)</li>
  <li><b>Random Forest</b> chosen for robust performance on non-linear relationships</li>
</ul>

<h2 id="roadmap">🗺️ Roadmap</h2>
<ul>
  <li>Add features: company size, location, industry</li>
  <li>Try XGBoost / Gradient Boosting</li>
  <li>Add cross-validation and learning curves</li>
  <li>Package as a REST API (FastAPI/Flask)</li>
  <li>Streamlit app for interactive predictions</li>
  <li>Model fairness audit (gender/age bias checks)</li>
</ul>

<h2 id="requirements">📦 Requirements</h2>
<pre><code># requirements.txt (example)
pandas
numpy
matplotlib
seaborn
scikit-learn
joblib
</code></pre>

<h2 id="contributing">🤝 Contributing</h2>
<p>
Pull requests are welcome! For major changes, please open an issue first to discuss your ideas.
</p>


