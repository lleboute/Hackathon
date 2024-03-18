# ECB_Hackathon
This repository holds the codes and other key information that were developed during the ECB's Beat the Heat Climate Change Hackathon

[FT Article Shared Document](https://docs.google.com/document/d/12Q87xb-5Ltxgxft2vi7Th89enidNYnbr/edit?usp=sharing&ouid=113254072246071435657&rtpof=true&sd=true)

## Data
We used economical data combined with climate data stored on the AWS S3.
At the beggining, we were provided just data until year 2018. Later, for finetuning purposes we were provided data until 2022.
Aggregation and merge of all data are in benchmark.ipynb

### Economical data
For the economical data, we were provided just one dataset with granularity of region, sector and year.
Variables are GDP, gross value added, population, employment and geo characteristics
 Python notebook: Econ.ipynb
 
### Climate data
Climate data were richer. Below is list with python notebooks for them:
1. Soil Moisture Anomaly (SMA): SMA.ipynb
2. Low-Flow Index: Low_Flow.ipynb
3. Standardized Precipitation Index (SPI): SPI.ipynb 
4. Combine Heat and Dought indicator: HeatDrought.ipynb
5. Vegetation Productivity (fAPAR) (VIIRS): Fapar.ipynb) 
6. Heat waves: HeatWaveIndex.ipynb
7. Maximum Temperatures: maxTemp.ipynb

### Geographical regional data
NN_VAR represents the outcomes of two processes, including the identification of neighboring regions using geographical data (geopandas) at the NUTS-3 level for each region. Subsequently, the average value of VAR is computed for the neighboring regions within each sector and year
#### Graphical support files:
* Geopandas.ipynb
* Map_GVA.ipynb
* Map_Benchmark.ipynb
 
A series of saved image files (.png format) that provide visual representations of various data sets. These images are essential for illustrating geographical patterns and clusters within the data. The specific types of images included are as follows:

1.  **Fapar Average per Region (All Years)**: These images depict the average Fapar values across different regions over multiple years.
    
2.  **SPI 1M Average per Region (All Years)**: These images show the monthly average of the Standardized Precipitation Index (SPI) for each region, aggregated over all available years.
    
3.  **SMA_MEDIAN_stdev Average per Region**: These maps represent the average Standardized Median Absolute Deviation (SMA_MEDIAN_stdev) for each region, highlighting variability in the data.
    

#### Purpose of the Images

-   **Illustrative Use**: The primary purpose of these images is to serve as illustrative materials. They effectively demonstrate geographical clusters and patterns in the data, making them useful for presentations and discussions about the input data.

#### Additional Images

-   **Principal Components Analysis (PCA) of SPI 1M Data**: The collection also includes two images representing the first two principal components of the aggregated SPI 1M data over all years. These images:
    -   Showcase clear geographical clustering.
    -   Account for 82% of the variance in the data, primarily driven by the first principal component.
    -   Although visually appealing, these images may require detailed explanation due to the complex nature of PCA.

## Processing
Data was cleaned in notebook BENCHMARK_clean.ipynb

## Modeling
Modeling files are:
* Fit_OLS.ipynb
* HistGradientBoostingRegressor.ipynb

These models take competing approaches to predicting the target variables. The first takes a more economietric approach using a linear regression model, the latter relies on a Machine Learning model to make predictions after carrying out hyperparameter tuning. These models were chosen 

## Notes on data
- Non EU countries eliminated. We only include EU27.
- Nuts3 data from non asinged regions (_zzz) are eliminated. 
