# Laboratorio Estructuras discretas

## Clase 2 

### ¿Qué es Haskell?
Es un lenguaje de programación puramente funcional multi-propósito.
Un lenguaje de programación es un conjunto de símbolos y reglas sintácticas y semánticas que definen su estructura y el significado de sus expresiones.
En un lenguaje de programación funcional, como su nombre lo indica, todas sus expresiones son funciones.
En Haskell una __función__ es un mapeo que toma uno o más __argumentos__ de un __tipo__ y produce una __expresión__ a través de instrucciones.
Un __tipo__ es un conjunto de elementos que son creados por una definición formal.

### Instalación Haskell

```shell
$ sudo apt-get install ghc
$ sudo dnf install ghc
$ sudo pacman -S ghc
```

```math
a^2+b^2=c^2
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
```haskell
doubleSmallNumber x = if x > 100  
                        then x  
                        else x*2   
```
Laboratorio de estructuras discretas 2021-1
```shell
ghci> False || True  
True   
```
Eso fue la shell
