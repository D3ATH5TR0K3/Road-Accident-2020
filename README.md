# Road-Accident-2020
---
title: "Analysis of Road Accident Data"
author: "[Your Name]"
date: "`r Sys.Date()`"
output: html_document
---

## Overview
This project analyzes road accident data to identify patterns, trends, and critical factors influencing accident outcomes. The analysis includes data cleaning, visualization, and statistical summaries.

## Dataset
The dataset contains information about road accidents, categorized by:
- **Cause Categories**: Traffic Control, Junction, Traffic Violation, Road Features, Impacting Vehicle/Object, Weather, and others.
- **Cause Subcategories**: Specific details like Stop Sign, Roundabout Junction, etc.
- **Outcomes**: Persons Killed, Greviously Injured, Minor Injury, Total Injured, Total Number of Accidents.

## Key Features
1. **Dynamic Plot Generation**:
   - A function (`plot_func`) generates plots for combinations of causes and outcomes.
   - Uses ggplot2 for visualizations.

2. **Combinatorial Analysis**:
   - Plots are created for all combinations of cause categories and outcomes using the `expand.grid()` function.
   - Insights into relationships between causes and outcomes.

3. **Top Causes Identification**:
   - Modifies the analysis to focus on numerical summaries rather than visualizations.
   - Identifies top causes and subcauses for deaths, grievous injuries, and minor injuries.

## How to Run the Analysis
1. Install the required libraries:
   ```r
   install.packages(c("ggplot2", "dplyr"))
   ```

2. Load the dataset into R:
   ```r
   accident_data <- read.csv("path_to_your_dataset.csv")
   ```

3. Execute the `.Rmd` file in RStudio to generate visualizations and summaries.

4. To save all generated plots:
   - Use the `plots` list created in the script.
   - Save each plot using `ggsave()`.

   Example:
   ```r
   for (i in seq_along(plots)) {
     ggsave(filename = paste0("plots/plot_", i, ".png"), plot = plots[[i]], width = 6, height = 4)
   }
   ```

## Results
### Visual Insights
- Visualizations reveal how different causes and subcategories affect accident outcomes.
- For example:
  - Stop Signs are a significant factor in fatal accidents.
  - Traffic violations, especially signal violations, contribute to minor injuries.

### Numerical Summaries
The analysis identifies the top cause and subcause for each outcome:
- **Most Deaths**: Traffic Control (Stop Sign).
- **Most Grievous Injuries**: Junction (Roundabout).
- **Most Minor Injuries**: Traffic Violation (Signal Violation).

## Technologies Used
- **R Programming**: Data manipulation and visualization.
- **Libraries**: ggplot2, dplyr.
- **Markdown**: Documentation.

## Usage
- Modify the dataset path in the script as needed.
- Use the `plot_func()` to generate additional plots for custom analyses.
- Extend the numerical summary code to include other outcomes.

## Acknowledgments
- Data Source: [Provide dataset source]
- Libraries: ggplot2, dplyr.
- Color Scheme: Frontiers color palette.

---
For further queries or contributions, feel free to raise an issue or submit a pull request on GitHub!
