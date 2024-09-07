# R12
Reto 12 Programación

## Consulta de Metodos de Strings:
### endswith():
Devuelve True si el string termina con el substring especificado, de lo contrario, devuelve False.
```python
"programming.py".endswith(".py")  # True
"document.txt".endswith(".doc")   # False
```
### startswith()
Devuelve True si el string comienza con el substring especificado, de lo contrario, devuelve False.
```python
"2024 year".startswith("2024")    # True
"Hello there".startswith("hello") # False 
```
### isalpha()
Devuelve True si todos los caracteres en el string son letras del alfabeto (sin incluir espacios, números o símbolos), de lo contrario, devuelve False.
```python
"Python".isalpha()    # True
"Python 3".isalpha()  # False (por el espacio y el número)
```
### isalnum
Devuelve True si todos los caracteres en el string son alfanuméricos (letras o números) y no hay espacios ni símbolos, de lo contrario, devuelve False.
```python
"Python3".isalnum()   # True
"Python 3".isalnum()  # False (por el espacio)
```
### isdigit
Devuelve True si todos los caracteres del string son dígitos (números), de lo contrario, devuelve False.
```python
"123456".isdigit()    # True
"123.45".isdigit()    # False (por el punto)
```
### isspace
Devuelve True si el string solo contiene caracteres de espacio en blanco, de lo contrario, devuelve False.
```python
"\t\n ".isspace()     # True (tabulaciones y saltos de línea son espacios en blanco)
" no spaces ".isspace()  # False
```
### istitle
Devuelve True si el string sigue el formato de título (cada palabra comienza con una letra mayúscula seguida de minúsculas), de lo contrario, devuelve False.
```python
"A New Beginning".istitle()   # True
"a New Beginning".istitle()   # False (la primera palabra no está capitalizada)
```
### islower
Devuelve True si todos los caracteres del string son minúsculas y hay al menos un carácter, de lo contrario, devuelve False.
```python
"hello world".islower()   # True
"Hello World".islower()   # False (hay mayúsculas)
```
### isupper
Devuelve True si todos los caracteres del string son mayúsculas y hay al menos un carácter, de lo contrario, devuelve False.
```python
"WELCOME".isupper()       # True
"WELCOME!".isupper()      # True (los signos de exclamación no afectan el resultado)
```

## Procesar Archivo
