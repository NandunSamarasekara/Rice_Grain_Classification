# Rice Cammeo and Osmancik - Exploratory Data Analysis (EDA)

This project contains an exploratory data analysis (EDA) pipeline for the **Rice Cammeo and Osmancik** dataset, implemented in a Jupyter Notebook designed to run on Google Colab.

---

## Project Overview

The notebook handles loading, decoding, inspecting, and visualizing a dataset stored in an Attribute-Relation File Format (`.arff`). It performs initial data quality checks and analyzes the geometric features of rice grains to distinguish between the two distinct varieties (*Cammeo* and *Osmancik*).

---

## Dataset Information

* **Relation Name:** `Rice_Cammeo_Osmancik`
* **Total Instances:** 3,810 rows and 8 columns
* **Target Variable:** `Class` (Nominal, with categories: `Cammeo` and `Osmancik`)
* **Features (Numeric):**
  * `Area`
  * `Perimeter`
  * `Major_Axis_Length`
  * `Minor_Axis_Length`
  * `Eccentricity`
  * `Convex_Area`
  * `Extent`

---

## Key Steps & Workflow

* **Data Loading & Preprocessing:** 
  * Mounts Google Drive to access the data directory (`/content/drive/MyDrive/Y3S1ML`).
  * Uses the `scipy.io.arff` module to load the `.arff` file format into a Pandas DataFrame.
  * Decodes nominal attributes from byte strings (e.g., `b'Cammeo'`) into standard UTF-8 text strings.
* **Data Inspection & Quality Checks:** 
  * Verifies dataset dimensions (`3810, 8`) and inspects the first 10 rows[cite: 1].
  * Confirms that there are **0 missing values** across all columns and **0 duplicate rows**.
  * Generates comprehensive descriptive statistics (`df.describe()`) for all numeric features.
* **Class Distribution Analysis:** 
  * Analyzes target class proportions: **Osmancik** accounts for 2,180 instances (~57.22%) and **Cammeo** accounts for 1,630 instances (~42.78%)[cite: 1].
* **Visualizations:** 
  * Plots a count distribution of the target classes using Seaborn.
  * Generates histograms with 30 bins for all independent features.
  * Produces boxplots for each feature grouped by the target class to observe feature-wise variance and separability[cite: 1].

---

## Prerequisites & Dependencies

To run this notebook successfully, the following Python libraries are required:
* `os`
* `pandas`
* `numpy`
* `matplotlib.pyplot`
* `seaborn`
* `scipy.io` (specifically `arff`)