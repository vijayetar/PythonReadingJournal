# Generate Random Numbers
[Home](../README.md) 
### [Random docs](https://docs.python.org/3/library/random.html) 
* Import Random
* random() --> is the key word. it generates random float number between 0.0 and 1.0.  
* Random.randint(start,stop) --> Generates random numbers between start and stopcode.  
* Random.random() --> generates numbers beween 0-1 and can be multiplied with 100 or 1000 to create higher numbers  
* Random.choice([insert set here]): generates random selection from choices in the set  
* random.seed(a=None, version=2) -->
Initializes the random number generator  
* random.randrange(start,stop[,step])  
* random.shuffle(x[, random])
Shuffle the sequence x in place.  
The optional argument random is a 0-argument function returning a random float in [0.0, 1.0); by default, this is the function random().  
* random.sample(population, k)
Return a k length list of unique elements chosen from the population sequence or set. Used for random sampling without replacement.  
* random.triangular(low, high, mode)  The mode argument defaults to the midpoint between the bounds, giving a symmetric distribution.
