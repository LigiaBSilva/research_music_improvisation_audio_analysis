# research_music_improvisation_audio_analysis
Audio features extraction (BPM, beat confidence), as part of data analysis for an empirical experiment on music improvisation, mental states and time perception

# Musical Improvisation, Audio Features & Time Perception

## Overview

This is a small part of data analysis from an experiment exploring how different improvisational contexts influence mental states and subjective time perception. Several measures were collected, such as duration estimates, ratings of attentional focus, perceived difficulty, emotional engagement etc..


In this part of the analysis we investigated whether acoustic properties of music being created during improvisations were associated with musicians’ perception of duration.


A key hypothesis explored during this analysis was that measurable audio features—such as tempo and beat salience—may help explain variations in perceived duration.

---

## Research Question

Does musical improvisation influence musicians’ perception of time, and are these effects associated with objective audio features extracted from the performances?

---

## Experimental Design

Participants completed improvisation tasks under different conditions:

- **musical setting: Solo vs Group
- **improvisation task:
  - A: Familiar harmony
  - B: Unfamiliar harmony
  - C: Free improvisation

Each participant completed 6 tasks.

For each task, we collected:
- Audio recordings of improvisations
- Self-reported measures (time perception, enjoyment, difficulty, etc.)

---

## Data Processing Pipeline

The analysis pipeline includes the following steps:

### 1. Data Loading
Participant response data was loaded from CSV format, containing metadata for each improvisation task.

### 2. Audio Path Construction
For each row in the dataset:
- Experimental condition metadata was extracted
- A corresponding file path to the audio recording was constructed dynamically
- These paths were stored as a new column in the dataset

### 3. Audio Feature Extraction
Audio files were processed using **Essentia**, extracting features including:
- Estimated tempo (BPM)
- Beat salience / beat confidence

Extracted features were stored as new variables for statistical analysis.

---

## Statistical Analysis

To assess relationships between conditions and extracted features, we applied:

- Independent t-tests
- One-way ANOVAs

(Full analysis in the original study also included linear mixed-effects models, though only simpler tests are shown in this notebook version.)

---

## Key Findings

- Beat confidence varied significantly across experimental conditions
- BPM did not significantly differ across conditions
- Neither BPM nor beat confidence significantly predicted time estimation

---

## Tools & Libraries

- Python
- pandas
- numpy
- scipy
- statsmodels
- Essentia (audio feature extraction)

---

## Project Structure
