

<!DOCTYPE html>
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
        <p><strong>3. Interactivity:</strong> The bar chart includes an interactive dropdown menu (<code>state_selection</code>) that allows users to select a state. This interactivity enables users to dynamically filter the data and examine the license type distribution for any specific state.</p>
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
        <p><strong>1. Description:</strong> This pie chart visualizes the distribution of the top 5 most frequent license statuses within cities that have at least 5 distinct license types. The chart shows the proportion of each license status within the selected city, with the size of each segment proportional to the number of licenses with that particular status.</p>
        <p><strong>2. Encoding Types:</strong>
            <ul>
                <li><strong>Theta (Angle):</strong> Quantitative encoding (<code>count_id</code>) represents the number of licenses with each status, determining the size of the pie segments.</li>
                <li><strong>Color:</strong> Categorical encoding (<code>License Status</code>) distinguishes between different license statuses, helping to visually separate the statuses for easier interpretation.</li>
                <li><strong>Tooltip:</strong> Displays detailed information on each license status and the associated count when hovering over the segments.</li>
            </ul>
        </p>
        <p><strong>3. Interactivity:</strong> The pie chart includes an interactive radio button feature (<code>city_selection</code>), enabling users to select a city from the list. This allows users to explore the top 5 license statuses for different cities, making the data exploration more dynamic and interactive.</p>
    </div>
</body>
</html>

#### Resources

- [The Data](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv)
- [The Analysis](https://github.com/ralate2/Homework_6.1/blob/main/Homework_6.1.ipynb)
