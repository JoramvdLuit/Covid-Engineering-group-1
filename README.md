# COVID-19 Infections Dashboard
Data Engineering Covid Assignment


By Boris van Os, Marthe Welkzijn (2732375) & Joram van der Luit (2706244)
This repository provides a comprehensive analysis and interactive dashboard to study the spread of COVID-19. The project covers data visualization, parameter estimation using an extended SIR model (including a deceased state), data wrangling, and an interactive dashboard built with Streamlit.


Table of Contents
•	Project Overview
•	Project Parts and User Interaction 
  o	Part 1: Data Visualization & SIR Model Simulation
  o	Part 3: Database Interaction & Country Analysis
  o	Part 4: Data Wrangling
  o	Part 5: Interactive Dashboard
  o	Part 6: Version Control and Deployment
•	Prerequisites
•	How to Run the Program
•	Project Structure
•	SIR Model fit test and conclusions


Project Overview
The project is designed to analyze COVID-19 data from various sources using Python. It simulates the epidemic using a SIR model with a death component, compares different parameter estimation methods, and provides an interactive dashboard for exploring global and country-specific trends.


Project Parts and User Interaction
Part 1: Data Visualization & SIR Model Simulation
•	What It Does:
  o	Loads time-series data from day_wise.csv and generates line graphs for new cases, deaths, and recoveries over time.
  o	Implements a SIR model (with an added Deceased state) and simulates the epidemic using three different parameter sets.
  o	Provides functions to filter the time range for visualization.
•	User Interaction:
  o	Users can call functions like plot_figure_dates(df, start_date, end_date) to visualize the data within a specific date       range.
  o	The SIR model simulation functions enable users to plot Covid data by simulating the number of deaths, infected             confirmed etc using parameters sets.


Part 3: Database Interaction & Country Analysis
•	What It Does:
  o	Connects to an SQLite database (covid_database.db) that contains multiple tables such as country-wise, day-wise, USA         county-wise, and worldometer data.
  o	Produces visualizations for cumulative cases, active cases, deaths, and recoveries for a selected country.
  o	Includes functions to estimate SIR model parameters on a per-country basis and generate a trajectory for the basic           reproduction number (R₀).
•	User Interaction:
  o	Users can select a country (for example, via a dropdown in the dashboard) to view country-specific plots.
  o	Functions such as plot_totals_for_country(country, start_date, end_date) generate visualizations showing cumulative         totals relative to the country's population.
  o	The function R0_trajectory_by_country(country) creates a time series of R₀ values for the chosen country.



Part 4: Data Wrangling
•⁠  ⁠What It Does:
  o	Processes an additional dataset (complete.csv) that contains detailed daily counts per country.
  o	Addresses missing values by applying manual interpolation and invariant-based corrections.
  o	Groups and aggregates data to ensure that cumulative counts are accurate.
•⁠  ⁠User Interaction:
  o	Users can choose a country to perform operations on
  o	The function plot_figures_country_complete(country, start_date, end_date) now provides plots of cumulative totals           (Confirmed, Active, Deaths, and Recovered) based on the cleaned data.
  o	Additional functions support detailed analysis at the county level (especially for the USA) via                               plot_figures_counties_complete(county).


Part 6: Version Control and Deployment
•	What It Does:
  o	Uses Git for version control with frequent commits and updates.
  o	Provides instructions for deploying the dashboard via the Streamlit Community Cloud.
  o	Ensures that the final repository is public and can be accessed by all team members and evaluators.
•	User Interaction:
  o	Developers contribute to the project by updating the GitHub repository and README file.
  o	Users can view the deployed dashboard online and verify the public accessibility of the GitHub repository.
  
Prerequisites
Ensure you have the following installed:
•	Python 3.7 or higher
•	Required libraries: 
  o	pandas
  o	numpy
  o	matplotlib
  o	statsmodels
  o	plotly
  o	streamlit

How to Run the Program
Running the Analysis Scripts
To generate figures and perform SIR model simulations:
1.	Open your terminal.
2.	Run the main Python file with the run_main flag: 
python your_script.py run_main
Replace your_script.py with the appropriate filename.

Running the Streamlit Dashboard
To launch the interactive dashboard:
1.	In your terminal, execute: 
    streamlit run your_script.py
2.	The dashboard will open in your default web browser.
3.	Use the sidebar to navigate between pages, select countries, and adjust the date range.
   
Project Structure
•	day_wise.csv: Time series data from January 22 to July 27, 2020.
•	complete.csv: Detailed daily counts per country, used after data wrangling.
•	covid_database.db: SQLite database with tables for country-wise, day-wise, USA county-wise, and worldometer data.
•	your_script.py: Main Python file containing data processing, visualization, SIR model simulation, and dashboard code.
•	README.md: This file, providing detailed project and usage information.





