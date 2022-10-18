# Class 12: Reading Notes & Assignment Summary

## Assignments

### JavaScript Canvas

* **What does the <canvas> allow a developer to achieve?**
  * Allows you to draw 2D graphics using JavaScript
* **What is the importance of the closing `</canvas> tag?**
  * Defines the fallback content for the image
  * Anything between the tags will populate as fallback content if the image fails to load
* **Explain what the getContext() method does.**
  * `getContext()` returns a render context object
  * It takes a single argument, the type of context
    * EX: `2d`
  * By invoking the `getContext(2d)` method, you can draw shapes, text, images, and other objects

### Chart.js Documentation

* **What is Chart.js and how it can be brought into your project?**
  * Chart.js allows to draw charts using JavaScript
  * You need to connect to Chart.js in your HTML file using the following `<script>`:

  ```html
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  ```

* **List 3 different Chart types you can create using Chart.js.**
  * Bar Chart
  * Scatter Plot
  * Doughnut & Pie Chart

### Easily Create Stunning Animated Charts with Chart.js

* **What are some advantages to displaying data via a chart over a table?**
  * Humans are visual creatures and a clean chart allows us to quickly consume the relevant information and take in the point being conveyed quickly
* **How could Chart.js aid your previously created applications visually?**
  * For both Salmon Cookies, you could use a time series line chart to show the trends in cookie demand over the course of each of the 14 hours each store operates. Additionally, you could use a bar graph to display total sales of each store to easily see which stores are outperforming. 
  * For Odd Duck, a simple bar graph collecting votes and views for each product could be telling. You'd want to find the products that not only had the most votes, but also had the highest votes / view ratio.
  For example, if the "Shark" product only received 10 votes across all users, but it was only show 10 times due to the randomness of the algorithm, then you'd want to research demand for that product further since everyone who saw it voted for it against other products.
