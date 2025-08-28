## 🚀 Project Overview

The **NumPy Mathematical Calculator** is a command-line application built in Python. Its primary goal is to perform a variety of mathematical and data manipulation tasks on a collection of numbers. Unlike a standard calculator that works with single numbers, this project operates on **arrays** (or lists) of numbers, making it a powerful tool for numerical and scientific computing.

The project serves as a practical introduction to **NumPy**, which is the most fundamental library for scientific computing in Python. It demonstrates how NumPy simplifies complex calculations that would otherwise require cumbersome loops and custom functions using standard Python lists.

***

## 💡 Why Use NumPy?

At the heart of this project is the NumPy library. While you could perform these calculations using standard Python lists, NumPy offers several critical advantages that make it the industry standard.

1.  **Performance:** NumPy arrays are stored in a continuous block of memory. This efficient storage, combined with code written in low-level languages (like C and Fortran), makes NumPy operations significantly faster than their Python list equivalents. For large datasets, this difference is substantial.

2.  **Vectorization:** NumPy allows you to perform operations on entire arrays at once without writing explicit loops. This is called **vectorization**. For example, to add 5 to every number in a list in standard Python, you'd need a loop. In NumPy, you simply do `my_array + 5`. This makes the code cleaner, more readable, and much faster.

3.  **Functionality:** NumPy comes with a huge library of built-in functions for linear algebra, statistical analysis, Fourier transforms, and more. For this project, we leverage its ready-made functions for mean, median, standard deviation, etc., which are highly optimized and reliable.

In short, NumPy provides the tools to work with numerical data efficiently and expressively.

***

## ⚙️ Detailed Feature Explanation

Here’s a breakdown of what each feature does and the NumPy concepts behind it.

### 1. Basic Arithmetic Operations

This feature set handles element-wise arithmetic. "Element-wise" means the operation is applied to each element in the array corresponding to its counterpart in the second array.

* **Addition, Subtraction, Multiplication, Division:** If you have two arrays, `a = np.array([1, 2, 3])` and `b = np.array([4, 5, 6])`, the operation `a + b` results in `[5, 7, 9]`. NumPy automatically handles applying the operation to each pair of elements.
* **Power Operations:** Similarly, `a ** b` would calculate `[1**4, 2**5, 3**6]`, resulting in `[1, 32, 729]`. This is another example of vectorization, simplifying a potentially complex loop into a single, intuitive expression.

### 2. Statistical Operations

This is where NumPy's rich functional library shines. These functions aggregate data from an entire array to produce a single, insightful value.

* **Mean, Median, Standard Deviation, Variance:**
    * `np.mean(array)`: Calculates the average of all elements.
    * `np.median(array)`: Finds the middle value after sorting the array. It's more robust to outliers than the mean.
    * `np.std(array)`: Measures the amount of variation or dispersion of the elements. A low standard deviation indicates that the values tend to be close to the mean.
    * `np.var(array)`: The square of the standard deviation, another measure of data spread.
* **Minimum, Maximum, Sum, Product:**
    * `np.min(array)` and `np.max(array)`: Efficiently find the smallest and largest values.
    * `np.sum(array)`: Adds up all elements in the array.
    * `np.prod(array)`: Multiplies all elements in the array together.
* **Shape, Size, and Data Type:** These are not calculations but **attributes** of the NumPy array that provide metadata.
    * `array.shape`: Returns a tuple representing the dimensions of the array (e.g., `(6,)` for a 1D array with 6 elements, `(2, 3)` for a 2x3 2D array).
    * `array.size`: Returns the total number of elements in the array.
    * `array.dtype`: Tells you the data type of the elements (e.g., `int64`, `float64`).

### 3. Array Manipulation

This category focuses on changing the structure, order, or content of the array.

* **Reshaping Arrays:** The `array.reshape(new_shape)` method allows you to change the shape of an array without changing its data. For example, you can turn a 1D array of 8 elements into a 2D array of 4 rows and 2 columns. This is essential for preparing data for many machine learning and mathematical models.
* **Sorting and Reverse Sorting:**
    * `np.sort(array)` returns a new, sorted copy of the array.
    * To reverse sort, you can use `np.sort(array)[::-1]`. The `[::-1]` is a Python slice notation that reverses a sequence.
* **Unique Value Extraction:** `np.unique(array)` returns a new array containing only the unique elements from the original array, in sorted order. This is very useful for understanding the diversity of values in a dataset.
* **Accessing First and Last Elements:** This demonstrates basic array **indexing**.
    * `array[0]` gets the first element.
    * `array[-1]` gets the last element.
* **Filtering Values Greater Than the Mean:** This is one of NumPy's most powerful features, known as **boolean indexing** or **masking**. The process is:
    1.  First, you calculate the mean: `mean_val = np.mean(array)`.
    2.  Then, you create a boolean "mask": `array > mean_val`. This doesn't return the values themselves but a new array of `True`/`False` values (e.g., `[False, True, True, False]`).
    3.  Finally, you use this mask to select elements from the original array: `array[array > mean_val]`. This returns a new array containing only the elements where the mask was `True`. This is an incredibly efficient way to filter data based on conditions.
