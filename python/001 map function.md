usage:
``` python
map(function, iterable)
```

function = a function that takes in an argument
iterable = usually a list

map will call the function on every value in the iterable

# example

function:
``` python
def make_even(num):
	if num % 2 == 1:
		return num + 1
	else:
		return num
```
iterable:
``` python
x = [12, 3, 21, 4, 5, 84, 34, 356, 647, 658, 57, 867, 7, 342]
# you get the idea
```

## 1st way 

``` python
y = []
for num in x:
	y.append(make_even(num))
```
this works but this is also why the map function exists 

this is good for:
1. simplicity
2. if you need to do something more complex in the loop
3. easier to debug

however this is slightly more wordy
## second way

``` python
y = map(make_even, x)
```
this is faster due to internal optimization

this is good for
1. being concise
2. faster for large sets of things (e.g. numbers, strings, etc)
3. fits with a more function programming style

however this is:
1. harder to debug
2. harder for beginners / less experienced people to understand 

however this is 'map' object by default if we want to turn it into a list

``` python
y = list(map(make_even, x))
```

now y is suddenly a list

this can be done with any other type e.g. tuple