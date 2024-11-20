
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>License Visualizations</title>
    <script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
    <script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
    <script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 20px;
        }
        h1, h2 {
            color: #333;
        }
        p {
            margin: 10px 0;
        }
        iframe {
            border: none;
        }
    </style>
</head>
<body>
    <h1>License Visualizations</h1>

    <!-- Bar Chart -->
    <h2>License Types by State</h2>
    <div id="bar_chart"></div>
    <script type="text/javascript">
        vegaEmbed('#bar_chart', 'bar_chart.json')
            .catch(console.error);
    </script>
    <div>
        <h3>Write-Up for Bar Chart</h3>
        <p><strong>1. Description:</strong> This bar chart visualizes the distribution of license types across different states. It displays the number of licenses for each type, where the height of each bar represents the frequency of a particular license type within the selected state. By providing a breakdown of license types, the chart helps to understand the prevalence of different types of licenses across states, offering insight into which license types are more common in the chosen state.</p>
        <p><strong>2. Encoding Types:</strong>
            <ul>
                <li><strong>X (Quantitative):</strong> The <code>count(id)</code> variable is used to encode the number of licenses for each license type. The height of each bar represents the number of licenses for that specific type.</li>
                <li><strong>Y (Ordinal):</strong> The <code>License Type</code> variable is encoded on the y-axis, sorted by the number of licenses in descending order to highlight the most frequent license types at the top.</li>
                <li><strong>Color:</strong> Categorical encoding (<code>License Type</code>) is used to color the bars by license type, visually distinguishing between the different license types.</li>
                <li><strong>Tooltip:</strong> Displays detailed information on the <code>License Type</code> and the corresponding count of licenses when hovering over each bar.</li>
            </ul>
        </p>
        <p><strong>3. Color Scheme:</strong> A categorical color scheme is applied to differentiate between the different license types. This color differentiation enhances clarity, making it easier for viewers to distinguish between each type of license. The colors are automatically assigned by Vega, ensuring consistent and clear visual communication.</p>
        <p><strong>4. Data Transformations:</strong> The data is filtered based on the selected state, allowing users to view the license type distribution for a specific state. The data is aggregated by License Type and the count of licenses (<code>count(id)</code>) is calculated to represent the number of licenses for each type. This transformation helps to focus on the specific license type distribution within the state, ensuring that the data is aggregated and presented accurately.</p>
        <p><strong>5. Interactivity:</strong> The bar chart includes an interactive dropdown menu (<code>state_selection</code>) that allows users to select a state. This interactivity enables users to dynamically filter the data and examine the license type distribution for any specific state. The dropdown allows for a smooth and flexible exploration of the data.</p>
        <p><strong>6. Impact of Interactivity:</strong> The interactivity of the bar chart enhances its usefulness by allowing users to filter the data based on the selected state. By choosing different states, users can easily compare the license type distribution across various regions. This interaction makes the visualization more personalized and relevant to the user's specific interests, improving data exploration and insight extraction. It also allows for a clearer focus on the license types that are most common in each state, providing a better understanding of regional differences in license distributions.</p>
    </div>



    <!-- Pie Chart -->
    <h2>Top 5 License Status Distribution by Cities</h2>
    <div id="pie_chart"></div>
    <script type="text/javascript">
        vegaEmbed('#pie_chart', 'pie_chart.json')
            .catch(console.error);
    </script>
    <div>
        <h3>Write-Up for Pie Chart</h3>
        <p><strong>1. Description:</strong> This pie chart visualizes the distribution of the top 5 most frequent license statuses within cities that have at least 5 distinct license types. The chart shows the proportion of each license status within the selected city, with the size of each segment proportional to the number of licenses with that particular status. By focusing on cities with a minimum of 5 license types, this visualization allows users to explore the most common license statuses in more diverse cities with a richer variety of license types.</p>
        <p><strong>2. Encoding Types:</strong>
            <ul>
                <li><strong>Theta (Angle):</strong> Quantitative encoding (<code>count(id)</code>) represents the number of licenses with each status, determining the size of the pie segments.</li>
                <li><strong>Color:</strong> Categorical encoding (<code>License Status</code>) distinguishes between different license statuses, helping to visually separate the statuses for easier interpretation.</li>
                <li><strong>Tooltip:</strong> Displays detailed information on each license status and the associated count when hovering over the segments.</li>
            </ul>
        </p>
        <p><strong>3. Color Scheme:</strong> A categorical color scheme is applied to differentiate the license statuses. This ensures that each license status is clearly distinguishable from others, enhancing the visual clarity of the chart. The colors are automatically assigned by Vega, ensuring consistent design and easy differentiation between the statuses.</p>
        <p><strong>4. Data Transformations:</strong> The data is filtered to include only those cities that have at least 5 distinct license types (filtered_data). It is then aggregated by License Status and City, with the count(<code>id</code>) computed to show the total number of licenses for each status within the city. The data is then ranked by the count of licenses in descending order, and only the top 5 license statuses for each city are displayed. This transformation allows the focus to be on the most significant license statuses while filtering out cities with fewer types of licenses.</p>
        <p><strong>5. Interactivity:</strong> The pie chart includes an interactive radio button feature (<code>city_selection</code>), enabling users to select a city from the list. This allows users to explore the top 5 license statuses for different cities, making the data exploration more dynamic and interactive.</p>
        <p><strong>6. Impact of Interactivity:</strong> Interactivity enhances the usability of the pie chart by allowing users to select a city and view its top 5 license status distribution. This gives users a tailored, more in-depth view of the data, enabling them to focus on specific cities of interest. The radio button selection makes it easier to choose cities from the list without overwhelming the user with too many options at once. Overall, this interaction improves the accessibility of the data and makes the visualization more engaging and customizable.</p>
    </div>

    
    <!-- Resources -->
    <h2>Resources</h2>
    <p>
        <a href="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv">The Data</a> |
        <a href="https://github.com/ralate2/Homework_6.1/blob/main/Workbook.ipynb">The Analysis</a>
    </p>
</body>
</html>
