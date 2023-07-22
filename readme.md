This is an example showing how ruff and flake8-quotes incorrectly think that 
multiline strings following a variable definition in the class is not a docstring
see https://peps.python.org/pep-0257/ for the documentation

> String literals occurring elsewhere in Python code may also act as documentation.
> They are not recognized by the Python bytecode compiler and are not accessible as runtime object attributes (i.e. not assigned to __doc__),
> but two types of extra docstrings may be extracted by software tools:
> 1. String literals occurring immediately after a simple assignment at the top level of a module, class, or __init__ method are called “attribute docstrings”.
> 2. String literals occurring immediately after another docstring are called “additional docstrings”.

```
# pip install -r requirements.txt
```

```
# ruff main.py            
main.py:7:5: Q001 [*] Double quote multiline found but single quotes preferred
Found 1 error.
[*] 1 potentially fixable with the --fix option.
```

```
# flake8 main.py
main.py:7:5: Q001 Double quote multiline found but single quotes preferred
```