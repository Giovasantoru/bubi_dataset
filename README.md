# Bike Trip Analysis Project

This project analyzes bike trip data to address two main tasks:
1. Assessing the sensitivity of bike rentals to weather conditions, particularly during rush hours.
2. Analyzing top routes and rental points to determine the best locations for advertising based on traffic and geographic spread.

## Folder Structure

- **data/**  
  Contains all CSV files generated through cleaning and merging operations, as well as the three initial CSV files provided.

- **notebooks/**  
  Contains all Jupyter Notebook files used for the analysis. The key notebooks for the challenge are:
  
  - **Rush Hours Sensitivity analysis.ipynb**  
    - Identifies morning and afternoon rush hours on working days.
    - Analyzes whether weather factors have less impact during rush hours compared to non-rush hours.
    - *Findings:*
      - **Rush Hour vs. Non-Rush Hour:** Rush hours show the highest average trip counts. However, weather (e.g., bad weather) still significantly decreases trip counts during rush hours, partly because higher baseline demand magnifies the absolute effect.
      - **Wind Speed:** A more pronounced negative effect on non-rush hours than on rush hours.
      - **Pressure:** A small but statistically significant negative effect, more apparent during non-rush hours.
      - **Interactions:** Interaction terms (e.g., between rush hour and weather factors like bad weather or temperature) are generally not statistically significant, suggesting that the *relative* impact of weather is similar between rush and non-rush hours.
  
  - **Top routes analysis.ipynb**  
    - Evaluates the effect of weather on the top 10 most common end stations based on average trip numbers.
    - *Findings:* Temperature is the dominant weather factor influencing trip counts at key stations, while other weather variables have a limited effect. This suggests that demand at strategic locations is robust, driven by necessity or strong incentives.

  - **Single top stations analysis.ipynb**  
    - Examines the most common stations individually.
    - *Findings:*
      - Commuter-driven stations in Budapest show strong resilience to everyday weather, with trip counts mainly influenced by time-of-day and, to a lesser extent, atmospheric pressure.
      - Recreational stations, such as Margitsziget, are more sensitive to weather factors (especially humidity and weekends), highlighting differences in usage patterns between utilitarian and leisure travel.

  - **rental points to place ads.ipynb**  
    - Displays the rental stations with the highest overall traffic (combining both starting and ending points).
    - Based on traffic and geographic distribution, the final selection for ad placement includes three stations.
    - *Findings:* The recommended stations for advertising are:
      - **Margaret Island (1304)**
      - **Kálvin tér (905)**
      - **Nyugati tér (611)**
    - These locations provide optimal exposure with a minimum distance of 1 km between stations to reach a broad user base.

- **README.md**  
  This file summarizes the main operations and findings of each component of the project.

## How to Use

1. **Data Preparation:**
   - The **data** folder contains both raw and processed CSV files. Data cleaning and merging processes are documented in the notebooks.
  
2. **Analysis Notebooks:**
   - Open the notebooks in the **notebooks** folder using Jupyter Notebook.
   - The key notebooks are:
     - `Rush Hours Sensitivity analysis.ipynb`
     - `Top routes analysis.ipynb`
     - `Single top stations analysis.ipynb`
     - `rental points to place ads.ipynb`
   - Each notebook begins with the import and installation of all necessary libraries.
  
3. **Project Execution:**
   - Review each notebook to follow the step-by-step analysis.
   - Detailed comments and markdown cells in the notebooks explain the rationale behind each step, the hypotheses tested, and the main findings.
   - The README files within the notebooks provide summaries of the operations and results for their respective analyses.

## Technical Details

- **Python Version:** Python 3.12.10
- **Libraries Used:**
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - haversine
  - itertools
  - statsmodels
  - scipy
  - scikit-learn (sklearn)
  
  All required libraries are either imported or, if necessary, installed at the beginning of each notebook.

## Findings Summary

- **Rush Hours Sensitivity analysis.ipynb:**
  - Rush hours have higher average trip counts.
  - Weather factors, especially bad weather, and humidity have a strong negative effect during rush hours, sometimes even in absolute terms that exceed the decrease seen in non-rush hours (due in part to higher baseline demand).
  - Wind speed affects non-rush hours more strongly.
  - Atmospheric pressure exhibits a small, significant negative influence on trip counts, particularly during non-rush hours.
  - Interaction effects between rush hour and weather variables are generally not statistically significant.

- **Top routes analysis.ipynb:**
  - Temperature stands out as the key weather factor affecting trip counts at top end stations, with other weather factors showing limited impact.

- **Single top stations analysis.ipynb:**
  - Commuter-driven stations show resilience to everyday weather, with trip counts mainly driven by time-of-day.
  - Recreational stations are more weather-sensitive, particularly in relation to humidity and weekend effects.

- **rental points to place ads.ipynb:**
  - Our analysis recommends advertising at Margaret Island (1304), Kálvin tér (905), and Nyugati tér (611) based on user traffic and geographic distribution.

---

This README file is intended to guide our team and collaborators through the project, providing a comprehensive overview of the methods used, how to navigate the code, and the key findings of our analysis.
