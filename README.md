
---

# Experiment 15: Data Normalization and Data Type Conversion

---

### Aim: To perform Data Normalization and Data Type Conversion using Python

---

### Theory

Data Normalization is a scaling technique used in the preprocessing phase to adjust the values of numeric columns in a dataset to a common scale. This ensures that features with larger ranges do not dominate the learning process of machine learning models over features with smaller ranges. Common methods include **Simple Feature Scaling**, **Min-Max Scaling**, **Z-score Normalization**, and **Decimal Scaling**.

Data Type Conversion (Encoding) involves transforming non-numeric data into a numerical format that computers can process. **Label Encoding** assigns a unique integer to each category, while **One-Hot Encoding** converts categorical variables into several binary columns (dummy variables) indicating the presence of a category with a 1 or 0.

---

### Command Descriptions

The following Pandas and NumPy commands were used to normalize and encode the dataset:

| Command | One-Line Description |
| :--- | :--- |
| `df['Col'] / df['Col'].max()` | Performs Simple Feature Scaling by dividing each value by the maximum value in the column. |
| `(df - df.min()) / (df.max() - df.min())` | Implements Min-Max Scaling to squeeze all numerical values into a range between 0 and 1. |
| `(df - df.mean()) / df.std()` | Applies Z-score Normalization to center data around a mean of 0 with a standard deviation of 1. |
| `df['Col'] / 10**n` | Performs Decimal Scaling by moving the decimal point based on the maximum absolute value in the column. |
| `df['Col'].astype('category').cat.codes` | Implements Label Encoding by assigning a unique incremental integer to each text category. |
| `pd.get_dummies()` | Converts categorical string variables into multiple binary dummy variables (One-Hot Encoding). |
| `pd.get_dummies() * 1` | Uses multiplication to convert boolean True/False encoding results into binary 1s and 0s. |
| `pd.concat()` | Merges the newly created dummy variable columns back into the original dataset. |
| `df.drop()` | Removes the original categorical columns from the dataset after they have been successfully encoded. |

---

### Functions and Logic Used

#### Normalization Logic
* **Simple Scaling:** Useful for keeping data positive and reducing the magnitude of values.
* **Min-Max Scaling:** Best used when the distribution of data is not Gaussian (Normal) and has fixed boundaries.
* **Z-Score (Standardization):** Ideal for algorithms that assume the data follows a bell curve or when outliers are present.
* **Decimal Scaling:** Normalizes data by power-of-ten division to ensure all values fall between -1 and 1.

#### Encoding Logic
* **Label Encoding:** Used to transform categorical text into a single column of ranked integers.
* **One-Hot Coding Multiplication:** Multiplying the dummy DataFrame by 1 to programmatically convert logical bits into mathematical integers for model compatibility.
* **Dummy Variable Creation:** Used to handle categorical data like "Department" so that the model can interpret them as mathematical features.
* **Feature Integration:** Using `pd.concat` ensures the structural integrity of the table while adding new numeric features.

---

### Conclusion

Through this experiment, I successfully performed data normalization and type conversion using Python. I learned how to scale numerical data using four different mathematical approaches—including Z-score and Decimal Scaling—to ensure feature balance. Furthermore, I practiced transforming categorical variables into binary formats using One-Hot Encoding and Label Encoding, which are mandatory steps for preparing text-based data for mathematical modeling and machine learning algorithms.
