# Logistic Regression Classification Workflow using Orange

An end-to-end data mining and machine learning workflow built using the **Orange Data Mining** tool. This project demonstrates data ingestion, feature selection, model training via Logistic Regression, and performance evaluation.

---

## 💻 Workflow Architecture

This visual pipeline orchestrates the data flow from raw input to performance scoring. Below is the active layout of the visual programming environment:

![Orange Workflow Workspace](path/to/your/Screenshot_2026-06-11_221329.png)

---

## 🛠️ Components & Widget Breakdown

The workflow utilizes the following core Orange widgets arranged sequentially:

### 1. 📄 File Widget
* **Category:** Data
* **Purpose:** Loads the primary dataset into the workspace. It reads local files (such as `.xlsx`, `.csv`, or native `.tab` formats) and automatically maps preliminary attribute types (categorical, numeric, text) and roles.
### 2. 🗂️ Select Columns Widget
* **Category:** Transform
* **Purpose:** Manages the dataset features. It filters out irrelevant columns and explicitly defines the **Features** (independent variables) and the **Target** (dependent variable/class label) before passing data down the pipeline.
### 3. 📈 Logistic Regression Widget
* **Category:** Model
* **Purpose:** Acts as the learning algorithm (**Learner**). It initializes a standard logistic regression model with customizable regularization parameters ($L_1$ or $L_2$ penalties) to handle binary or multinomial classification tasks.
### 4. 🧪 Test and Score Widget
* **Category:** Evaluate
* **Purpose:** The final evaluation node. It receives the dataset processing schema from *Select Columns* and the training algorithm structure from *Logistic Regression*. It executes validation techniques (such as Cross-Validation or Random Sampling) to output key evaluation metrics.
* **Expected Outputs:** Classification Accuracy (CA), AUC (Area Under ROC), F1-Score, Precision, and Recall.
---

## 🔌 Data Connections (Data Flow)

The links connecting the widgets pass specific data streams through the pipeline:
* **File** ➡️ **Select Columns**: Passes the raw loaded dataset string (`Data`).
* **Select Columns** ➡️ **Test and Score**: Passes the refined data subset with isolated targets (`Data`).
* **Select Columns** ➡️ **Logistic Regression**: Passes the training dataset structure (`Data`).
* **Logistic Regression** ➡️ **Test and Score**: Passes the trained classification logic framework (`Learner`).

---

## 🚀 How to Run the Project

1. Install **Orange Data Mining** (v3.x or later).
2. Clone this repository to your local directory.
3. Open Orange and select `File -> Open` to load the `orange workflow.ows` file.
4. Double-click the **File** widget to point to your data source, then double-click **Test and Score** to inspect model evaluations.
