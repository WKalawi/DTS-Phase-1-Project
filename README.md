## DTS Phase 1 Project

**Author:** [Wallace Ouma](https://github.com/WKalawi)
***
## Business Understanding

**Overview**

This study sought to guide Microsoft's possible foray into original video content by studying current patterns in box office success. By using descriptive statistics and analyzing several online movie databases, we have identified three key areas that provide unique opportunities for recommendations: establishing strategic partnerships, improving content selection, and optimizing talent acquisition and recruiting.

**Business Problem**

Microsoft's new film studio, lacking competence in filmmaking, needs guidance about the most advantageous film genres for achieving maximum box office success. This investigation seeks to affect the studio's film choices by analyzing past box office statistics and examining genre patterns. Key metrics such as box office sales, return on investment (ROI), and ratings will assess the financial feasibility and audience response across various film genres.

**Areas of Focus**
The primary emphasis was on providing guidance for the choice of genre, budgets channels, and the selection of cast and crew members. The success was measuered through two key metrics: ROI (return on investment), calculated by dividing the movie's total gross by its budget, and the overall profitability of the movie. While these success indicators are closely associated, they are not entirely synonymous.

## Budgets

**Data prep & cleaning**

In the process of conducting the budgets analysis, a dataset sourced from TheNumbers, a platform dedicated to tracking box office revenue, was used. The dataset comprised 5,782 sample entries, encompassing details on production budgets, domestic and worldwide gross figures for various movies. To facilitate statistical analyses, the dataset's monetary columns, initially formatted as strings, were converted into integer types. 

Subsequently, this monetary data was leveraged to generate columns representing a movie's ROI, profitability status, and foreign gross. The ROI was calculated as a percentage: (worldwide gross / budget) * 100. Profitability status was classified as True if ROI > 100% and False if ROI <= 100%. Additionally, a foreign gross column was created by subtracting the domestic gross from the worldwide gross.

To add nuance to the analysis, an additional ROI column was introduced. Unlike its continuous counterpart, this categorical column featured ranges such as "142%–214%". To ensure the robustness of the dataset, outliers that could potentially distort results were addressed. Employing the same criterion as box plots, outliers were identified based on being greater than the 75th percentile plus the interquartile range (IQR) or less than the 25th percentile minus the IQR. To maintain data integrity and avoid misleading recommendations, identified outliers in the ROI, budget, and worldwide gross columns were treated as null values and subsequently removed from the dataset.

**Analyses and recommendations**

In this section, three distinct analyses were conducted, each accompanied by corresponding visualizations. The first analysis delved into the percentage distribution of total earnings, both domestically and globally, across various ROI levels. Subsequent examinations replicated this approach for unprofitable movies and profitable ones. The consistent trend observed was the prevalence of domestic budgets over foreign, with its dominance diminishing as movie success or budget increased. Notably, unprofitable movies exhibited a tendency to neglect foreign budgets even as their budget increased, a trend not mirrored in profitable movies.

The recommendation stemming from these analyses suggests that Microsoft should place a heavier emphasis on domestic budgets while simultaneously avoiding the neglect of foreign budgets. This strategic approach assists in the wise allocation of resources, a prudent practice applicable to any entity. Aligning budgets efforts with the observed patterns in successful movies can optimize resource utilization, potentially enhancing overall marketing effectiveness for Microsoft.

## Genre

**Data Prep and Cleaning:**

For the genre analysis, two datasets were utilized: one formed in the Budgets section and another from IMDB, a comprehensive platform collecting data on various content types. The latter dataset, part of a larger SQLite database, specifically contained information on movie genres. To merge these datasets into a cohesive dataframe, a SQL query was employed. Post-merging, the next step involved eliminating any duplicate entries, characterized by identical names and genres but conflicting monetary data.

**Analyses and Recommendations:**

Three analyses were conducted, each accompanied by visualizations. Initially, the researcher explored correlations between different genres and profitability status, a binary variable indicating a movie's financial success. However, no discernible patterns emerged from this analysis. The second analysis focused on ROI for each genre, while the third delved into the average profitability status for each genre. These latter two analyses provided insights into genres deemed highly reliable, those considered less reliable, and a more extensive list of genres with no apparent defects or superiorities.

The recommendation arising from these analyses advises Microsoft to steer clear of unreliable genres and concentrate efforts on reliable or average genres. This strategic guidance aims to safeguard Microsoft from potentially unfavorable financial decisions, aligning with the prudent practice of making financially sound choices. By avoiding genres with less favorable outcomes and emphasizing those with proven reliability, Microsoft can enhance the likelihood of success in their content endeavors.

## Cast

**Data Prep and Cleaning:**

For the cast analysis, three datasets were utilized: one formed in the Genre section and two additional datasets from IMDB containing information on names, professions, and movie participation of individuals. A SQL query was employed to join all three tables into a consolidated dataset.

**Analyses and Recommendations:**

The analysis in this section is notably intricate compared to previous sections. The core question addressed is the influence of cast members on a movie's success. To answer this question, a multistep process was undertaken:

1. **Selection of People and Movies:** Groups of people with different success levels in a certain time were selected. Movies involving these people in a later time were also identified.

2. **Correlation Determination:** The correlation between the success of actors and the subsequent success of movies they were involved in was calculated. This process was repeated for different measures of success and various time periods.

3. **Aggregation:** The data was aggregated to derive single success scores for each profession.

The results of this comprehensive analysis revealed a clear superiority of off-screen crew over on-screen crew in terms of influencing a movie's success.

**Recommendations:**

The recommendation stemming from this analysis is for Microsoft to prioritize off-screen crew over on-screen crew. Specifically, emphasis is placed on making the director the most crucial hire. This strategic guidance is intended to help Microsoft prioritize the most influential cast members, thereby improving the chances of creating a successful movie. By understanding the significant impact of off-screen roles, particularly the director, Microsoft can optimize their hiring decisions and enhance the overall quality and success potential of their movie projects.


## Repository Contents

* `Dataset`: folder containing the zipped im.db and csv data files

* `PhaseOneProject.ipynb`: project notebook containing all data imports, cleanup, analyses, and visualizations

* `PhaseOneProject.pdf`: PDF version of the notebook

* `presentation.key:` the original presentation created with the application Keynote, meant for live use

* `presentation.pdf`: a PDF version of my presentation for this project

* `Images`: a folder with all relevant visualizations from the notebook