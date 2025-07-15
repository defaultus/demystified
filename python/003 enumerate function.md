usage:
``` python
enumerate(iterable, starting_index)
```
this function can be used to get the index number of something within an iterable (list, tuple, etc)

# example 

lets say you have a list of names
``` python
names = ["howard", "dave", "michael"] # this is not me being uncreative i swear
```

we can easily get / loop over the names but what if we want the index number too

``` python 
for index, name in enumerate(names):
	print(index, name)
```

the result would look like this:

```
0 howard
1 dave 
2 michael
```

we can actually change the starting number too 

``` python
for index, name in enumerate(names, start=1): #can be any number you want
	print(index, name)
```

now it will look like this:
```
1 howard
2 dave 
3 michael
```

# another example

lets say you have a function that takes in a list 
lets also say you want the index number from something in that list if it matches some criteria 

``` python
def func_name(names):
	for index, name in enumerate(names):
		if name == "dave":
			return index
	return None
```

here we can nab the index of dave and can use it for whatever we want

## notes

we are ignoring that

``` python
names.index('dave')
```

exists

however when working with large lists or tuple or whatever you may not be able to read through every value to know what it is

dave could've been at index 213 in some large list and I know you aren't reading all that

the previous function is great if you want the value of a specific index or the index of a specific value