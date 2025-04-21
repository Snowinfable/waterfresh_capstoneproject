# waterfresh_capstoneproject

This repository is related to the UMSI - MADS capstone project from Matthew Parent and Shiyi Song, analyzing the change in water levels in groundwater wells throughout the United States. The project analyzes current trends in groundwater-related issues facing the United States, and attempts to create a model the can predict future water level changes based a variety of water use and other environmental data.


### Below is a high level overview of the repository:
- project_code_data/ a folder containing datasets and notebooks necessary to produce the results from the report.
- requirements.txt: the software package requirements for running the code in this repository
- README.md: this file that explains how to use the github repository
- Data Access Statement

### How to use this repository
Follow the following steps to obtain the necessary data and run the notebooks to replicate the report.

# 1. Data Retrieval and upload
To reproduce the results from the following code you will need to download some data and run the notebooks in the project_code_data folder in a specific order. The four "data cleaning" files will require data to be uploaded to the project_code_data folder containing these notebooks (except for one exception, for which you will upload the data into a folder instide project_code_data). 


#### For the "Data Cleaning - Water Use" notebook:
You will need to access the county-level datasets for water use at this website: https://water.usgs.gov/watuse/data/. The 2015 data will be downloadable in CSV format. The 2000, 2005, and 2010 data will be in excel. You will need to convert these to CSV format to be able to use the notebook. To run the notebook, the four files should be:
- usco2000.csv
- usco2005.csv
- usco2010.csv
- usco2015v2.0.csv

#### For the "Data Cleaning - Water Level Trends" notebook:
You will need to download four files to run this notebook. You can access the files here: https://www.sciencebase.gov/catalog/item/650b31f8d34e823a02735c0b. The four files are:
- CA_stations_v2.0.csv
- NWIS_gwl_meta_v2.0.csv
- NGWMN_gwl_meta_v2.0.csv
- GW_trendsout_v2.0.csv

#### For the "Data Cleaning - Evapotranspiration" notebook:
You will need to upload GeoTIFF files to the 'monthly_ets' folder in the project_code_data folder. You can access the GeoTIFFS here: https://www.sciencebase.gov/catalog/item/64135576d34eb496d1ce3d2e. You will need to add all of the GeoTIFFs for every month in these two zipfiles: AET_2000_2009_monthly.zip and AET_2010_2018_monthly.zip. You will need to place the GeoTIFF files from these zipfiles in the 'monthly_ets' folder. The GeoTIFFs are in the form AET_year_month.tif.

#### For the "Data Cleaning - Climate" notebook:
The data is access through an API, so you do not need to download any data for this. Make sure to check the note in the notebook, as the name of the url for the API call is updated periodically (possibly monthly).

# 2. Running the data prep notebooks
After you have uploaded the data to the appropriate locations, you will then be able to run the notebook. First, you will want to run the the "Data Cleaning" notebooks. They can be run in any order, except you will need to run the "Data Cleaning - Water Level Trends" notebook and produce the file 'trends_clean.csv' before you run the "Data Cleaning - Evapotranspiration" notebook. 

After you have cleaned the data, the 'merge_data' folder should contain these four files (these files should already be placed in the folder for convenience, but running the data cleaning notebooks will produce them as well):
- trends_clean.csv
- water-use_cleaned_totals-removed.csv
- et_cleaned.csv
- climate_all_data_clean.csv

Once these files are in the 'merge_data' folder, you will then be able to run the 'Merge Datasets' notebook. This brings all of the input and target data together into one csv, which will be exported as 'final_without_totals_visuals.csv'.

# 3. Run the modeling and visualizations notebooks
Now you will be able to run two notebooks:
- Introductory Visualizations.ipynb
- Random Forest Regressor Model and Visuals.ipynb

These notebooks will produce the random forest regressor results and various visualizations seen in the report.







