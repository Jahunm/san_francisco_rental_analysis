# San Francisco Housing Rental Analysis

---

![San Francisco](Images/sanfranhomes.png)

## Table of Contents
1. [Calculate and plot the housing units per year.](#1-calculate-and-plot-the-housing-units-per-year)

2. [Calculate and plot the average prices per square foot.](#2-calculate-and-plot-the-average-sale-prices-per-square-foot)

3. [Compare the average prices by neighborhood.](#3-compare-the-average-sale-prices-by-neighborhood)

4. [Build an interactive neighborhood map.](#4-build-an-interactive-neighborhood-map)

5. [Compose your data story.](#5-compose-your-data-story)

---

## 1. [Calculate and plot the housing units per year.](#1-calculate-and-plot-the-housing-units-per-year)

1. Use the `groupby` function to group the data by year. Aggregate the results by the `mean` of the groups.
2. Use the `hvplot` function to plot the `housing_units_by_year` DataFrame as a bar chart. Make the x-axis represent the `year` and the y-axis represent the `housing_units`.
3. Style and format the line plot to ensure a professionally styled visualization.
4. Note that your resulting plot should appear similar to the following image:
5. Answer the following question:

    ![](Images/housing_units_by_year.png)

    * What’s the overall trend in housing units over the period that you’re analyzing?
      * **Answer:** The units of houses has increased steadily from 2010 - 2016
      
    
## 2. [Calculate and plot the average prices per square foot.](#2-calculate-and-plot-the-average-sale-prices-per-square-foot)

1. Group the data by year, and then average the results. What’s the lowest gross rent that’s reported for the years that the DataFrame includes?
2. Create a new DataFrame named `prices_square_foot_by_year` by filtering out the “housing_units” column. The new DataFrame should include the averages per year for only the sale price per square foot and the gross rent.
3. Use hvPlot to plot the `prices_square_foot_by_year` DataFrame as a line plot.
    >This single plot will include lines for both `sale_price_sqr_foot` and `gross_rent`.
4. Style and format the line plot to ensure a professionally styled visualization.
5. Note that your resulting plot should appear similar to the following image:
6. Use both the `prices_square_foot_by_year` DataFrame and interactive plots to answer the following questions:

    **Question:** Did any year experience a drop in the average sale price per square foot compared to the previous year?

    ![](Images/price_vs_rent.png)

**Answer:** Yes, the price per square foot dropped an average of $28 per square foot in 2010 to 2011.

   **Question:** If so, did the gross rent increase or decrease during that year?

**Answer:** The average gross rent increased over $300 a month from 2010 to 2011. Even though the price per square foot droppped.
        
        
        
## 3. [Compare the average prices by neighborhood.](#3-compare-the-average-sale-prices-by-neighborhood)

1. Create a new DataFrame that groups the original DataFrame by year and neighborhood. Aggregate the results by the `mean` of the groups.
2. Filter out the “housing_units” column to create a DataFrame that includes only the `sale_price_sqr_foot` and `gross_rent` averages per year.
3. Create an interactive line plot with hvPlot that visualizes both `sale_price_sqr_foot` and `gross_rent`. Set the x-axis parameter to the year (`x="year"`). Use the `groupby` parameter to create an interactive widget for `neighborhood`.
4. Style and format the line plot to ensure a professionally styled visualization.
5. Note that your resulting plot should appear similar to the following image:
6. Use the interactive visualization to answer the following question:

    ![](Images/price-by-hood.png)
    
     **Question:** For the Anza Vista neighborhood, is the average sale price per square foot for 2016 more or less than the price that’s listed for 2012? 

    **Answer:** It has droppped in 2016 when compared to 2012.
    
    
## 4. [Build an interactive neighborhood map.](#4-build-an-interactive-neighborhood-map)

1. Read the `neighborhood_coordinates.csv` file from the `Resources` folder into the notebook, and create a DataFrame named `neighborhood_locations_df`. Be sure to set the `index_col` of the DataFrame as “Neighborhood”.
2. Using the original `sfo_data_df` Dataframe, create a DataFrame named `all_neighborhood_info_df` that groups the data by neighborhood. Aggregate the results by the `mean` of the group.
3. Review the two code cells that concatenate the `neighborhood_locations_df` DataFrame with the `all_neighborhood_info_df` DataFrame. Note that the first cell uses the [Pandas concat function] to create a DataFrame named `all_neighborhoods_df`. The second cell cleans the data and sets the “Neighborhood” column. Be sure to run these cells to create the `all_neighborhoods_df` DataFrame, which you’ll need to create the geospatial visualization.
4. Using hvPlot with GeoViews enabled, create a `points` plot for the `all_neighborhoods_df` DataFrame:
5. Use the interactive map to answer the following question:

    ![](Images/6-4-geoviews-plot.png)

   **Question:** Which neighborhood has the highest gross rent, and which has the highest sale price per square foot?

    **Answer:** Merced Heights had the highest gross rent and the most expensive neighborhood to purchase per square foot was Union Square District. The darker the color on the Geoviews plot shows which areas have the highest rent.

## 5. [Compose your data story.](#5-compose-your-data-story)

* Based on the visualizations that you created, answer the following questions:
    **Question:**  How does the trend in rental income growth compare to the trend in sales prices? Does this same trend hold true for all the neighborhoods across San Francisco?

    **Answer:** The growth trend of the average gross rent is extrodinary and has grown much over the years. The rate at which home prices, while has increased, it doesn't compare to the growth of the rent.
    
    **Question:** What insights can you share with your company about the potential one-click, buy-and-rent strategy that they're pursuing? Do neighborhoods exist that you would suggest for investment, and why?

    **Answer:** This analysis shows that it is much more profitable to buy the homes that are in less expensive neighborhoods. The ability to get a higher ROI is more substantial than the homes in more expensive neighborhoods.  
    
    ![](Images/goldengate.jpeg)
    
    
**File:** [San Fransisco Real Estate Market Analysis](san_francisco_housing.ipynb)    
