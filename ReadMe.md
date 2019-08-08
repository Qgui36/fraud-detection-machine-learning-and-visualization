# Final Project - DC Properties<br>
## Presented by: Hank, Lauren, Diego, Steve, Qin, Anna<br>
### Wednesday, June 3rd, 2019 

<img  src="https://www.tripsavvy.com/thmb/OrqFLS2jHbFlmOsOBLbvmUsx_IU=/960x0/filters:no_upscale():max_bytes(150000):strip_icc()/architecture-lenfant-DC-564109589-crop-5b454aec46e0fb005bd49251.jpg"  alt="Final Project - DC Properties"  />

### Requirements
* Find a problem worth solving, analyzing, or visualizing. The key is to show the **value** of what you've learned.
* Use ML in the context of technologies learned.
* You must use: Scikit-Learn and/or another machine learning library.

You must use at least 3 of the below:
* Pandas
* Matplotlib
* HTML/CSS
* JavaScript libraries
* Plotly
* D3
* Leaflet
* SQL Database
* NoSQL Database
* Tableau

### Data Source - Kaggle D.C. Residental Properties Dataset
Washington, D.C. is the capital of the United States. Washington's population is approaching 700,000 people, and has been growing since 2000 following a half-century of population decline. The city is highly segregated and features a high cost of living. In 2017, the average price of a single family home in the district was $649,000. This dataset provides insight on the housing stock of the district. <br>

Link: [DC Residental Properties](https://www.kaggle.com/christophercorrea/dc-residential-properties)

#### Data Definitions

![alt text](https://github.com/grlofgd/Images/blob/master/Data_Dictionary.jpg "Data Dictionary")


### Prepping the Data 
The feature variables for each house observation include quantitative and qualitative (nominal and ordinal) values. We will be using these variables to predict the price of houses using Regression techniques. <br>

1.	Went through the data together and determined how to clean the data (see above)
2.	Pulled in CSV into Python and removed Condos & Unqualified rows
3.	Dropped columns 
    * Visualization DF: NUM_UNITS, AYB, YR_RMDL, SALE_NUM, BLDG_NUM, GIS_LAST_MOD_DTTM, CMPLX_NUM, LIVING_GBA, NATIONALGRID, SOURCE, QUALIFIED
    * Machine Learning DF: ['NUM_UNITS', 'AYB', 'YR_RMDL','SALE_NUM', 'BLDG_NUM', 'STYLE', 'GIS_LAST_MOD_DTTM', 'CMPLX_NUM', 'LIVING_GBA', 'FULLADDRESS', 'CITY', 'STATE','NATIONALGRID','ASSESSMENT_NBHD', 'ASSESSMENT_SUBNBHD',  'CENSUS_TRACT', 'CENSUS_BLOCK', 'WARD', 'SQUARE', 'X', 'Y' ,’SOURCE’,’QUALIFIED’]
4.	Remove Rows with SALEDATE older than 5 years
5.	Remove all NULLs
6.	Generate dummy variables for columns 'HEAT', 'AC','STRUCT', 'EXTWALL', 'ROOF', 'INTWALL', 'USECODE ', 'ZIPCODE ', ' QUADRANT '
7.	Generate ranks for columns ‘GRADE’, ‘CNDTN’
8.	Dropped additional columns as needed
9.	Understanding ‘USE CODE’ 
    *	011 Residential-Row-Single-Family (CLASS 1)
    *	012 Residential-Detached-Single-Fa (CLASS 1)
    *	013 Residential-Semi-Detached-Sing (CLASS 1)
    *	015 Residential-Mixed Use (CLASS 1 or 2)
    *	019 Residential-Single-Family-Misc (CLASS 1) 
    *	023 Residential Flats-Less than 5 (CLASS 1)
    *	024 Residential-Conversions-Less t (CLASS 1 )
    *	039 Residential-Transient, Misc (CLASS 2)

### Machine Learning

1.	Principal Component Analysis (PCA) with y as PRICE
2.	StandardScaler to standardize the dataset’s features into unit scale 
3.	Train the data & reshape the price values 
4.	Fit on the training set and transform on the training and test set

### Visualizations

Generated dashboard [Tableau](https://public.tableau.com/profile/anna5120#!/vizhome/Residence/Dashboard1?publish=yes "DC Properties") to allow an interactive viz for the user to select a residence based on their search criteria 