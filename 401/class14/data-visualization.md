# Data Visualization

## Reading

* [Matplotlib Tutorial](https://www.labri.fr/perso/nrougier/teaching/matplotlib/)

## Reference

* [Seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)
* [Bokeh Tutorial](https://mybinder.org/v2/gh/bokeh/bokeh-notebooks/master?filepath=tutorial%2F00%20-%20Introduction%20and%20Setup.ipynb)
* [Seaborn Cheat Sheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Seaborn_Cheat_Sheet.pdf)


## Notes

### What is Matplotlib?

Matplotlib is a data visualization library in Python. It allows users to create a wide range of static, animated, and interactive visualizations in Python. Matplotlib was initially designed to provide an interface for drawing 2D graphics, but has since grown to support many additional plotting capabilities. 

It is one of the most widely used plotting libraries in the scientific Python ecosystem and is an important tool for both data exploration and data communication.

Matplotlib can be used for a wide range of statistical plotting needs. Some common types of plots that are used for statistical analysis include:

Line plots: Line plots are used to visualize the trend of one or more numerical variables over a continuous interval or time period.

Scatter plots: Scatter plots are used to visualize the relationship between two numerical variables.

Bar plots: Bar plots are used to visualize the distribution of a categorical variable.

Histograms: Histograms are used to visualize the distribution of a numerical variable.

Box plots: Box plots are used to visualize the distribution and quartiles of a numerical variable.

To use Matplotlib for statistical plotting, you will first need to install it using `pip install matplotlib`. Then, you can use the `pyplot` module from Matplotlib to create a wide range of statistical plots. For example:

```py
import matplotlib.pyplot as plt

# Generate some random data
x = np.random.normal(size=100)
y = np.random.normal(size=100)

# Create a scatter plot
plt.scatter(x, y)

# Show the plot
plt.show()
```

This code with generate a scatter plot of randomized values at `x,y`


### What's the difference between Matplotlib and Seaborn?

Matplotlib and Seaborn are both data visualization libraries in Python. Matplotlib is a lower-level library that is more tightly integrated with the base Python language, while Seaborn is built on top of Matplotlib and is designed to provide higher-level abstractions for visualizing statistical datasets.

One key difference between Matplotlib and Seaborn is that Seaborn is specifically designed to work with Pandas dataframes and NumPy arrays, which makes it easier to use for statistical plotting. Seaborn also has a number of additional features, such as support for plotting statistical regression models and automatic generation of plot titles and axis labels.

In general, Matplotlib is a powerful and flexible library for creating a wide range of static, animated, and interactive visualizations in Python, but it can be somewhat complex to use and requires a lot of code to create even basic plots. Seaborn is generally easier to use and provides a higher-level interface that is better suited for statistical plotting. However, it is built on top of Matplotlib and can be used to create the same types of plots as Matplotlib, so you can use either library depending on your needs and preferences.

### What is Bokeh?

Bokeh is a data visualization library for Python that allows users to create interactive, web-based plots. It is particularly useful for creating plots that can be displayed in a web browser, such as plots embedded in a website or as part of a web application.

Bokeh is built on top of modern web technologies, such as HTML, CSS, and JavaScript, and can be used to create a wide range of visualizations, including scatter plots, line plots, bar plots, and choropleth maps. Bokeh also has a number of advanced features, such as support for streaming and real-time data and the ability to link different plots together.

One key advantage of Bokeh is that it is designed to be used with large datasets and can handle very large numbers of data points efficiently. It is also easy to use and allows users to create interactive plots with relatively little code. However, it is a specialized library focused on creating interactive web-based visualizations and may not be the best choice for all types of data visualization tasks.

### How do I choose between these data visualization libraries?

When choosing a data visualization library for your project, you should consider a few key factors:

* **The type of visualizations you need to create:** Each library has its own set of supported plot types and features, so you should choose a library that has the capabilities you need.

* **The level of customization you require:** Some libraries, such as Matplotlib, offer a high level of customization, but may require more code to create custom plots. Others, such as Seaborn, provide a higher-level interface with fewer customization options.

* **The size and complexity of your data:** Some libraries, such as Bokeh, are designed to handle large and complex datasets efficiently, while others may not be as well-suited for this type of data.

* **The level of interactivity you need:** Some libraries, such as Bokeh, provide advanced support for creating interactive plots, while others may not have this capability.

* **The intended use of the plots:** If you need to create plots for web-based applications or for use in a web browser, libraries like Bokeh and Plotly may be more suitable than Matplotlib or Seaborn.

Ultimately, the best choice of data visualization library will depend on your specific needs and requirements. It may be helpful to try out a few different libraries to see which one works best for your use case.

### Specific considerations when choosing which library to use

* **Matplotlib:**
  * You need to create a wide range of plot types and customize the appearance of your plots in fine detail.
  * You are comfortable with a relatively low-level interface and don't mind writing more code to create custom plots.
  * You need to create static plots that can be saved as image files.
  * You want to use a library that is well-established and has a large user base and a robust developer community.
* **Seaborn:**
  * You want to create statistical plots and are working with Pandas dataframes or NumPy arrays.
  * You want to create plots with a higher-level interface that requires less code to use.
  * You want to create attractive, publication-quality plots with a minimal amount of effort.
  * You want to create static plots that can be saved as image files.
* **Bokeh:**
  * You want to create interactive, web-based plots that can be displayed in a web browser.
  * You are working with large and complex datasets and need a library that can handle a large number of data points efficiently.
  * You want to create real-time or streaming plots.
  * You want to create plots that can be linked and interact with each other.
