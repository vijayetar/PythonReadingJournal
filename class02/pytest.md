## What is Pytest?
[Home](../README.md)  
* [Link for installing it](https://www.guru99.com/pytest-tutorial.html)  

* Pytest is a testing framework which allows us to write test codes using python.  

* Advantages are:
    * easy
    * run tests in parallel
    * detect tests
    * skip tests
    * run tests or subsets of test

* It recognizes files starting with "test_" or ending with "_test".
* the test method names should start with "test"

* Run py test commmand using   
  1. Substring matching 
    *  >py.test  
    *  >py.test test_sample1.py  
    *  >py.test -k method1 -v  
    *  >py.test -k method -v - will run all the four methods  
    *  >py.test -k methods -v – will not run any test as there is no test name matches the substring 'methods'  
-k <expression> is used to represent the substring to match
-v increases the verbosity  

  2. Run tests by markers  
    * Pytest allows us to set various attributes for the test methods using pytest markers, @pytest.mark . To use markers in the test file, we need to import pytest on the test files.  
    *  >import pytest
@pytest.mark.set1
def test_file1_method1(): pass  

  *  >@pytest.mark.set2
def test_file1_method2():  

  *   Run tests using markers
    *  >py.test -m <name>  
    *  >example: Running py.test -m set2 will run test_file1_method2.  
  * Questions:
    * What does it mean to be able to __detect tests__?
    * what is the __assert__ command?
