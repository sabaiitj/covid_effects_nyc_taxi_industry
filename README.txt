# NYC Taxi Data README:

## DESCRIPTION
This packaged contains three main components: this readme, the processing python notebook, and the dashboard package. The README contains the instructions to extract the package, open and use the dashboard, and instructions to set up and run the python code on Google DataProc/Google Cloud Storage/Google BigQuery.

The Dashboard comes with all data included, so the user does not need to import any new CSVs or Data Sources. Note, however, that examining the actual data row by row may require authentication with permissions that the user does not possess. Thus, if the user wishes to see the background data in detail, they can run the DataProc cluster and examine the CSVs in the backend. Because the data for 2019 and 2020 NYC taxi trips already exists in Google BigQuery as a part of Google's public data source, the code is set to pull the data from BigQuery into Google DataProc cluster for processing. The instructions in this readme should provide enough information; only two lines containing a project name and bucket name need to be changed in order to make the code work.

The Python package can be loaded into DataProc. Detailed below are two lines (the project name and the bucket name) that the user needs to change to run the code. The code is extremely well documented and in an object-oriented format. This should give more than enough information to get going on new extensions, should an end user wish to do so.

## INSTALLATION AND EXECUTION (Per component)

## Component 1: Extraction

1. Unzip the package of software containing: 
	The Python notebook used to create and initialize CSVs of data to be used in the dashboard
	The Tableau dashboard workbook


## Component 2: Dashboard

1. Double click on the provided tableau dashboard to open it. 
2. The open tab should be "Covid Impact on the NYC Yellow Taxi Industry. In the upper right corner, you can filter via borough. This uses data from component 3 below if you want to see how it is generated. It uses economic/trip forecasts on cleaned data to estimate economic impact.
3. The other main important tab is NYC Yellow Taxi Zone Connectivity. In this visualization, you can see a more granular view of taxi trip differences between 2019 and 2020. You can change the zone to view, as well as whether that zone is the origin or destination of the trip.
4. The other two dashboarding tabs contain a wider view of the second tab. That is, the difference with and without inner zone travel. Feel free to examine if you would like a more detailed view.
5. For some examples of behavior, try selecting zone 170 (Murray Hill). Try selecting it as both origin and destination.
6. For some interesting economic results, try selecting Manhattan as a Borough, followed by the Bronx. Based on locations of interest in the Bronx, why might the behavior be different?

## Component 3: Data Preprocessing

Note: The code is extremely well documented in the notebook, using docstrings. Any user should be able to pick this notebook up and begin work with it.

1. Create a project on Google Cloud Console. Note the name (typically something like adjective-noun-numbers). 
2. Click on "APIs and Services"
3. Search in the top bar "Data Proc". Select the option that contains a description with Hadoop.
4. Create a cluster with as many workers as you want. Make sure to select Jupyter under "Optional Components".
5. If cluster creation fails due to lack of an API, enable the API for your account.
6. Start the cluster.
7. Select tab for "Web Interfaces" and select "Jupyter Notebook". Also select "Component Gateway".
8. Select the folder "GCS" and upload the notebook from the zip file.
9. Open a new tab. Go to your project in Google Cloud Console and search for Google Cloud Storage. 
10. Create a bucket with a new name. Make a note of the name.
11. In the Jupyter notebook, underneath the name == __main__ cell, change the project and bucket names to the proper names.
12. Run the code. Depending on machines, this may take over an hour. 
13. Check your GCS bucket. The data should be there. Examine for background data found in dashboard.




