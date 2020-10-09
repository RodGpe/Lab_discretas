# Laboratorio Estructuras discretas

## Clase 2 

### ¿Qué es Haskell?
Es un lenguaje de programación puramente funcional multi-propósito.
Un lenguaje de programación es un conjunto de símbolos y reglas sintácticas y semánticas que definen su estructura y el significado de sus expresiones.
En un lenguaje de programación funcional, como su nombre lo indica, todas sus expresiones son funciones.
En Haskell una __función__ es un mapeo que toma uno o más __argumentos__ de un __tipo__ y produce una __expresión__ a través de instrucciones.
Un __tipo__ es un conjunto de elementos que son creados por una definición formal.

### Caracteristicas de Haskell

+ Programas concisos
+ Estáticamente tipado
+ Uso de listas por comprensión
+ Funciones recursivas
+ Permite el uso de funciones de orden superior (Funciones que aceptan funciones)
+ Funciones genéricas
+ Evaluación perezosas

## Historia

+ 1930, Alonzo Church desarrolla el cácluclo lambda. una simple pero poderosa teoria de funciones.
+ 1950, John McCarty desarrolla Lisp, reconocido como el primer lenguaje de programación funcional.
+ 1960, Peter Landin desarrolla ISWIM ("If you see what I mean"). El primer lenguaje puramente funcional.
+ 1970, John Backus desarrolla FP ("Functional Programming"), un lenguaje que hace énfasis en funciones de orden superior.
+ 1980, David Turner desarrolla un número de lenguajes perezosos.
+ 1987, Un comité internacional inicia el desarrollo de Haskell, nombrado así por Haskell Curry.
+ 2003, El comité de Haskell publica el Haskell Report, el cual define la esperada versión estable de Haskell.
+ 2010, Una versión revisada y actualizada del Haskell Report fue publicado.

Vale mencionar que McCarty, Backus y Milner recibieron el premio Turing, que es considerado el Nobel de computación.

### Entornos

GCH: (Glasgow Haskell Compiler) Más popular. ghci es el intérprete interactivo.
Página oficial [Haskell](https://www.haskell.org/)

### Interpretes
Es un programa que analiza un programa y lo ejecuta.

El intérprete toma un programa y lo convierten en código máquina hasta que sea necesario.

Es más sencillo, pero ineficiente a comparación del compilado.

### Instalación Haskell

```shell
$ sudo apt-get install ghc
$ sudo dnf install ghc
$ sudo pacman -S ghc
```

```shell
$ ghci Prelude > (Cargar módulos)
```

Comandos:
```shell
:l Carga un programa al intérprete.
:r Recarga un programa.
:q Cierra el intérprete.
:? Ayuda (:h).
:t Tipo de una expresión. Ejemplos…
:module + módulo Importar un módulo (import módulo)
```

### Standar prelude

Haskell viene con un gran número de funciones, las cuales estan definidas en un archivo llamado _standar prelude_ En adición a las funciones numéricas tales como `+` o `*`, el preludio provee funciones útiles para operar con listas. En Haskell, los elementos de una lista se encierran entre corchetes y son separados por comas como en `[1,2,3,4,5]`. Algunas de las funciones más usadas son:
```shell
> head [1,2,3,4,5]
1
> tail [1,2,3,4,5]
[2,3,4,5]
> [1,2,3,4,5] !! 2
3
> take 3 [1,2,3,4,5]
[1,2,3]
> drop 3 [1,2,3,4,5]
[4,5]
> length [1,2,3,4,5]
5
> sum [1,2,3,4,5]
15
> product [1,2,3,4,5]
120
> reverse [1,2,3,4,5]
[5,4,3,2,1]

```

### Aplicación de funciones

En matemáticas la aplicación de funciones es usualmente denotada encerrando los argumentos en parentesis, mientras que la multiplicación de dos valores se denota silenciosamente, escrbiendo los dos valores uno junto al otro. Por ejemplo, la expresión

<img src="https://latex.codecogs.com/svg.latex?\Large&space;f(a,b)+cd" title="\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" />

significa aplicar la función f a dos argumentos a y b, y sumarle el resultado el producto de c y d. Reflejando la idea central del lenguaje, la aplicación de función se denota silenciosamente usando espacio, mientras que la multiplicación de dos valores se denota con el operador `*`. Por ejemplo, la expresión anterior se escriben en haskell como: 

```haskell
f a b + c*d
```
Aún más, la aplicación de funciones tiene la mayor prioridad con los demás operadores en el lenguaje. Por ejemplo `f a + b` significa `(f a) + b` y no `f (a + b)`

La siguiente table ejemplifica aún más las diferencias en la aplicación de función en Haskell.

Matemáticas | Haskell
--- | ---
f(x) | f x
f(x,y) | f x y
f(g(x)) | f (g x)
f(x,g(y)) | f x (g y)
f(x)g(y) | f x * g y


```haskell
head [1,2,3,4,5]
```
Laboratorio de estructuras discretas 2021-1
```shell
ghci> False || True  
True   
```
Eso fue la shell
