**monthly_power_generation_analysis** project analyses monthly electricity generated data for a given country, source of power and for a given month and date range in the format `YYYY-MM`.

This application is integrated with **Ember Energy** API. It retrieves data from, transforms the data into structured tabular format using `Pandas` Library, filters the selected power source, performs statistical analysis, generates visualizations and exports yearly results into CSV files.

Further this project was extended to support the analyses of CO2 emission for a specified source of power. For better understanding both the dataframes, power and emissions, have been merged for better understanding.

### Architecture Flow
1. **User Input**
   - Start Date (YYYY-MM)
   - End Date (YYYY-MM)
   - Country Code (3 letter format)
   - Source of power (Coal, Wind, Solar, Nuclear, Gas etc.)

2. **Data Ingestion**
   - Requests library of python sends HTTP get request to the Ember Energy monthly electricity-generation API.
   - API response is JSON.
   - `data` portion of the JSON response is converted into Pandas DataFrame.

3. **Data Processing**
   - Power generated Dataset contains the following attributes:
     - `entity`
     - `entity_code`
     - `date`
     - `series`
     - `generation_twh`
   - CO2 emissions Dataset contains the following attributes:
     - `entity`
     - `entity_code`
     - `date`
     - `series`
     - `emissions_mtco2`

4. **Exploratory Analysis**
   - Monthly generation is analyzed over time.
   - Data is grouped conceptually by year for year-wise comparison.
   - Following statistical measures are employed for each year:
       - Mean
       - Median
       - Variance
       - Standard Deviation
       - Quartile Ranges

5. **Output**
   - Filtered yearly datasets are exported to CSV files.
   - Further optional Azure Blob storage upload workflow is provided.

### Architecture Flow Diagram
<img width="1372" height="372" alt="power_analytics_pipeline" src="https://github.com/user-attachments/assets/5e63e65c-f6c1-43fe-81ac-236c49ac02cc" />


### Visualization
1. **Power Generation Trend Year-on-Year Visualized**
   
   <img width="1214" height="435" alt="image" src="https://github.com/user-attachments/assets/0075bdfa-0bee-4489-bab9-3f4f5547f174" />

3. **Month-on-Month Power Generation Visualized**
   
   <img width="1226" height="467" alt="image" src="https://github.com/user-attachments/assets/239b3184-122b-4926-b6eb-4846048721f6" />


