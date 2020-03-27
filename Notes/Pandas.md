# Pandas Notes

[PythonHow Tutorial](https://pythonhow.com/data-analysis-with-python-pandas/)
- Python for data analysis
- Built on numpy, which also allows you to create 2d and 3d arrays of data in Python
- Pandas main object is a **dataframe** (dataframe = 2d numpy array _with rows and columns_)

```python
import pandas as pd #Imported Pandas and assigned the pd namespace for it
df1 = pd.read_csv("C:/PythonHow/income_data.csv")
print(df1)

# Code introspection
help(pd.DataFrame.read_csv)

# Removing the header of the dataframe
df1 = pd.read_csv("C:/PythonHow/file1.csv", header=None)
```

## Jupyter Notebook "Jupyter"
```python
jupyter notebook # start Jupyter Notebook

# Setting the state column as the index column; drop prevents the column from being dropped when new index column is set
df2 = df1.set_index("State", drop=False)

# Extracting dataframe subset
# #loc
df2.loc[startrow:endrow, startcolumn:endcolumn]
df2.loc["California", "2013"] # Specific cell
df2.loc[:, "2005"].mean()
# #iloc
df2.iloc[0:3, 0:4] # Index based position location
# #ix
df2.ix[0:3, "2005":"2007"] # If you don't know whether you're using indexing in the row or column, use ix



# Extracig specific columns and rows
df2[["2005", "2008", "2009"]] # Columns, with double square-brackets
df2[1:3] # Rows, of a pandas dataframe
```

## Data Analysis Methods
- Methods applied to df are applied on columns
```python
# List of available DataFrame methods
dir(pd.DataFrame)
# Description of each meethod
help(pd.DataFrame.mean)

df2.loc[:, "2005"].mean() # Applying not to pandas dataframe but pandas data series object
type(df2.loc[:, "2005"]) # pandas.core.series.Series

# Calculate mean along the column
df2["Mean"]=df2.mean(axis=1) # axis=0 would be along the rows
df2["Mean"]=df2.mean(axis=0) # axis=0 is along the rows
```

## Graphs
- Bokeh graphs are interactive
- matplotlib are static images
- Python websites are Flask or Django