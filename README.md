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
### Consonantes Y Vocales
```python
def voc(a, c):
    # Inicializa el contador de letras a 0
    k = 0
    
    # Asigna el parámetro 'a' (cadena de caracteres) a 'l'
    l: str = a
    
    # Itera sobre cada carácter en 'l'
    for i in l:
        # Suma el número de veces que el carácter 'i' aparece en la cadena 'c'
        k += c.count(i)
    
    # Devuelve el total de caracteres contados
    return k

if __name__ == "__main__":
    # Abre el archivo "mbox.txt" en modo lectura y lo asigna a 'file'
    with open("mbox.txt", "r") as file:
        # Lee todo el contenido del archivo y lo convierte a minúsculas
        c = file.read().lower()  
    
    # Llama a la función 'voc' para contar la cantidad de vocales en 'c'
    l = voc("aeiou", c)
    
    # Llama a la función 'voc' para contar la cantidad de consonantes en 'c'
    m = voc("bcdfghjklmnpqrstvwxyz", c)

    # Imprime la cantidad total de vocales encontradas
    print(f"Cantidad de Vocales: {l}")
    
    # Imprime la cantidad total de consonantes encontradas
    print(f"Cantidad de Consonantes: {m}")
```
### 50 Palabras mas repetidas 
```python
def mostwords(a, n):
    # Abre el archivo especificado por 'a' en modo lectura
    with open(a, "r") as file:
        # Lee todo el contenido del archivo y convierte el texto a minúsculas
        tx = file.read().lower()

    # Define los delimitadores para dividir el texto
    d = " \t\n\r,.!?;:"
    # Reemplaza cada delimitador con un espacio en blanco
    for i in d:
        tx = tx.replace(i, " ")
    # Divide el texto en palabras usando los espacios como delimitadores
    pb = tx.split()

    # Crea un diccionario para contar la frecuencia de cada palabra
    cnum = {}
    for plb in pb:
        if plb in cnum:
            # Si la palabra ya está en el diccionario, incrementa su contador
            cnum[plb] += 1
        else:
            # Si la palabra no está en el diccionario, añádela con un contador de 1
            cnum[plb] = 1

    # Ordena el diccionario de palabras por frecuencia en orden descendente
    po = sorted(cnum.items(), key=lambda x: x[1], reverse=True)

    # Obtiene las 'n' palabras más comunes
    pmc = po[:n]
    return pmc

if __name__ == "__main__":
    # Nombre del archivo que se va a analizar
    a = "mbox.txt"
    # Llama a la función 'mostwords' para obtener las 50 palabras más frecuentes
    pmb = mostwords(a, 50)
    # Imprime cada palabra y su frecuencia
    for p, f in pmb:
        print(f"{p}: {f}")
```
