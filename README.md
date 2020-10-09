# Laboratorio Estructuras discretas

## Clase 2 

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
