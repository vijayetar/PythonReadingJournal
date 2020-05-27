# PANDAS  

[Home](../README.md) 
[detailed reference](https://realpython.com/learning-paths/pandas-data-science/)   
[Reference](https://towardsdatascience.com/be-a-more-efficient-data-scientist-today-master-pandas-with-this-guide-ea362d27386)   
[10 min PANDAS](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html)    

* It is open source  
*  Pandas is a core package with additional features from a variety of other packages.  
* Pandas is like Excel in Python: it uses tables (namely DataFrame) and operates transformations on the data. But it can do a lot more.  
* It is simple to use, hiding all the complex and abstract computations behind(generally) intuitive
fast, if not the fastest data analysis package (it highly optimized in C)  


## Reading  

```
data = pd.read_csv('my_file.csv', sep=';', encoding='latin-1', nrows=1000, skiprows=[2,5])
```
>read_csv  , read_excel  , read_clipboard  , read_sql  

## Writing  
``` 
data.to_csv('my_new_file.csv', index=None) 
```
* There’s also the .to_clipboard if you’re like me an Excel maniac who wants to paste your results from Python to Excel.  

## Checking the data  
```
data.shape  

data.describe()
```
## Seeing the data  

```
data.head(3)  
data.loc[8, 'column_1']  
data.loc[range(4,6)]  

```
## Basic Plotting  
* this is with matplotlib  
```
data['column_numerical'].plot()
data['column_numerical'].hist()
data.loc[data['column_1']=='french', 'column_1'] = 'French'
```
## Medium Level Functioning  
```
1. Counting occurences -  data['column_1'].value_counts()  
2. Operations on the data - 
data['column_1'].map(len)  
3.  data['column_1'].map(len).map(lambda x: x/100).plot()  
4. Missing data - data.fillna('missing', inplace=True)
# or, for instance, if your data is numeric
5. Missing integer data - data.fillna(-9999, inplace=True)
```
* .apply() applies a function to columns. Use .apply(, axis=1) to do it on the rows.  
* .applymap() applies a function to all cells in the table (DataFrame).  

## Advanced Level Functioning  
* Merging, grouping, iterating  
```
data.merge(other_data, on=['column_1', 'column_2', 'column_3'])  

data.groupby('column_1')['column_2'].apply(sum).reset_index()  

dictionary = {}
for i,row in data.iterrows():
  dictionary[row['column_1']] = row['column_2']  


```