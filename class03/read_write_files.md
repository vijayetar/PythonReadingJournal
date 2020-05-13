# Read and Write Files
[Bookmark](https://realpython.com/read-write-files-python/)

A file is a contiguous set of bytes used to store data.  n

__Character Encodings__
 An encoding is a translation from byte data to human readable characters. The two most common encodings are the __ASCII and UNICODE Formats__. ASCII can only store 128 characters, while Unicode can contain up to 1,114,112 characters. 

__Opening and Closing a File in Python__  
When you want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file. open() has a single return, the file object.

__Closing the file__ is important to prevent leaking and unwanted behavior.  
The first way to close a file is to use the __try-finally block__:  
>reader = open('dog_breeds.txt')  
try:  
    # Further file processing goes here  
finally:  
    reader.close()  

The __with__ statement automatically takes care of closing the file once it leaves the with block.  
> with open('dog_breeds.txt') as reader:  
    # Further file processing goes here  

examples of txt files  
> open('abc.txt')  
  open('abc.txt', 'r')  
  open('abc.txt', 'w') 

With these types of files, open() will return a TextIOWrapper file object.   

A buffered binary file type is used for reading and writing binary files.  
> open('abc.txt', 'rb'  
open('abc.txt', 'wb')  

With these types of files, open() will return either a BufferedReader or BufferedWriter file object:  

Raw files are low level building blocks for text and binary files and rarely used.

by passing command - 
> file.readline(chr_number) => read characters limited to the char_number in the file  
>with file.read()=> read the entire file >list(f) => make list out of contents of file f.  
