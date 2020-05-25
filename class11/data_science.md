# Data Science and NumPY

[Home](../README.md)   
[Data Science Reference](https://headstrait.com/data-science-in-a-nutshell/)  
[Numpy Reference](https://www.dataquest.io/blog/numpy-tutorial-python/) 
[Numpy CheatSheet](https://cs231n.github.io/python-numpy-tutorial/#numpy)

## Data Science in Nutshell  

__Data Science__ is basically trying to make sense of data by identifying patterns, applying algorithms to extract information and predict future actions that are suitable for a specific situation.

* __Unstructured Data:__ It does not have a predefined data model. It can be available in audio, video and text format.   
* __Structured Data:__ It is mostly available in a text format which originates from databases or specific file formats like CSV (Comma Separated Values)  

* After categorizing data (unstructured or structured), you need to analyze it. Identifying patterns of the data and understanding the data by processing it in such a way that you convert the data into information. This area of processing the data is typically referred as __Data Analytics__.  

![Image](https://headstrait.com/wp-content/uploads/2018/12/img3.png)  

## NumPy  

* Read a csv file
```
import csv
with open('winequality-red.csv', 'r') as f:
    wines = list(csv.reader(f, delimiter=';'))

### breaks the csv.reader at the delimiter ";" instead of standard ","
```
* Extract the last element from each row after the header row.  
* Convert each extracted element to a float.  
* Assign all the extracted elements to the list qualities.  
* Divide the sum of all the elements in qualities by the total number of elements in qualities to the get the mean.  

```
qualities =
[float(item[-1]) for item in wines[1:]]
sum(qualities) / len(qualities)
```
### Numpy 2-Dimensional Arrays
* In a NumPy array, the number of dimensions is called the __rank__, and each dimension is called an __axis__. So the rows are the first axis, and the columns are the second axis.
* One of the limitations of NumPy is that all the elements in an array have to be of the same type, so if we include the header row, all the elements in the array will be read in as strings. 
```
import csv
with open("winequality-red.csv", 'r') as f:
    wines = list(csv.reader(f, delimiter=";"))
import numpy as np
wines = np.array(wines[1:], dtype=np.float)
```
In the above code, we:

1. Import the numpy package.  
2. Pass the list of lists wines into the array function, which converts it into a NumPy array.  
3. Exclude the header row with list slicing.  
4. Specify the keyword argument dtype to make sure each element is converted to a float. We’ll dive more into what the dtype is later on.  
5. check out the rows and columns using command - wines.shape  

* NumPy has several data types.  
>>> float — numeric floating point data.  
int — integer data.  
string — character data.  
object — Python objects.  

