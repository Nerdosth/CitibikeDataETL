# Citibike Data Preparation for Tableau

This code is used to prepare Citibike trip data from January 2019 to December 2022 for visualization in Tableau. The original data is in separate CSV files for each month, and the code reads, cleans, and combines the data to make it suitable for Tableau.

## Steps

1. Read CSV files from 2019-2022 and concatenate them into two separate dataframes, `df` and `df1`. The data inputs were changed after January 2021, so each dataframe will need to be manipulated before merging them together.
2. Reduce the dataframes to the necessary columns, and rename them for consistency and personal preference.
3. Concatenate the two dataframes together into a single dataframe, `df2`.
4. Convert the `ride_time_start` and `ride_time_end` columns from objects to datetime.
5. Standardize the `usertype` values to 'Subscriber' and 'Customer'.
6. Remove rows with missing coordinates and station locations.
7. Calculate the ride time in minutes for each trip.
8. Remove outliers that would skew the ride time data.
9. Add a `trip_count` helper column for use in Tableau.
10. Create a sample CSV, `citibiketripsSample.csv`, for initial visualization in Tableau.
11. Save the final transformed dataframe as `citibiketrips19-22.csv` for importing into Tableau.

## Requirements

* pandas

## Usage

Run the script to generate the cleaned and transformed dataset for importing into Tableau. The script will produce two CSV files:

* `citibiketripsSample.csv`: A sample dataset with the first 50,000 rows for faster visualization and development in Tableau.
* `citibiketrips19-22.csv`: The full dataset for creating the final visualizations in Tableau.
* After running the script and obtaining the two CSV files, `citibiketripsSample.csv` and `citibiketrips19-22.csv`, you can proceed with creating visualizations in Tableau.

### Importing Data in Tableau

1. Open Tableau and click on 'Connect to Data'.
2. Choose 'Text File' as the data source and navigate to the location of the CSV files.
3. First, select `citibiketripsSample.csv` to work with the sample dataset for faster visualization and development.
4. After creating the initial visuals using the sample data, replace the data source with the full dataset by selecting `citibiketrips19-22.csv`.


### Creating Visualizations in Tableau

With the cleaned and transformed data imported into Tableau, you can create various visualizations to gain insights into Citibike usage patterns. Some examples of visualizations can be found referencing the visualization I created here: 

[CitiBike Ridership 2019-2022 (Tableau Public)](https://public.tableau.com/authoring/CitiBikeRidership2019-2022/PandemicImpactsonCitiBikeRidership#1)
