

# Music Improvisation, Time Perception & Audio Analysis

This repository contains the data analysis pipeline for an empirical study investigating how **musical improvisation influences musicians' perception of time**, and whether these effects are associated with **objective audio features** extracted from musical performances.

---

# Research Question

**Does musical improvisation influence musicians' perception of time, and are these effects associated with objective audio features extracted from the performances?**

---

# Experimental Design

Participants completed improvisation tasks under different experimental conditions.

## Independent Variables

| Factor             | Levels                                                                            |
| ------------------ | --------------------------------------------------------------------------------- |
| Musical Setting    | Solo / Group                                                                      |
| Improvisation Task | **A:** Familiar harmony<br>**B:** Unfamiliar harmony<br>**C:** Free improvisation |

Each participant completed **six improvisation tasks**.

---

## Data Collected

For each improvisation task, the following data were collected:

* Audio recordings of the improvisations
* Self-reported measures, including:

  * Time estimation
  * Perceived speed of time passage
  * Mental States: fluctuations in attentional demand and focus
  * Enjoyment
  * Difficulty
  * Familiarity
* Demographic information

---

# Project Structure

```text
music-improvisation-time-perception-analysis/
│
├── README.md
│
├── data/
│── raw/
│    ├── improv_time_results_base.csv
│    ├── improv_time_demographic_public.csv
│    └── recordings/
│  
│
└── notebooks/
    ├── 01_etl_and_time_analysis.ipynb
    └── 02_audio_feature_analysis.ipynb
 


---

# Analysis Pipeline

## 1. Data Loading

Participant responses were imported from CSV files containing metadata for each improvisation task.

## 2. ETL (Extract, Transform, Load)

The dataset was cleaned by:

* Removing incomplete observations
* Verifying data types
* Renaming variables for consistency
* Removing irrelevant variables

## 3. Data Preparation

Additional variables were created to facilitate statistical analysis, including:

* Relative time estimation measures
* Merging demographic information
* Saving the cleaned dataset
* Exploring potential outliers

## 4. Statistical Analysis

Relationships between experimental conditions and psychological measures were investigated using:

* Pearson correlations
* Independent-samples t-tests
* One-way ANOVAs
* Linear mixed-effects models (LMM)

The notebook included in this repository focuses primarily on exploratory analyses and classical statistical tests. The complete linear mixed-effects models were conducted during the final stage of the research and are not fully reproduced here.

## 5. Audio Feature Extraction

Audio analysis was conducted in a separate notebook dedicated to feature extraction.

The objective was to investigate whether acoustic properties of musical improvisations were associated with musicians' perception of duration.

Audio files were processed using **Essentia**, extracting:

* Estimated tempo (BPM)
* Beat confidence (beat salience)

For each observation:

* Experimental metadata were used to construct the corresponding audio file path.
* Audio features were extracted automatically.
* Extracted features were added to the dataset for subsequent statistical analyses.

Differences in audio features across improvisation conditions were examined using:

* Independent-samples t-tests
* One-way ANOVAs

These variables were later incorporated into linear mixed-effects models, which are not included in this repository.

---

# Main Findings

The principal findings of the study were:

* Estimated duration differed between **solo** and **group** improvisation.
* Differences in duration estimation were **not explained** by the collected psychological or acoustic measures.
* The perceived speed of time passage was associated with **enjoyment** and **mind wandering**, and differed between free and structured improvisation tasks.
* **Beat confidence** varied significantly across some experimental conditions, suggesting differences in the stability of the musical pulse.
* **Tempo (BPM)** did not differ significantly between experimental conditions.
* Neither **tempo** nor **beat confidence** significantly predicted participants' time estimation.

---

# Technologies

* Python
* pandas
* NumPy
* SciPy
* statsmodels
* Essentia
* Jupyter Notebook

---

# Repository Contents

| Notebook                            | Description                                                                            |
| ----------------------------------- | -------------------------------------------------------------------------------------- |
| **01_etl_and_time_analysis.ipynb**  | Data cleaning, preprocessing, and statistical analyses of questionnaire data           |
| **02_audio_feature_analysis.ipynb** | Audio feature extraction using Essentia and statistical analysis of acoustic variables |

---

# Citation

If you use this repository in academic work, please cite the corresponding publication or contact the author for citation details.

