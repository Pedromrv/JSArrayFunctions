
![imgMeme](img/meme.png)
  

# JavaScript Map, Reduce, and Filter - JS Array Functions Explicadas con Ejemplos de Código

## Map

El método `map()` se utiliza para crear un nuevo array a partir de uno existente, aplicando una función a cada uno de los elementos del primer array.

### Syntax

```javascript
let new_array = arr.map(function callback(element, index, array) {
    // Return value for new_array
}[, thisArg])
```

En el callback, sólo se requiere el array `element`. Normalmente se realiza alguna acción sobre el valor y luego se devuelve un nuevo valor.

### Ejemplo 

En el siguiente ejemplo, cada número del array se duplica.

```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(item => item * 2);
console.log(doubled); // [2, 4, 6, 8]
```

## Filter

El método `filter()` toma cada elemento de un array y aplica una sentencia condicional contra él. Si esta condicional devuelve true, el elemento es empujado al array de salida. Si la condición es falsa, el elemento no se envía a la matriz de salida. 

### Syntax

```javascript
let new_array = arr.filter(function callback(element, index, array) {
    // Return true or false
}[, thisArg])
```

La sintaxis de `filter` es similar a la de `map`, excepto que la función de callback de llamada debe devolver `true` para mantener el elemento, o `false` en caso contrario. En el callback, sólo se requiere  `element`. 

### Ejemplos

En el siguiente ejemplo, se "filtran" los números impares, dejando sólo los pares.

```javascript
const numbers = [1, 2, 3, 4];
const evens = numbers.filter(item => item % 2 === 0);
console.log(evens); // [2, 4]
```

En el siguiente ejemplo, se utiliza `filter()` para obtener todos los alumnos cuyas notas son mayores o iguales a 90.

```javascript
const students = [
  { name: 'Quincy', grade: 96 },
  { name: 'Jason', grade: 84 },
  { name: 'Alexis', grade: 100 },
  { name: 'Sam', grade: 65 },
  { name: 'Katie', grade: 90 }
];

const studentGrades = students.filter(student => student.grade >= 90);
return studentGrades; // [ { name: 'Quincy', grade: 96 }, { name: 'Alexis', grade: 100 }, { name: 'Katie', grade: 90 } ]
```

## Reduce

El método `reduce()` reduce un array de valores a un solo valor. Para obtener el valor de salida, ejecuta una función reductora en cada elemento del array.

### **Syntax**

```javascript
arr.reduce(callback[, initialValue])
```

El argumento `callback` es una función que será llamada una vez por cada elemento del array. Esta función toma cuatro argumentos, pero a menudo sólo se utilizan los dos primeros.

-  _accumulator_ - el valor devuelto de la iteración anterior
- _currentValue_ - el elemento actual de la matriz
- _index_ - el índice del elemento actual
- _array_ - el array original sobre el que se llamó a reducir
- El argumento `initialValue` es opcional. Si se proporciona, se utilizará como valor inicial del acumulador en la primera llamada a la función de devolución de llamada.

### Ejemplos

El siguiente ejemplo suma todos los números de una matriz de números.

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce(function (result, item) {
  return result + item;
}, 0);
console.log(sum); // 10
```

En el siguiente ejemplo, `reduce()` se utiliza para transformar un array de cadenas en un único objeto que muestra cuántas veces aparece cada cadena en el array. Observe que esta llamada a reduce pasa un objeto vacío `{}` como parámetro `initialValue`. Éste se utilizará como valor inicial del acumulador (el primer argumento) que se pasa a la función callback.

```javascript
let pets = ['dog', 'chicken', 'cat', 'dog', 'chicken', 'chicken', 'rabbit'];

let petCounts = pets.reduce(function(obj, pet){
    if (!obj[pet]) {
        obj[pet] = 1;
    } else {
        obj[pet]++;
    }
    return obj;
}, {});

console.log(petCounts); 

/*
Output:
 { 
    dog: 2, 
    chicken: 3, 
    cat: 1, 
    rabbit: 1 
 }
 */
```

En pocas palabras,

filter: Cuando se necesita eliminar algún elemento no deseado del array.
map: Convierte un array en otro.
reduce: Cuando se necesita reducir el array.

## Ejercicios

