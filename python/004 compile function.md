usage: 
``` python
compile(source, name, mode)
```
now this is some difficult stuff

source = a string of code
``` python 
random_string = "4 + 3"
random_string2 = "print('Hello, World!')"
```
just a genuine string 
this can either be put into the `compile()` function directly or stored in a variable

name = just a name that will be used if an error rises from the code

mode = 
1. `exec` - for multiple lines (e.g. scripts)
2. `eval` - for code that returns a value
3. `single` - for one line statements (stuff like `print("whatever")`)

eval & exec both have a file dedicated to them too 

#  example (single line)

``` python
code = compile("4 + 2", "random error name", "eval")
result = eval(code)
print(result)
```

output

```
6
```

# example (multi line)

``` python
script = """
for i in range(3):
	print(i)
"""

code = compile(script, "another error name", "exec")
exec(code)
```

in both of these you are technically generating code at run time

this is all well and good but there is cooler stuff you can do with this

# example (function generation)

``` python
script = """
def greet(name):
	return f"Hello, {name}"
"""

code_object = compile(source, "<generated function>", "exec")

# a namespace is kinda like how you type os.funcname os is the namespace there
ns = {} # empty 
exec(code_objcet, ns) # this has put greet() in the ns namespace

greeting = ns["greet"]("dr house")
print(greeting)
```

now this is might be the most complex hello function you might make ever

## how?

to put it simply 

``` python
code_object = compile(source, "<generated function?", "exec")
```
here we are storing out generated code inside an object
because this is a function it is not executed immediately 


``` python
ns = {} 
```

this is just a plain empty dictionary 

``` python
exec(code_object, ns)
```

this code is placing our code into the dictionary where

`key = function name`
`value = memory address of the code`

``` python
greeting = ns["greet"]("popular show reference")
```
here we are asking the `ns` namespace for the `greet` function and then we are supplying the arguments


and that is it

# notes

the `ns` is not needed however highly recommended since its a namespace that it kept separate from global stuff like variable names and function names.

nor does it need to be called `ns` it could be `stupidville` or something 