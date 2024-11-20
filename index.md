
# License Dataset Visualisations
*Submitted By Ruchita Alate (ralate2@illinois.edu)*


## Visualization 1: License types across different States

<!-- Embed the JSON chart for License types across different States -->
<div id="vis1"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  // Load the JSON specification for Visualization 1
  vegaEmbed('#vis1', 'bar_chart.json').catch(console.error);
</script>

**Writeup:**

### **1. Description**  
This bar chart visualizes the distribution of license types across different states. It displays the number of licenses for each type, where the height of each bar represents the frequency of a particular license type within the selected state. By providing a breakdown of license types, the chart helps to understand the prevalence of different types of licenses across states, offering insight into which license types are more common in the chosen state.

### **2. Encoding Types**  
- **X (Quantitative)**: The `count(id)` variable is used to encode the number of licenses for each license type. The height of each bar represents the number of licenses for that specific type.
- **Y (Ordinal)**: The `License Type` variable is encoded on the y-axis, sorted by the number of licenses in descending order to highlight the most frequent license types at the top.
- **Color**: Categorical encoding (`License Type`) is used to color the bars by license type, visually distinguishing between the different license types.
- **Tooltip**: Displays detailed information on the `License Type` and the corresponding count of licenses when hovering over each bar.

### **3. Color Scheme**  
A categorical color scheme is applied to differentiate between the different license types. This color differentiation enhances clarity, making it easier for viewers to distinguish between each type of license. The colors are automatically assigned by Altair, ensuring consistent and clear visual communication.

### **4. Data Transformations**  
The data is filtered based on the selected state, allowing users to view the license type distribution for a specific state. The data is aggregated by `License Type` and the count of licenses (`count(id)`) is calculated to represent the number of licenses for each type. This transformation helps to focus on the specific license type distribution within the state, ensuring that the data is aggregated and presented accurately.

### **5. Interactivity**  
The bar chart includes an interactive dropdown menu (`state_selection`) that allows users to select a state. This interactivity enables users to dynamically filter the data and examine the license type distribution for any specific state. The dropdown allows for a smooth and flexible exploration of the data.

### **6. Benefits of Interactivity**  
The interactivity of the bar chart enhances its usefulness by allowing users to filter the data based on the selected state. By choosing different states, users can easily compare the license type distribution across various regions. This interaction makes the visualization more personalized and relevant to the user's specific interests, improving data exploration and insight extraction. It also allows for a clearer focus on the license types that are most common in each state, providing a better understanding of regional differences in license distributions.


## Visualization 2 : Top 5 License Status Distribution by Cities
<!-- Embed the JSON chart for Top 5 License Status Distribution by Cities -->
<div id="vis2"></div>

<script>
  // Load the JSON specification for Visualization 2
  vegaEmbed('#vis2', 'pie_chart.json').catch(console.error);
</script>

**Writeup:**

### **1. Description**  
This pie chart visualizes the distribution of the top 5 most frequent license statuses within cities that have at least 5 distinct license types. The chart shows the proportion of each license status within the selected city, with the size of each segment proportional to the number of licenses with that particular status. By focusing on cities with a minimum of 5 license types, this visualization allows users to explore the most common license statuses in more diverse cities with a richer variety of license types.

### **2. Encoding Types**  
- **Theta (Angle)**: Quantitative encoding (`count_id`) represents the number of licenses with each status, determining the size of the pie segments.
- **Color**: Categorical encoding (`License Status`) distinguishes between different license statuses, helping to visually separate the statuses for easier interpretation.
- **Tooltip**: Displays detailed information on each license status and the associated count when hovering over the segments.

### **3. Color Scheme**  
A categorical color scheme is applied to differentiate the license statuses. This ensures that each license status is clearly distinguishable from others, enhancing the visual clarity of the chart. The colors are automatically assigned by Altair, ensuring consistent design and easy differentiation between the statuses.

### **4. Data Transformations**  
The data is filtered to include only those cities that have at least 5 distinct license types (`filtered_data`). It is then aggregated by `License Status` and `City`, with the `count(id)` computed to show the total number of licenses for each status within the city. The data is then ranked by the count of licenses in descending order, and only the top 5 license statuses for each city are displayed. This transformation allows the focus to be on the most significant license statuses while filtering out cities with fewer types of licenses.

### **5. Interactivity**  
The pie chart includes an interactive radio button feature (`city_selection`), enabling users to select a city from the list. This allows users to explore the top 5 license statuses for different cities, making the data exploration more dynamic and interactive.

### **6. Benefits of Interactivity**  
Interactivity enhances the usability of the pie chart by allowing users to select a city and view its top 5 license status distribution. This gives users a tailored, more in-depth view of the data, enabling them to focus on specific cities of interest. The radio button selection makes it easier to choose cities from the list without overwhelming the user with too many options at once. Overall, this interaction improves the accessibility of the data and makes the visualization more engaging and customizable.


#### General Data Cleaning Practices Implemented for the Visualizations: 
In the preprocessing workflow, the dataset is first read from a URL, and then columns with more than 90% missing values are dropped. Missing values in the 'Middle' column are filled with "N/A" to maintain data integrity. Rows with missing critical data, such as 'License Number', 'First Name', 'Last Name', 'Effective Date', and others, are dropped. After handling missing values, the dataset's dimensionality is updated, and date columns (such as 'Original Issue Date', 'Effective Date', 'Expiration Date', and 'LastModifiedDate') are converted to the datetime format. New year columns are created from these dates. Finally, all object-type columns are converted to the 'category' data type to optimize memory usage and performance.

#### Difference from Previous Assignment: 
The plots created in this assignment differ from those in previous assignments, offering a unique visualization style enriched with interactive features.


#### Resources

- [The Data](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv)
- [The Analysis](https://github.com/ralate2/Homework_6.1/blob/main/Workbook.ipynb)
