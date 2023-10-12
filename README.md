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
