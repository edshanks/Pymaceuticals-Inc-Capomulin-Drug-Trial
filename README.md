<h2>Pymaceuticals-Inc-Capomulin-Drug-Trial</h2>
In this study, 249 mice who were identified with SCC tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens. The gathered data was then cleaned, analyzed, and visualized using Python with the help of Matplotlib, Pandas, and Scipy.
<h4>Data Sources</h4>
The data for this project comes from two CSV files. The first CSV contains the metadata of the mice that participated in the drug trial. The metadata includes a mouse ID, weight, sex, age in months, and the drug regimin used to treat the mouse.
<mouse_metadata>

The second CSV contains the results of the drug trial. The data is a time series which details the number of metastatic sites and tumor volume for a given mouse at a particular point in time. 
<study_results>

<h4>Data Preparation</h4>
First, the 2 CSV files were loaded into Python and merged on the mouse ID into a single dataframe titled 'merged_data'. 
<merged_data_raw>
  
The resulting dataframe was then checked for duplicate rows. This revealed that there were duplicate rows for mouse g989. All rows corresponding to mouse g989 were therefore dropped from the 'merged_data' dataframe. After dropping mouse g989 from the dataset, there were 248 mice included in the data.
<mouse_g989>

Next, the tumor volume data was summarized in terms of mean, median, variance, standard deviation, and standard error and stored in new dataframe called 'tumor_volume'.
<summary_stats>
<summary_stats_df>

<h4>Data Visualization</h4>
Using the original data and leaving out data for mouse g989, a bar graph showing the number of mice that were involved in each drug trial was created using Matplotlib.
<number_of_mice_tested>

A pie chart showing the sex of the mice in the trial was then generated using the original mouse metadata. 
<mice_sex>

In order to analyze the final results of the study, the 'merged_data' dataframe was altered such that only the final tumor volume measurement was included. This data was then stored in the 'max_time_data' data frame.
<final_timepoint>

The final tumor volumes for each mouse that underwent treatment with the drugs 'Capomulin', 'Ramicane', 'Infubinol', and 'Ceftamin' were then gathered from the 'max_time_data' dataframe and stored in 'tumor' dataframe.
<final_tumor_volume>
<final_tumor_volume_df>

In order to test for outliers in the tumor volume data in the 'tumor' dataframe, the upper and lower quartiles and the interquartile range were calculated. For the purposes of this analysis, an outlier is defined as any data point whose value is greater or less than the the upper or lower quartiles, respectively, by at least a factor of 1.5 times the interquartile range.
<IQR>
<outliers>

As shown in the screenshot above, only one outlier, belonging to the Infubinol dataset was found. This was confirmed by plotting the data from the 'tumor' dataframe in a box and whisker plot.
<box_whisker>

Next, mouse l509 was singled out in order to analyze the effects of a Capomulin treatment regime. 
<capo_treatment>

The 'merged_data' dataframe was then filtered for mice who underwent the Capomulin treatment regime. The mean tumor volume was then calculated for each mouse in the regime and stored in the 'cap2' dataframe. The aggreagated tumor volume was then plotted on a scatter plot.
<capo_scatter>
<capo_treatment_all>

<h4>Correlation Testing</h4>
