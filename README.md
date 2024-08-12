# Health-Monitoring-and-Analysis-using-Python
Health Monitoring and Analysis refers to the systematic use of health data to track and evaluate the health status of individuals or populations over time. It contains a range of activities from real-time physiological data collection (like heart rate, blood pressure, and temperature) to the analysis of more complex health records.
The given dataset contains several health-related metrics for different patients, organized in the following columns:

PatientID: Numerical identifier for the patient.
Age: Age of the patient in years.
Gender: Gender of the patient.
HeartRate: Heart rate in beats per minute.
BloodPressure: Blood pressure readings, formatted inconsistently.
RespiratoryRate: Respiratory rate in breaths per minute.
BodyTemperature: Body temperature in Fahrenheit.
ActivityLevel: Activity level at the time of the measurement.
OxygenSaturation: Oxygen saturation percentage.
SleepQuality: Quality of sleep reported by the patient.
StressLevel: Reported level of stress.
Timestamp: Date and time of the measurement.
The dataset includes health metrics from 500 individuals, featuring variables such as age, gender, heart rate, blood pressure, respiratory rate, body temperature, and oxygen saturation, recorded over a specific period. These variables provide a comprehensive snapshot of each patient’s health status, which is crucial for monitoring and managing various health conditions.

Problem:
Traditional health monitoring systems often categorize patient health status using rigid, predefined thresholds that may not capture the nuanced variations across a diverse patient population. This can lead to oversimplified assessments and potentially overlook subtle yet critical patterns in health data. The challenge is to develop a more dynamic and responsive approach that utilizes unsupervised learning to identify natural groupings within health data, facilitating personalized and precise health management.

Expected Outcomes:
Identified Clusters: Distinct patient groups based on health metrics, each with unique characteristics that provide insight into their specific health needs.
Personalized Health Insights: Enhanced understanding of patient health requirements and risks, enabling tailored intervention strategies.
Improved Health Monitoring: Recommendations for targeted monitoring and intervention strategies that cater to the specific needs of each cluster, leading to more effective health management and better patient outcomes.

Firstly, imported the necessary Python libraries and the dataset, checked whether the data contains any null values or not, the data contains null values in body temperature and oxygen saturation columns. For simplicity, I filled the null values using the median value.

Next, examined summary statistics and the distribution of the numerical health metrics (Age, Heart Rate, Respiratory Rate, Body Temperature, and Oxygen Saturation). It helped to understand the typical values and the spread of the data.  Also included some visualizations to better understand these distributions.

Next, the gender distribution in the data and the correlation between the numerical columns in the dataset is plotted. The pie chart indicates a nearly even split between male and female subjects in the dataset, with males comprising a slight majority at 51.2%. The correlation matrix shows no strong correlations between the variables, as all the values are close to zero. Specifically, none of the health metrics (Age, Heart Rate, Respiratory Rate, Body Temperature, and Oxygen Saturation) display a strong positive or negative linear relationship with one another in this particular dataset. It suggests that, for this group of individuals, changes in one metric are not strongly associated with changes in the others.

Next, the heart rate by activity level is plotted.It shows that the median heart rate increases from resting to walking, which is expected as physical activity increases. However, the median heart rate does not significantly increase further during running compared to walking, which is unusual since we would expect a higher median heart rate for a more strenuous activity. Additionally, there is considerable overlap in the interquartile ranges between walking and running, suggesting similar variability in heart rates for these activities within the sampled population. The presence of outliers in the resting category indicates that some individuals have resting heart rates that are much higher than the typical range for the rest of the group.
Next, the distribution of blood pressure levels and some health metrics by gender is plotted. The systolic blood pressure, represented in blue, shows a more spread-out distribution with peaks suggesting common readings around 120 mmHg and 140 mmHg. The diastolic blood pressure, in red, appears to have a narrower distribution, with a significant peak around 80 mmHg. The spread of systolic values is broader than the diastolic ones, which is typical as systolic pressure tends to vary more with factors like activity level and stress. This distribution is consistent with general population trends where a systolic reading of around 120 mmHg and a diastolic reading of around 80 mmHg are considered normal.

For heart rate, both males and females show similar median values with a relatively similar interquartile range, indicating no significant difference in heart rate between genders within this dataset. In terms of oxygen saturation, again, both genders exhibit nearly identical medians and interquartile ranges, suggesting that oxygen saturation does not differ notably between males and females in this sample. There are a few outliers in oxygen saturation for both genders, indicating a few individuals with lower than typical values, but these do not seem to affect the overall distribution significantly.

Next, heart rate and oxygen saturation by sleep quality and stress levels are analysed. Heart rate appears relatively consistent across different levels of sleep quality and stress, with a slight increase in variation for those reporting poor sleep. Oxygen saturation shows a minimal decrease in median values from excellent to poor sleep quality, with some outliers indicating lower saturation for excellent and good sleep. When correlated with stress levels, oxygen saturation remains largely unchanged. Overall, while there are outliers, the central tendencies suggest that neither heart rate nor oxygen saturation is greatly affected by sleep quality or stress level within this dataset.

Next, the respiratory rate and body temperature by activity levels are analysed. The respiratory rate tends to increase with activity level, as indicated by higher median rates for walking and running compared to resting. It aligns with physiological responses to exercise, where the breathing rate increases to meet oxygen demands. For body temperature, there is a slight upward trend from resting to running, which is consistent with the body heating up during physical exertion. There are outliers in body temperature at the resting and running levels, suggesting some individuals have temperatures outside the typical range for these activities. Overall, the trends observed are in line with expected physiological responses to varying levels of activity.

The data is not so complicated enough that we need to use a clustering algorithm to group patients. So, patients are grouped based on:

Age Group: Young, Middle-aged, Senior
Blood Pressure Category: Normal, Elevated, Hypertension Stage 1, Hypertension Stage 2
Heart Rate Category: Low, Normal, High
Oxygen Saturation Category: Normal, Low

Observation:
Distribution of Age Groups: The count plot shows that the ‘Senior’ category has the highest count, followed by the ‘Young’ and ‘Middle-aged’ categories. It suggests that seniors are the largest age group in this dataset.
Distribution of Blood Pressure Categories: The majority of the dataset falls under ‘Normal’ blood pressure, with fewer instances in the ‘Elevated’ and ‘Hypertension Stage 1’. ‘Hypertension Stage 2’ has the lowest count, indicating that severe hypertension is less common among the participants.
Distribution of Heart Rate Categories: Most individuals have a ‘Normal’ heart rate, with very few falling into the ‘Low’ or ‘High’ categories. It indicates that most individuals in this dataset have a heart rate that falls within the expected range.
Distribution of Oxygen Saturation Categories: Almost everyone has ‘Normal’ oxygen saturation levels, with very few instances of ‘Low’ saturation. It suggests that oxygen deprivation is not a common issue in this group.

Summary
So, Health Monitoring and Analysis contains a range of activities from real-time physiological data collection (like heart rate, blood pressure, and temperature) to the analysis of more complex health records (including patient history, lifestyle choices, and genetic information).


