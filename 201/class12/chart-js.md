# Chart.js

## Reference

* [Drawing Shapes with Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)
* [Applying Style and Colors - Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)
* [Drawing Text - Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)

## Reading

* [Chart.js Documentation](http://www.chartjs.org/docs/)
* [Easily Create Stunning Animated Charts with Chart.js](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)

## Notes

* Using Chart.js only requires the necessary script run along with a single `<canvas>` node to render the chart
* Chart.js needs to be linked in the HTML file using the following:

```html
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
```

* This allows us to access the Chart.js scripting language

### Use

* Always starts with a `<canvas>` tag:

```html
<canvas id="myChart" width="400" height="400"></canvas>
```
* You can then use `getElementById` to grab the `<canvas>` element from the DOM:

```js
// Any of the following formats may be used
const ctx = document.getElementById('myChart');
const ctx = document.getElementById('myChart').getContext('2d');
const ctx = $('#myChart');
const ctx = 'myChart';
```

* Full Example:

``` html
<canvas id="myChart" width="400" height="400"></canvas>
<script>
const ctx = document.getElementById('myChart');
const myChart = new Chart(ctx, {
    type: 'bar',
    data: {
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
        datasets: [{
            label: '# of Votes',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
        scales: {
            y: {
                beginAtZero: true
            }
        }
    }
});
</script>
```
