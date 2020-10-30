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
abs' n = if n>= 0 then n else -n
```
Claro que puede ser escrita sobre la misma línea pero se lee mejor así:
```haskell
abs' n = if n>= 0
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

## Clase 4

### Introducción a los tipos de datos nuevos 

Hasta ahora hemos jugado con muchos tipos: `Bool, Int, Cha`, etc. Pero ¿Cómo los creamos? Bueno, una forma es usar la palabra clave `data` para definir un tipo. Vamos a ver como está definido el tipo Bool en la librería estándar:
```haskell
data Bool = False | True
```
data significa que vamos a definir un nuevo tipo de dato. La parte a la izquierda del = denota el tipo, que es Bool. La parte a la derecha son los constructores de datos. Estos especifican los diferentes valores que puede tener un tipo. El | se puede leer como una o. Así que lo podemos leer como: El tipo Bool puede tener un valor True o False. Tanto el nombre del tipo como el de los constructores de datos deben tener la primera letra en mayúsculas.

De la misma forma podemos pensar que el tipo Int está definido como:

```haskell
data Int = -2147483648 | -2147483647 | ... | -1 | 0 | 1 | 2 | ... | 2147483647
```
El primer y el último constructor de datos son el mínimo y el máximo valor posible del tipo Int. En realidad no está definido así, los tres puntos están ahí porque hemos omitido una buena cantidad de números, así que esto es solo para motivos ilustrativos.
Cargando...
Ahora vamos a pensar en como definiríamos una figura en Haskell. Una forma sería usar tuplas. Un círculo podría ser (43.1, 55.0, 10.4) donde el primer y el segundo campo son las coordenadas del centro del círculo mientras que el tercer campo sería el radio. Suena bien, pero esto nos permitiría también definir un vector 3D o cualquier otra cosa. Una solución mejor sería crear nuestro propio tipo que represente una figura. Digamos que una figura solo puede ser un círculo o un rectángulo:
```haskell
data Shape = Circle Float Float Float | Rectangle Float Float Float Float
```
¿Qué es esto? Piensa un poco a que se parece. El constructor de datos `Circle` tiene tres campos que toman valores en coma flotante. Cuando creamos un constructor de datos, opcionalmente podemos añadir tipos después de él de forma que estos serán los valores que contenga. Aquí, los primeros dos componentes son las coordenadas del centro, mientras que el tercero es el radio. El constructor de datos Rectangle tiene cuatro campos que aceptan valores en coma flotante. Los dos primeros representan las coordenadas de la esquina superior izquierda y los otros dos las coordenadas de la inferior derecha.
Ahora, cuando hablamos de campos, en realidad estamos hablando de parámetros. Los constructores de datos son en realidad funciones que devuelven un valor del tipo para el que fueron definidos. Vamos a ver la declaración de tipo de estos dos constructores de datos.
```shell
ghci> :t Circle
Circle :: Float -> Float -> Float -> Shape
ghci> :t Rectangle
Rectangle :: Float -> Float -> Float -> Float -> Shape
```
Bien, los constructores de datos son funciones como todo lo demás ¿Quíen lo hubiera pensado? Vamos a hacer una función que tome una figura y devuleva su superficie o área:
```haskell
surface :: Shape -> Float
surface (Circle _ _ r) = pi * r ^ 2
surface (Rectangle x1 y1 x2 y2) = (abs $ x2 - x1) * (abs $ y2 - y1)
```
La primera cosa destacable aquí es la declaración de tipo. Dice que toma una figura y devuelve un valor en coma flotante. No podemos escribir una declaración de tipo como Circle -> Float ya que Circle no es un tipo, Shape si lo es. Del mismo modo no podemos declarar una función cuya declaración de tipo sea True -> Int. La siguiente cosa que podemos destacar es que podemos usar el ajuste de patrones con los constructores. Ya hemos utilizado el ajuste de patrones con constructores anteriormente (en realidad todo el tiempo) cuando ajustamos valores como [], False, 5, solo que esos valores no tienen campos. Simplemente escribimos el constructor y luego ligamos sus campos a nombres. Como estamos interesados en el radio, realmente no nos importan los dos primeros valores que nos dicen donde está el círculo.
```shell
ghci> surface ( Circle 10 20 10 )
314.15927
ghci> surface ( Rectangle 0 0 100 100 )
10000.0
```
Bien ¡Funciona! Pero si intentamos mostrar por pantalla Circle 10 20 5 en una sesión de GHCi obtendremos un error. Esto sucede porque Haskell aún no sabe como representar nuestro tipo con una cadena. Recuerda que cuando intentamos mostrar un valor por pantalla, primero Haskell ejecuta la función show para obtener la representación en texto de un dato y luego lo muestra en la terminal. Para hacer que nuestro tipo Shape forme parte de la clase de tipo Show hacemos esto:
```haskell
data Shape = Circle Float Float Float | Rectangle Float Float Float Float deriving (Show)
```
No vamos a preocuparnos ahora mismo acerca de derivar. Simplemente diremos que si añadimos deriving (Show) al final de una declaración de tipo, automáticamente Haskell hace que ese tipo forme parte de la clase de tipos Show. Así que ahora ya podemos hacer esto:
```shell
ghci> Circle 10 20 5
Circle 10.0 20.0 5.0
ghci> Rectangle 50 230 60 90
Rectangle 50.0 230.0 60.0 90.0
```
Nuestro tipo de dato es bueno, pero podría se mejor. Vamos a crear un tipo de dato intermedio que defina un punto en espacio bidimensional. Luego lo usaremos para hacer nuestro tipo más evidente.
```haskell
data Point = Point Float Float deriving (Show)
data Shape = Circle Point Float | Rectangle Point Point deriving (Show)
```
Te habrás dado cuenta de que hemos usado el mismo nombre para el tipo que para el constructor de datos. No tiene nada de especial, es algo común usar el mismo nombre que el del tipo si solo hay un constructor de datos. Así que ahora Circle tiene dos campos, uno es el del tipo Point y el otro del tipo Float. De esta forma es más fácil entender que es cada cosa. Lo mismo sucede para el rectángulo. Tenemos que modificar nuestra función surface para que refleje estos cambios.
```haskell
surface :: Shape -> Float
surface (Circle _ r) = pi * r ^ 2
surface (Rectangle (Point x1 y1) (Point x2 y2)) = (abs $ x2 - x1) * (abs $ y2 - y1)
```
Lo único que hemos cambiado han sido los patrones. Hemos descartado completamente el punto en el patrón del círculo. Por otra parte, en el patrón del rectángulo, simplemente hemos usado un ajuste de patrones anidado para obtener las coordenadas de los puntos. Si hubiésemos querido hacer una referencia directamente a los puntos por cualquier motivo podríamos haber utilizado un patrón como.
```shell
ghci> surface (Rectangle (Point 0 0) (Point 100 100))
10000.0
ghci> surface (Circle (Point 0 0) 24)
1809.5574
```

¿Cómo sería una función que desplaza una figura? Tomaría una figura, la cantidad que se debe desplazar en el eje x, la cantidad que se debe desplazar en el eje y y devolvería una nueva figura con las mismas dimensiones pero desplazada.
```haskell
nudge :: Shape -> Float -> Float -> Shape
nudge (Circle (Point x y) r) a b = Circle (Point (x+a) (y+b)) r
nudge (Rectangle (Point x1 y1) (Point x2 y2)) a b = Rectangle (Point (x1+a) (y1+b)) (Point (x2+a) (y2+b))
```
Bastante sencillo. Añadimos las cantidades a desplazar a los puntos que representan la posición de las figuras.
```shell
ghci> nudge (Circle (Point 34 34) 10) 5 10
Circle (Point 39.0 44.0) 10.0
```
Si quisiéramos exportar las funciones y tipos que acabamos de crear en un módulo, podríamos empezar con esto:
```haskell
module Shapes
( Point(..)
, Shape(..)
, surface
, nudge
, baseCircle
, baseRect
) where
```
### Sintaxis de registro
```haskell
data Person = Person String String Int Float String String deriving (Show)
```
Puede escribirse como: 
```haskell
data Person = Person { firstName :: String
                     , lastName :: String
                     , age :: Int
                     , height :: Float
                     , phoneNumber :: String
                     , flavor :: String
                     } deriving (Show)
```
Lo que permite:
```shell
ghci> :t flavor
flavor :: Person -> String
ghci> :t firstName
firstName :: Person -> String
```


### Parámetros de tipo

Un constructor de datos puede tomar algunos valores como parámetros y producir un nuevo valor. Por ejemplo, el constructor Car toma tres valores y produce un valor del tipo coche. De forma similar, un constructor de tipos puede tomar tipos como parámetros y producir nuevos tipos.
```haskell
data Maybe a = Nothing | Just a
```
### Instancias derivadas

Un tipo puede ser una instancia de esa clase si soporta ese comportamiento. Ejemplo: El tipo Int es una instancia de la clase Eq, ya que la clase de tipos Eq define el comportamiento de cosas que se pueden equiparar. Y como los enteros se pueden equiparar, Int es parte de la clase Eq. La utilidad real está en las funciones que actúan como interfaz de Eq, que son == y /=. Si un tipo forma parte de la clase Eq, podemos usar las funciones como == con valores de ese tipo. Por este motivo, expresiones como 4 == 4 y "foo" /= "bar" son correctas.
Primero creamos nuestro tipo de dato y luego pensamos como qué puede comportarse. Si puede comportarse como algo que puede ser equiparado, hacemos que sea miembro de la clase Eq. Si puede ser puesto en algún orden, hacemos que sea miembro de la clase Ord.

Más adelante veremos como podemos hacer manualmente que nuestros tipos sean una instancia de una clase de tipos implementando las funciones que esta define. Pero ahora, vamos a ver como Haskell puede automáticamente hacer que nuestros tipos pertenezcan a una de las siguientes clases: Eq, Ord, Enum, Bounded, Show y Read. Haskell puede derivar el comportamiento de nuestros tipos en estos contextos si usamos la palabra clave deriving cuando los definimos.
```haskell
Considera el siguiente tipo de dato:
data Person = Person { firstName :: String
                     , lastName :: String
                     , age :: Int
                     }
 ```                    
Describe a una persona. Vamos a asumir que ninguna persona tiene la misma combinación de nombre, apellido y edad. Ahora, si tenemos registradas a dos personas ¿Tiene sentido saber si estos dos registros pertenecen a la misma persona? Parece que sí. Podemos compararlos por igualdad y ver si son iguales o no. Por esta razón tiene sentido que este tipo se miembro de la clase de tipo Eq. Derivamos la instancia:
```haskell
data Person = Person { firstName :: String
                     , lastName :: String
                     , age :: Int
                     } deriving (Eq)
```

Cuando derivamos una instancia de Eq para un tipo y luego intentamos comparar dos valores de ese tipo usando == o /=, Haskell comprobará si los constructores de tipo coinciden (aunque aquí solo hay un constructor de tipo) y luego comprobará si todos los campos de ese constructor coinciden utilizando el operador = para cada par de campos. Solo tenemos que tener en cuenta una cosa, todos los campos del tipo deben ser también miembros de la clase de tipos Eq. Como String y Int ya son miembros, no hay ningún problema. Vamos a comprobar nuestra instancia Eq.

```shell
ghci> let mikeD = Person {firstName = "Michael", lastName = "Diamond", age = 43}
ghci> let adRock = Person {firstName = "Adam", lastName = "Horovitz", age = 41}
ghci> let mca = Person {firstName = "Adam", lastName = "Yauch", age = 44}
ghci> mca == adRock
False
ghci> mikeD == adRock
False
ghci> mikeD == mikeD
True
ghci> mikeD == Person {firstName = "Michael", lastName = "Diamond", age = 43}
True
```

Vamos a hacer que nuestro tipo de dato Person forme parte también de las clases Show y Read.
```haskell
data Person = Person { firstName :: String
                     , lastName :: String
                     , age :: Int
                     } deriving (Eq, Show, Read)
```
                     
Ahora podemos mostrar una persona por la terminal.
```shell
ghci> let mikeD = Person {firstName = "Michael", lastName = "Diamond", age = 43}
ghci> mikeD
Person {firstName = "Michael", lastName = "Diamond", age = 43}
ghci> "mikeD is: " ++ show mikeD
"mikeD is: Person {firstName = \"Michael\", lastName = \"Diamond\", age = 43}"
```
Read es prácticamente la clase inversa de Show. Show sirve para convertir nuestro tipo a una cadena, Read sirve para convertir una cadena a nuestro tipo. Aunque recuerda que cuando uses la función read hay que utilizar una anotación de tipo explícita para decirle a Haskell que tipo queremos como resultado. Si no ponemos el tipo que queremos como resultado explícitamente, Haskell no sabrá que tipo queremos.
```shell
ghci> read "Person {firstName =\"Michael\", lastName =\"Diamond\", age = 43}" :: Person
Person {firstName = "Michael", lastName = "Diamond", age = 43}
```

Podemos usar fácilmente los tipos de dato algebraicos para crear enumeraciones, y las clases de tipos Enum y Bounded nos ayudarán a ello. Considera el siguiente tipo de dato:
```haskell
data Day = Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Sunday
```
Como ningún contructor de datos tiene parámetros, podemos hacerlo miembro de la clase de tipos Enum. La clase Enum son para cosas que tinen un predecesor y sucesor. Tambien podemos hacerlo miembro de la clase de tipos Bounded, que es para cosas que tengan un valor mínimo posible y valor máximo posible. Ya que nos ponemos, vamos a hacer que este tipo tenga una instancia para todas las clases de tipos derivables que hemos visto y veremos que podemos hacer con él.
```haskell
data Day = Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Sunday
           deriving (Eq, Ord, Show, Read, Bounded, Enum)
```
Como es parte de las clases de tipos Show y Read, podemos convertir valores de est tipo a y desde cadenas.
```shell
ghci> Wednesday
Wednesday
ghci> show Wednesday
"Wednesday"
ghci> read "Saturday" :: Day
Saturday
```

Como es parte de las clases de tipos Eq y Ord, podemos comparar o equiparar días.
```shell
ghci> Saturday == Sunday
False
ghci> Saturday == Saturday
True
ghci> Saturday > Friday
True
ghci> Monday `compare` Wednesday
LT
```
También forma parte de Bounded, así que podemos obtener el día mas bajo o el día más alto.
```shell
ghci> minBound :: Day
Monday
ghci> maxBound :: Day
Sunday
```
También es una instancia de la clase Enum. Podemos obtener el predecesor y el sucesor de un día e incluso podemos crear listas de rangos con ellos.
```shell
ghci> succ Monday
Tuesday
ghci> pred Saturday
Friday
ghci> [Thursday .. Sunday]
[Thursday,Friday,Saturday,Sunday]
ghci> [minBound .. maxBound] :: [Day]
[Monday,Tuesday,Wednesday,Thursday,Friday,Saturday,Sunday]
```
Bastante impresionante.

### Instanciar:
Cuando instanciamos, nosotros le indicamos a Haskell cuál va a ser el resultado del método usado, o sea, nosotros escribimos el cuerpo de los métodos usando instance Clase TipoUtilizado where
```haskell
data Time = TF Int Int | TW Int Int Bool

instance Show Time where
  show a = func a


func :: Time -> String
func (TF h m)   = show h ++ " : " ++ show m ++ " HRS"
func (TW h m b) = show h ++ " : " ++ show m ++ if b then "PM" else "AM"
```

TF 13 55 -> “13 : 55 HRS” TW 1 55 True -> 1 : 55 PM

## Clase 5

### Where y Let

Supongamos un ejemplo para caza de patrones y la formula para el indice de masa corporal
```haskell
imcDecir :: Float -> Float -> String
imcDecir masa altura
 | masa / altura ^ 2 <= 18.5 = "bajo de peso"
 | masa / altura ^ 2 <= 25.0 = "Estas bien"
 | masa / altura ^ 2 <= 30.0 = "Estas gordito"
 | otherwise                 = "Eres una ballenita" 
```
Aquí definimos 3 veces la misma función y lo pudimos escirbir así usando un `where` :
```haskell
imcDecir :: Float -> Float -> String
imcDecir masa altura
 | imc <= 18.5 = "bajo de peso"
 | imc <= 25.0 = "Estas bien"
 | imc <= 30.0 = "Estas gordito"
 | otherwise   = "Eres una ballenita" 
 where imc = masa / altura  ^ 2
 ```
 Podemos escribir varias definiciones en el mismo `where`.

```haskell
imcDecir :: Float -> Float -> String
imcDecir masa altura
 | imc <= flaco = "bajo de peso"
 | imc <= normal = "Estas bien"
 | imc <= gordito = "Estas gordito"
 | otherwise   = "Eres una ballenita" 
  where  imc = masa / altura  ^ 2
         flaco = 18.5
         normal = 25.0
         gordito = 30.0
 ```
 
 ### Let in
 Muy similar es un `where`. La diferencia es que Let es más local, no se puede usar en guardas.
 
 ```haskell
cilindro :: Float -> Float -> Float  
cilindro r h = 
    let areaLateral = 2 * pi * r * h  
        areaSuperior = pi * r ^2  
    in  areaLateral + 2 * areaSuperior  
```
### Recursión 

Ejemplo de una función recursiva
```haskell
factorial :: Integer -> Integer
factorial 0 = 1
factorial n = n * factorial (n - 1)
```
