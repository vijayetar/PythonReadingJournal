# Big O Notation
[link](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/)  
* It is just about understanding to what degree is your program complicated and complex, because it automatically makes the run time much longer.
* O(1): executes the program in the same time irrespective of the size of the input data.  
* O(N): grow linearly depending on the size of the input data  
* O(N*2): will grow directly proportional to the square of the size of the input data.  
* O(N**2): growth doubles with each addiiton of the input data set
* O(logN): grows logarithimically  
# Facts and Myths about Names and Values
* Assignment never copies data
* Lists are mutable and so allow us to change value by appending to it
* Immutable data sets are tuples, integers, floats and strings
  * so when we are writing 
  > x = x+1 
  we are rebinding it to a new integer
  * but in case of lists when we append it, it is basically mutating it or changing it.
* within a loop
  * >for x in nums:
  * here x gets assigned to nums[0] and so forth
  but if we change
  * > x=x+1
  * it does not change the values for numn because the assignement does not affect the value of nums[i]. but if you changed it for nums[i] will change the list contents.  
__Don't mutate lists, make new lists instead__
* Names have no types and can be used on any values, but they have scope.  And values exist, but they have no scope on their own.  
[Python Library](https://pymotw.com/3/index.html)