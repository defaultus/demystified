usage:
``` python
variable_name = zip(iterable1, iterable2)
```
the iterable in this case can be a list or something like a tuple but they don't have to be the same

# example

``` python
names = ["howard", "dave", "michael"] # list
fav_foods = ("pizza", "pork pies", "pudding") # tuple

people = zip(names, fav_foods)

for i in people:
	print(i)
```
the output would be something akin to:

```
('howard', 'pizza')
('dave', 'pork pies')
('michael', 'pudding')
```
being returned here is just some tuples

by default it returns a `zip` object but can be easily converted into something else

``` python
people = list(zip(names, fave_foods))
```
with this change we will instead have a list of tuples

kind of like this 

``` 
people = [
('howard', 'pizza'),
('dave', 'pork pies'),
('michael', 'pudding')]
```

however I'd like to demonstrate turning a zip object into a dictionary 

``` python
people = dict(zip(names, fave_foods))
```
this line is easy but we need to change the for loop because its now in keys and values

``` python
for key, value in people.items():
	print(key + " : " + value)
```

the output will change to:

```
howard : pizza
dave : pork pies
michael : pudding
```

what ever was passed into the zip function first will become the key and the second will be the value

# extra notes

the zip function can take in more than 2 arguments however for the sake of simplicity I did not end up showing it here

as with anything to do with programming I recommend messing about with any functions shown here to really get a feel for them and how they can help you 

"what if I turn turn this zip object that has 3 things into a dictionary?" try it out and have some fun  