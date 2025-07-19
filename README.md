# Store Sales Data Analysis

This project utilizes Python to analyze retail sales data and gain valuable insights into the sales performance of various outlet types. The primary focus is on visualizing total sales based on the outlet location type.

## Project Goal

The main objectives of this project are:
* To perform initial data exploration and cleaning (if necessary).
* To calculate total sales aggregated by different outlet location types.
* To understand sales distribution and performance through visual representations.
* To identify key insights that can inform business decisions.

## Technologies Used

* **Python**: The core programming language.
* **Pandas**: For data manipulation and analysis.
* **Matplotlib**: The foundational library for creating visualizations.
* **Seaborn**: For generating aesthetically pleasing and informative statistical graphics.

## Code Description

The provided Python code snippet performs the following operations:

1.  **Aggregates Sales:** It groups the `df` DataFrame by `'Outlet Location Type'` and calculates the sum of `'Sales'` for each group. The `.reset_index()` converts the grouped output back into a DataFrame.
2.  **Sorts Data:** The resulting `sales_by_location` DataFrame is then sorted in descending order based on the `'Sales'` column, allowing for easy identification of top-performing outlet types.
3.  **Creates Bar Plot:** A bar plot is generated using Seaborn, where:
    * The x-axis represents `'Sales'` (total sales).
    * The y-axis represents `'Outlet Location Type'`.
    * The `figsize` is set to `(8, 3)` to ensure a compact yet clear visualization.
4.  **Adds Labels and Title:** Appropriate titles for the plot and labels for the axes are added for better readability.
5.  **Adjusts Layout:** `plt.tight_layout()` is called to ensure that all elements of the plot fit within the figure area without overlapping.
6.  **Displays Plot:** `plt.show()` displays the generated visualization.

Python 

sales_by_location = df.groupby('Outlet Location Type')['Sales'].sum().reset_index()
sales_by_location = sales_by_location.sort_values('Sales', ascending=False)

plt.figure(figsize=(8, 3)) # Smaller height, enough width
ax = sns.barplot(x='Sales', y='Outlet Location Type', data=sales_by_location)

plt.title('Total Sales by Outlet Location Type')
plt.xlabel('Total Sales')
plt.ylabel('Outlet Location Type')

plt.tight_layout() # Ensures layout fits without scroll
plt.show()

## How to Run

1.  **Clone the Repository (if applicable):**

    git clone [https://github.com/CingizEsgerov05/Sales-Analysis-Python.git](https://github.com/YourUsername/your-repo-name.git)
    cd your-repo-name
  

2.  **Install Dependencies:**
    This project requires the following Python libraries. You can install them using `pip`:

    pip install pandas matplotlib seaborn

3.  **Data File:**
    Ensure you have a CSV file (e.g., `dataset.csv` or similar) containing your sales data, with columns like `Outlet Location Type` and `Sales`. This file should be loaded into a Pandas DataFrame named `df` at the beginning of your script or Jupyter Notebook.

    *(Example of loading data in your script/notebook):*

    import pandas as pd
    df = pd.read_csv('dataset.csv') # Make sure this matches your file name

4.  **Execute the Code:**

      * If you're using a Jupyter Notebook (like `Market_Analysis_Python.ipynb`): Open the notebook and run the cells sequentially.
      * If it's a Python script: Run the script from your terminal.

    <!-- end list -->

    python your_script_name.py

## Expected Output

Upon running the code, a bar plot titled "Total Sales by Outlet Location Type" will be displayed, showing the total sales for each distinct outlet location type, sorted from highest to lowest sales.
