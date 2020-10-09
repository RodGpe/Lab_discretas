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

Haskell viene con un gran número de funciones, las cuales estan definidas en un archivo llamado _standar prelude_ En adición a las funciones numéricas tales como `+` o `*`
```haskell
head [1,2,3,4,5]
```
Laboratorio de estructuras discretas 2021-1
```shell
ghci> False || True  
True   
```
Eso fue la shell
