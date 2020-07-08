## GENERATOR, ITERATORS

[Home](../README.md)   
[Iterator Reference](https://dbader.org/blog/python-iterators)

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
print(tuple(g(7,11)))
==> (7,9,11,)
```
## Iterators
```
repeater = Repeater('Hello')
for item in repeater:
    print(item)

class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return RepeaterIterator(self) 

class RepeaterIterator:
    def __init__(self, source):
        self.source = source

    def __next__(self):
        return self.source.value
```

```
class InfiniteRepeater(object):
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return self

    def __next__(self):
        return self.value

    # Python 2 compatibility:
    def next(self):
        return self.__next__()
```

