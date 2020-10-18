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

### Tipos primitivos
+ Int (enteros)
+ Float/Double
+ Bool
+ Char (caracteres)
+ “String” ([Char]) (Cadenas de texto)
+ (t1, t2, …, tn) tuplas (tamaño específico)
+ [t1, t2, …, tn] listas (tamaño variable Y mismo tipo)

### Operadores 
Tipoes de operadores:

+ `+` Suma.
+ `-` Resta.
+ `*` Producto.
+ `**` Potencia en “reales”.
+ `div` División en enteros.
+ `/` División en “reales”.
+ `<` Menor qué.
+ `<=` Menor o igual qué. (<=)
+ `>` Mayor qué.
+ `>=` Mayor o igual qué. (>=)
+ `==` Igualdad (==)
+ `++` Concatenación.
+ `\\` Diferencia entre listas (Import Data.List)

Usar `:t` dentro del interprete para consultar el tipo. Ej 
```shell
Prelude> :t 3.0
3.0 :: Fractional t => t
Prelude> :t pi
pi :: Floating a => a
```
Ejemplo de una función en haskell

```haskell
succN n = n +1  
doble x = x + x
doble2 x = x * 2
```
Cómo se evalua la función
 
```haskell
--sustitución
doble(x) = x + x
doble(4) = 4 + 4
head [1,2,3,4,5]
```

Más ejemplos:

```haskell
1 + 8
9

--prefija
(+) 1 14
15

(1.0 + 3) == (2 +2)

div 4 2

4 `div` 2

[1,2,3] ++ "amigo"

```
### Clases

Una clase es una interfaz que define algún comportamiento. Ej
+ Eq
+ Ord
+ Enum

## Clase 3

Sobre la clase pasada:

Los operadores y las funciones utilizan en su mayoria notación prefija:
Ej
```haskell
--suma de 2 números
(+) 1 2

--concatenación de 2 listas
(++)  [1,2] [3,4]

--Aplicar la función suma a dos números
suma 1 2
```

Si bien esta manera nos garantiza consistencia sacrifica facilidad de lectura, por ejemplo 

```haskell
(div) 4 2 
```
no queda claro quien es el numerador y el denomidador, pero si lo escribimos así:

```haskell
4 `div` 2
```
Se lee claramente que 4 se divide entre 2

Para usar la notación infija se tiene que encerrar la función entre comillas invertidas \`  \`  .

La precedencia de las operaciones es la que normalmente se usa en matemátcias, es decir `2 * 3 + 4` es equivalente a `(2 * 3) + 4`. La aplicación de funciones tiene la mayor precedencia, por ejemplo, `2 * suma 3 4` es equivalente a `2 * ( 3 + 4 )`.

### Más sobre clases tipos y clases

Un tipo es una colección de valores que se relacionan. Por ejemplo, el tipo `Bool` contiene los dos valores lógicos `False` y `True` mientras que el tipo `Bool -> Bool` contiene todas las funciones que mapean argumentos de `Bool` a resultados de `Bool` tal como la es la función de negación. Usamos la notacin `v :: T` que significa que el valor de `v` es de tipo `T` y se lee, _v es de tipo T_. Por ejemplo 
```haskell
False :: Bool

not :: Bool -> Bool
```
En haskell __toda expreción debe tener un tipo__ que es calculado antes de la evaluación de la expresión por un proceso llamado _inferencia de tipos_

Una tupla es una secuencia finita de componentes con posibles tipos distintos.

## Currificación

Toda función en haskell toma exactamente un argumento y regresa una expresión que puede ser otra función o un tipo específico.
Así que ¿Como es posible que hayamos definido y usado varias funciones que toman mas de un parámetro? Bueno ¡Es un buen truco! Todas las funciones que hemos usado hasta el momento y aceptaban más de un parámetro han sido funciones currificadas.
En la ciencia de la computación, currificar es la técnica inventada por Moses Schönfinkel y Gottlob Frege que consiste en transformar una función que utiliza múltiples argumentos (o más específicamente una n-tupla como argumento) en una secuencia de funciones que utilizan un único argumento. (Eso es la operación inversa a la composición de funciones en matemáticas).

El nombre "currificar", acuñado por Christopher Strachey en 1967, es una referencia al lógico Haskell Curry. 

En matemáticas, dada una función _f_ del tipo _f:(X __x__ Y)-> Z_, currificándola sería una función del tipo _f: X -> (Y -> Z)_. En otras palabras, _curry(f)_ toma un argumento del tipo _X_  y retorna una función del tipo _Y -> Z_. Descurrificar es la transformación inversa.

Intuitivamente, la currificación expone que "Si fijas algunos argumentos, tendrás una función de los argumentos restantes". Por ejemplo, si la función div significa la versión currificada de la operación x / y, entonces div con el parámetro x fijado en 1 es otra función: igual que la función inv que devuelve la inversa multiplicativa de sus argumentos, definida por inv(y) = 1 / y.

En haskell entonces son equivalentes las siguientes firmas

```haskell
--funciones que suman 3 numeros

suma :: Int -> Int -> Int -> Int
suma x y z = x + y + z

suma' :: Int -> (Int -> (Int -> Int))
suma' x y z = x + y + z
```

Además de ser interesantes por sí mismas las funciones currificadas son más flexibles que, digamos, funciones en tuplas, porque funciones pueden ser parcialmente aplicadas con menos de sus argumentos completos. For ejemplo, la función  que incrementa un entero por 1 puede ser dado mediante la aplicación parcial  de `suma 1 :: Int -> Int`.
 ### Sobrecargando tipos
 
 El operador aritmético `+` calcula la suma de cualesquiera dos números del mismo tipo numerico.
 ```console
 > 1 + 2
 3
 > 1.0 + 2.0
 3.0
 ```
 La idea de que `+` puede ser aplicada a cualquier número de tipo numerico es precisada en su tipo mediante al inclusión de una _restricción de clase_. Las restricciones de clase son escritas de la forma `C a` donde `C` es el nombre de una clase y `a` es una variable de tipo. Por ejemplo, el tipo de la adición es la siguiente.
 ```haskell
 (+) :: Num a => a -> a -> a
 ```
 Esto es, para cualquier tipo `a` que es una _instancia_ de la clase `Num` de tipos numericos, la función `(+)` tiene un tipo `a -> a -> a`.
 Un tipo que tiene una o más restricciones de clase se llama _sobrecargado_, así como una expresión con tal tipo. Por lo tanto `Num a => a -> a -> a` es un tipo sobrecargado y `(+)` es una función sobrecargada. Más general, la matoria de las funciones numericas que tiene Prelude son sobrecargadas. Por ejemplo 
 ```haskell
 (*)   :: Num a => a -> a -> a
negate :: Num a => a -> a
abs    :: Num a => a -> a
 ```
Los números por sí mismos son sobrecargados, es decir que `3 :: Num a => a` signigifica que para cualquier tipo numerico `a`, el valor `3` tiene tipo `a`. Así el valor `3` puede ser un Int, Float o más general un valor de cualquier tipo numérico. Dependiendo del contexto en el que sea usado.

### Clases básicas
Recuerda que un tipo es una colección de valores que se relacionan. Sobre esta noción, una clase es una collección de tipos que soportan ciertas operaciones sobrecargadas llamadas _metodos_. Haskell provee de clases que están ya en el lenguaje:

La clase `Eq` que tiene los siguiente métodos:
```haskell
(==) :: a -> a -> Bool
(/=) :: a -> a -> Bool
```

La clase `Ord` que tiene los siguientes métodos:
```haskell
(<) :: a -> a -> Bool
(<=) :: a -> a -> Bool
(>) :: a -> a -> Bool
(>=) :: a -> a -> Bool
min :: a -> a -> a
max :: a -> a -> a
```
La clase `Show` que tiene los siguiente métodos:
```haskell
show :: a -> String
```

La clase `Read` que tiene los siguientes métodos:
```haskell
read :: String -> a
```

La clase `Num` que tiene los siguientes métodos:
```haskell
(+) :: a -> a -> a
(-) :: a -> a -> a
(*) :: a -> a -> a
negate :: a -> a
abs :: a -> a
signum :: a -> a
```

La clase `Integral` que tiene los sguientes métodos:
```haskell
div :: a -> a -> a
mod :: a -> a -> a
```

La clase `Fractional` que tiene los siguientes métodos:
```haskell
(/) :: a -> a -> a
recip :: a -> a
```

### Guardas o guardias
Haskell tiene distintas maneras de definir una función que escogen entre un número de posbiles resultados. La más sencilla son la _expresiones condicionales_ las cuales usan una expresión lógica llamada _condición_ que escoge entre dos resultados del mismo tipo.
Si la condición es `True` entonces se escoge la primera y si es `False` entonces la segunda se escoge. Por ejemplo:
```haskell
abs' :: Int -> Int
abs' = if n>= then n else -n
```
Claro que puede ser escrita sobre la misma línea pero se lee mejor así:
```haskell
abs' = if n>= 0
       then n
       else -n
```
Además de que podemos anidar las condicionales, por ejemplo una función que regresa el signo de un entero:
```haskell
signum :: Int -> Int
signum n = if n < 0 
           then -1 
           else
           if n == 0 then 0 else 1
```
### Expresiones con guardas
Como alternativa de usar expresiones condicionales las funciones también pueden ser definidas usando _expresiones con guardas_, en cuales una secuencia de expresiones lógicas llamadas _guardas_ son usadas para elegir entre una secuencia de resultados del mismo tipo. Por ejemplo:
```haskell
abs' n  | n>= 0     = n
        | otherwise = -n
```
El simbolo `|` se lee _tal que_ y la guarda `otherwise` esta definida en el preludio que siempre se evalua a verdadero, `otherwise = True`. No es necesario terminar con `otherwise` pero es una manera conveniente de cachar todos los casos no considerados antes.

El benficio principal de usar guardas es que las expreciones con multiple guardas son mucho más fácil de leer. Por ejemplo:

```haskell
signum n | n < 0   = -1
         | n == 0  = 0
         | otherwise = 1
```

### Ajuste o caza de patrones

Muchas funciones tienen una simple e intuitiva definición usando _ajuste o caza de patrones_, en el cual una secuencia de expresiones sintanticas llamadas _patrones_ son usadas para escoger entre una secuencia de resultados del mismo tipo. Si el primer patrón _ajusta o caza_ entonces el primer resultado se escoge. Por ejemplo, el operador `not` que regresa la negación de dos valores lógicos puede definirse así.
```haskell
not' :: Bool -> Bool
not' False = True
not' True = False
```
Funciones con más de un argumento tambíen puede usar caza de patrones. Por ejemplo la función conjunción lógica `conj`,
```haskell
conj :: Bool -> Bool -> Bool

conj True  True    = True
conj True  False   = False
conj False  True   = False
conj False  False  = False
```
Pero, esta definición puede ser simplificada si combinamos las últimas tres ecuaciones en una sola ecuación que regrese `False` independientemente de los valores de sus dos argumentos, usando _patrón comodín_ que caza con cualquier valor:

```haskell
True $$ True = True 
_    $$  _   = False
```
#### Patrones el tuplas

Una tupla de patrones en sí un patrón, el cual caza cualquier tupla de la misma aridad cuyos componentes todos cazan el corrrespondiente patrón en orden. Por ejemplo Prelude tiene la función `fst` y `snd` que regresa el primer y el segundo componenete de un __Par__ o dupla.

```haskell
fst :: (a,b) -> a
fst (x,_) = x

snd :: (a,b) -> b
snd (_,y) = y
```

### Alias
```haskell
type R2 = (Double, Double)
type PhoneBook = [(String,String)]  
```

### Buenas prácticas
+ Nombres de funciones empiezan con minusculas
+ Nombre de los type inician con mayúscula
+ Toda función debe tener una firma
+ Comentarios descriptivos
+ Estructura

```haskell
--comentarios iniciales
module Nombre where
-- Tipos definidos
-- Funciones principales
-- Funciones auxiliares
-- Ejemplos
```

Para definir un nuevo tipo de dato
```haskell
data Formula = 
 Prop Var
 | Neg Formula
 | Formula :$: Formula
 | Formula :|: Formula
 | Formula :=>: Formula
 | Formula :<=>: Formula derving (Show, Eq, Ord)
```
