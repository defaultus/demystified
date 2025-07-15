
exec is the same as eval just that exec is meant to run actual python code

usage:

``` python
exec("print('Hello, World!'))
```

exec is meant for 
1. full python code
2. returns nothing
3. functions / classes / any multi line code

which is why it was used in our `compile()` function example