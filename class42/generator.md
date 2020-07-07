## GENERATOR 

[Home](../README.md) 

* Generator yields a product, and pauses it until it is requested again.
```
def odds(start, stop):
  for odd in range (start, stop+1, 2):
    yield odd

g=odds(5,11)

print(next(g)) ==> 5
print(next(g)) ==> 7
print(next(g)) ==> 9
print(next(g)) ==> 11

for i in g(5,11):
  print(i)
5
7
9
11

print(list(g(5,11)))
==>  [5,7,9,11]
