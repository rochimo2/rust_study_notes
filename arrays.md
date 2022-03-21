# Arrays

Una matriz es una colección de objetos del mismo tipo, que se almacenan secuencialmente en la memoria. La longitud o tamaño de una matriz es igual al número de elementos que esta contiene. El tamaño de una matriz se puede especificar en el código o calcularse mediante el compilador.

## Definición de una matriz

Una matriz se puede definir de dos maneras:

* Una lista de valores separados por comas, donde no se especifica la longitud.
* El valor inicial, seguido de punto y coma y, después, la longitud de la matriz.

En ambos casos, el contenido se pone entre corchetes [].

``` [rust]
// Declare array, initialize all values, compiler infers length = 7
let days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
  
// Declare array, initialize all values to 0, length = 5
let bytes = [0; 5];
``` 


En tiempo de compilación, la firma de una matriz se define como [T; size]:

* T es el tipo de datos de todos los elementos de la matriz.
    size es un entero no negativo que representa la longitud de la matriz.

La firma revela dos características importantes sobre las matrices:

* Todos los elementos de una matriz tienen el mismo tipo de datos. El tipo de datos nunca cambia.
    El tamaño de una matriz es fijo. La longitud nunca cambia.

Solo hay una cosa de una matriz que puede cambiar con el tiempo: **los valores de los elementos que contiene**. El tipo de datos sigue siendo constante y el número de elementos (longitud) permanece invariable. Solo los valores pueden cambiar.

## Indexación en una matriz

Los elementos de una matriz se numeran implícitamente a partir de 0. Usamos la indexación para acceder a los elementos de una matriz con la expresión `<array>[<index>]`. Por ejemplo, `my_array[0]` accede al elemento en el índice 0 de la variable my_array. La expresión devuelve el valor del elemento de matriz en esa ubicación de índice.

```
// Get the first day of the week
let first = days[0];
```

### Búsqueda de valores de índice fuera de los límites

Si intentamos acceder a un elemento de nuestra matriz con un índice que no está en el intervalo permitido, el compilador devuelve un error. 

Dado que la longitud de la matriz se conoce en tiempo de compilación, Rust hace imposible compilar cualquier programa que intente acceder a la matriz con un índice fuera de sus límites.

