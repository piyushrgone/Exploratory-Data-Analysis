# Exploratory-Data-Analysis

**Exploratory Data Analysis with Pandas Python**

**Step 0: Import and Reading Data**

```python
import pandas as pd

# Read the data from a CSV file
df = pd.read_csv('data.csv')
```

**Step 1: Understanding Data**

**Dataframe `shape`**

```python
df.shape
```

This will give you the dimensions of the dataframe, i.e., the number of rows and columns.

**`head` and `tail`**

```python
df.head()
df.tail()
```

These methods will show you the first and last few rows of the dataframe, respectively. This can be helpful for getting a quick overview of the data.

**`dtypes`**

```python
df.dtypes
```

This method will show you the data type of each column in the dataframe. This is important to know when performing certain data analysis tasks.

**`describe`**

```python
df.describe()
```

This method will provide you with summary statistics for each numerical column in the dataframe, such as the mean, median, standard deviation, and range.

**Step 2: Data Preparation**

**Drop irrelevant columns and rows**

```python
# Drop a column
df = df.drop('irrelevant_column', axis=1)

# Drop a row
df = df.drop(10)
```

**Identifying duplicates**

```python
# Find duplicate rows
duplicates = df[df.duplicated()]

# Drop duplicate rows
df = df.drop_duplicates()
```

**Renaming columns**

```python
# Rename a column
df = df.rename(columns={'old_column_name': 'new_column_name'})
```

**Feature creation**

```python
# Create a new feature from existing features
df['new_feature'] = df['feature_1'] + df['feature_2']
```

**Step 3: Feature Understanding**

**Plotting feature distribution**

**Hist**

```python
import matplotlib.pyplot as plt

df['feature'].hist()
plt.xlabel('Feature')
plt.ylabel('Count')
plt.title('Distribution of Feature')
plt.show()
```

**KDE**

```python
import seaborn as sns

sns.kdeplot(df['feature'])
plt.xlabel('Feature')
plt.ylabel('Density')
plt.title('Distribution of Feature')
plt.show()
```

**Boxplot**

```python
sns.boxplot(x='feature', y='target', showmeans=True, data=df)
plt.xlabel('Feature')
plt.ylabel('Target')
plt.title('Boxplot of Feature vs. Target')
plt.show()
```

**Step 4: Feature Relationships**

**Scatterplot**

```python
plt.scatter(df['feature_1'], df['feature_2'])
plt.xlabel('Feature 1')
plt.ylabel('Feature 2')
plt.title('Scatterplot of Feature 1 vs. Feature 2')
plt.show()
```

**Heatmap Correlation**

```python
sns.heatmap(df.corr(), annot=True)
plt.title('Correlation Heatmap')
plt.show()
```

**Pairplot**

```python
sns.pairplot(df)
plt.show()
```

**Groupby comparisons**

```python
df.groupby('feature')['target'].mean()
```

This will give you the mean target value for each group of the feature. You can use this to compare the target variable across different groups of the feature.

**Step 5: Ask a Question about the data**

Once you have a good understanding of the data, you can start to ask questions about it. For example, you might want to know:

* What is the relationship between the feature variables and the target variable?
* Are there any outliers in the data?
* Are there any patterns in the data?

You can use the various plots and statistics that you have learned about to answer these questions.

**Conclusion**

This is just a brief overview of how to perform exploratory data analysis (EDA) with Pandas Python. For more detailed information, there are many resources available online and in books.