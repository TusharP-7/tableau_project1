<!DOCTYPE html>
<html>
<head>
<title>Region Sales Comparison - Tableau Project</title>
</head>

<body>

<h1>Comparison of Region Based on Sales - Tableau Project</h1>

<p><strong>Description:</strong> The director of a leading organization wants to compare the sales between two regions. The upper management seeks to visualize the sales data using a dashboard to understand performance and suggest improvements.</p>

<p><strong>Objective:</strong> Create a dashboard to visualize the sales comparison between two selected regions.</p>

<p><strong>Datasets:</strong> Sample Superstore</p>

<h2>Steps to Perform:</h2>
<ol>
<li>Select Sample Superstore as Dataset
  <ol type="i">
    <li>Use Sample Superstore Dataset</li>
    <li>Select Data</li>
    <li>Use Group by from Data Source Table on a Folder to segregate data for Customer Name and Order ID.</li>
  </ol>
</li>
<li>Create a hierarchy called Location for the variable Country.</li>
<li>Create two parameters: Primary Region and Secondary Region with all regions listed.
  <ol type="i">
    <li>Create Parameters for Primary Region and Secondary Region</li>
    <li>Create a Calculated Field for both Primary Region and Secondary Region</li>
  </ol>
</li>
<li>Create a First Order Date
  <ol type="i">
    <li>Create a Calculated Field and name it as the First Order Date</li>
  </ol>
</li>
<li>Create a dashboard
  <ol type="i">
    <li>Align all sheets in the dashboard</li>
  </ol>
</li>
<li>Partition the dashboard to display details of Primary Region and Secondary Region:
  <ol type="i">
    <li>First Order Date</li>
    <li>Total Sales</li>
    <li>Average Sales per Order</li>
    <li>No. of Customers</li>
    <li>No. of Orders</li>
    <li>No. of Products in Sales</li>
  </ol>
</li>
</ol>

<p><strong>Calculations:</strong></p>
<ol>
<li><strong>First Order Date Calculation:</strong>
  <ul>
    <li>Convert order date to number using the formula: <code>(YEAR([Order Date]) * 10000) + (MONTH([Order Date]) * 100) + DAY([Order Date])</code></li>
    <li>Add this calculated value to 'Measure Values'</li>
    <li>Select measure as 'Minimum' to get the first order date</li>
    <li>Change the format to custom and add '####-##-##' to change the format.</li>
  </ul>
</li>
<li><strong>No. of Customers:</strong> <code>COUNTD([Customer ID])</code></li>
<li><strong>Average Sales per Order (Using LOD):</strong> <code>{FIXED [order ID]: SUM([Sales])}</code></li>
<li><strong>No. of Orders:</strong> <code>COUNTD([order ID])</code></li>
<li><strong>No. of Products in Sale (Using LOD):</strong> <code>{INCLUDE [Product ID] : SUM([Sales])}</code></li>
</ol>

<p><strong>Project Link:</strong> <a href="https://public.tableau.com/app/profile/tushar.parab4936/viz/SalescomparisonbyRegion_17148295776400/Dashboard1?publish=yes" target="_blank">View Dashboard</a></p>

<h1>Dashboard Insights</h1>

<p><strong>Customer Base & Market Presence:</strong> The Central region has a significantly larger customer base with 829 customers compared to 642 in the East region, indicating a stronger market presence.</p>

<p><strong>Order Volume:</strong> The Central region also has a higher number of orders at 1,807, suggesting higher sales activity compared to 1,683 orders in the East.</p>

<p><strong>Product Variety:</strong> Despite fewer customers and orders, the East region has more products in sales (3.6K) than the Central (3.5K), which could point to a wider product range or more frequent stock turnover.</p>

<p><strong>Spending Per Transaction:</strong> The average sale per order is higher in the East ($242) than in the Central ($238), implying that customers in the East may be purchasing more expensive items or larger quantities per order.</p>

<p><strong>Top-Selling Categories:</strong> Phones and Chairs are consistently prominent across months in both regions, indicating they are likely top-selling products.</p>

<p><strong>Seasonal Trends:</strong> Certain product categories like Appliances show peaks at specific times of the year, suggesting seasonal demand fluctuations.</p>

<p><strong>Sales Fluctuations:</strong> There are noticeable fluctuations in average sale per order within sub-categories, which could be influenced by promotional activities or shifts in consumer purchasing patterns.</p>

<p>These insights can inform targeted sales strategies, inventory management, and marketing campaigns to capitalize on regional strengths and opportunities for growth.</p>
</body>
</html>

