# Data Analysis

## Reading

* [What is Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)
* [NumPy Tutorial](https://www.dataquest.io/blog/numpy-tutorial-python/)

## Reference

* [NumPy Arrays](https://www.tutorialspoint.com/numpy/index.htm)

## Notes

### Jupyter Lab

#### What is Jupyter Lab?

JupyterLab is the next-generation user interface for Project Jupyter. It provides a modern, flexible, and powerful platform for data science and scientific computing. JupyterLab offers a more integrated development environment for working with notebooks, code, and data.

It includes the following:

* file browser
* console
* text editor
* debugger

JupyterLab is designed to be extensible, so you can add new capabilities to it with plugins. It is also fully compatible with the classic Jupyter Notebook, so you can use all of your existing notebooks in JupyterLab.

#### What is a Jupyter Notebook?

Jupyter notebooks are interactive documents that contain a combination of text, code, and code output. They are used to create and share documents that contain live code, equations, visualizations, and narrative text. Jupyter notebooks are often used for data science, machine learning, and scientific computing, but they can be used for a wide range of tasks. They are a popular choice for doing reproducible research, as they allow you to combine code, results, and explanations in one document.

#### What is the advantage of Jupyter Lab over an IDE?

There are a few main advantages of Jupyter notebooks and JupyterLab over IDEs like VSCode and PyCharm:

* **Notebook-style development:** Jupyter notebooks allow you to mix code, text, and output in a single document, which can be useful for documenting and sharing your work. This is different from IDEs, which typically have a more traditional file-based development experience.

* **Interactive execution:** Jupyter notebooks allow you to execute code in a cell-by-cell manner, which can be useful for testing and debugging your code. This is different from IDEs, which typically require you to run your code all at once.

* **Wide language support:** Jupyter supports a wide range of programming languages, including Python, R, Julia, and more. This can be useful if you work with multiple languages or if you want to use a language that is not supported by your IDE.

That being said, IDEs like VSCode and PyCharm have their own advantages as well. They generally have more powerful code editing and debugging capabilities, and they may be a better choice for larger, more complex projects.

#### Jupyter Lab Shortcuts

* Edit mode
  * Enter: enter edit mode
  * Shift + Enter: run cell, select below
  * Ctrl + Enter: run cell
  * Alt + Enter: run cell, insert below
  * Y: to code
  * M: to markdown
  * R: to raw
  * 1-6: to heading 1-6
  * Up: select previous cell
  * Down: select next cell
* Command mode
  * Enter: enter edit mode
  * H: show keyboard shortcuts
  * Shift + H: show extended keyboard shortcuts
  * Up: select previous cell
  * Down: select next cell
  * Shift + Up: extend selected cells up
  * Shift + Down: extend selected cells down
  * A: insert cell above
  * B: insert cell below
  * X: cut selected cell
  * C: copy selected cell
  * Shift + V: paste cell above
  * V: paste cell below
  * Z: undo cell deletion
  * D, D: delete selected cell
  * Shift + M: merge selected cells, or current cell with cell below if only one cell is selected
  * S: save notebook
  * L: toggle line numbers
  * O: toggle output
  * Space: scroll down
  * Shift + Space: scroll up
  * Shift + J: select next cell
  * Shift + K: select previous cell

### NumPy

#### What is NumPy?

NumPy is a **library for Python** that is used for **scientific computing**. It provides a high-performance **multidimensional array object**, and tools for working with these arrays. 

NumPy arrays are used to store large amounts of numerical data, and they can be efficiently processed using specialized functions and libraries written in C and Fortran. 

NumPy is a fundamental library for scientific computing with Python, and it provides the foundation for many other libraries in the scientific Python ecosystem, such as SciPy and Pandas.

Can install with the `pip install numpy` command in the CLI

#### What is a NumPy Array?

A NumPy array is a multi-dimensional array of elements of the same data type. It is a **grid of values, all of the same type**, and is **indexed by a tuple of nonnegative integers**. The number of dimensions is the rank of the array, and the shape of an array is a tuple of integers giving the size of the array along each dimension.

NumPy arrays are used to store large amounts of numerical data, and they can be efficiently processed using specialized functions and libraries written in C and Fortran. NumPy arrays are more efficient and more powerful than Python's built-in lists or tuples, and they are an essential part of the scientific Python ecosystem.

Here is an example of how you can create a NumPy array in Python:

```py
import numpy as np

# Create a 1-dimensional array
a = np.array([1, 2, 3])

# Create a 2-dimensional array
b = np.array([[1, 2, 3], [4, 5, 6]])

# Create an array with three dimensions
c = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])

print(a.shape) # (3, 0)
print(b.shape) # (2, 3)
print(c.shape) # (2, 2, 3)
```

In the example above, a is a 1-dimensional array with shape (3,), b is a 2-dimensional array with shape (2, 3), and c is a 3-dimensional array with shape (2, 2, 3).

The shape (2, 3) indicates that the array has two dimensions, and the size of the array along each dimension is given by the integers 2 and 3. In this case, the first integer 2 represents the number of rows in the array, and the second integer 3 represents the number of columns in the array.

Essentially, `shape` output is like this `(#layer, #rows, #columns)`

#### NumPy Arrays and Monte Carlo Simulation

Monte Carlo simulations typically involve generating many random samples and performing statistical analyses on them in order to make predictions or estimate uncertainties. NumPy arrays are a convenient and efficient way to store and manipulate large amounts of numerical data, which makes them well-suited for use in Monte Carlo simulations.

```py
import numpy as np

# Set the number of samples
n_samples = 100000

# Generate random samples from a normal distribution
samples = np.random.normal(size=n_samples)

# Compute the mean of the samples
mean = np.mean(samples)

# Compute the standard deviation of the samples
std = np.std(samples)

print(f"Mean: {mean:.4f}")
print(f"Standard deviation: {std:.4f}")
```

In this example, we use the `np.random.normal` function to generate `n_samples` random samples from a normal distribution. We then use the `np.mean` and `np.std` functions to compute the mean and standard deviation of the samples. These statistics can be used to estimate the mean and standard deviation of the underlying distribution from which the samples were drawn.

#### Importing CSVs for Use in Python with NumPy

Code Example:

```py
import csv
with open("winequality-red.csv", 'r') as f:
    wines = list(csv.reader(f, delimiter=";"))
import numpy as np
wines = np.array(wines[1:], dtype=np.float)
```

* Steps:
  * Import the CSV library: `import csv`
  * Open the file in read (`r`) mode and set to a variable
    * Note: `delimiter` will change based on the separating value (`,`, `;`, etc)

    ```with open("winequality-red.csv", 'r') as f:
          wines = list(csv.reader(f, delimiter=','))
    ```
  
  * Import numpy: `import numpy as np`
  * Exclude header row with list slicing: `wines[1:]`
  * Set datatype to the correct format using `dtype=`
    * In this case, we use a float, so `dtype=np.float`
