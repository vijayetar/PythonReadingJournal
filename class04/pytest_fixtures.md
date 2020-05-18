# Pytest Fixtures and Coverage  
[Home](../README.md)  
* When you're writing tests, you'll have a few tests with similar characteristics, something that pytest handles with "parametrized tests".  
* Those objects might contain data you want to share across tests, or they might involve the network or filesystem. These are often known as __"fixtures"__ in the testing world, and they take a variety of different forms.  
* Define fixtures using a combination of the pytest.fixture decorator, along with a function definition.  
> def reverse_lines(f):  
   return [one_line.rstrip()[::-1] + '\n'  
           for one_line in f]  

  > @pytest.fixture  
def simple_file():  
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))  

  > def test_reverse_lines(simple_file):  
   assert reverse_lines(simple_file) == ['cba\n', 'fed\n',
 ↪'ihg\n', 'lkj\n']  

 *  this looks like a simple function  
 *  fixtures are used differently from global variables  
 * fixture might act like data, in that you don't invoke it with parentheses  
 * can make calculations and decisions
 *  if you set the scope of the fixture to be "module", it'll be available throughout your tests but will execute only a single time. 
 *  > @pytest.fixture(scope='module')
def simple_file():  
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))  

  * __Do not do the scope = 'module'__

  ## Coverage  
  * "Code coverage" allows you to check that your tests have run all of the code.
  >pytest --cov=my_function
  >coverage html  **human readable coverage report**
  * This creates a directory called htmlcov. Open the index.html file in this directory using your browser, and you'll get a web-based report showing (in red) where your program still lacks coverage.  


