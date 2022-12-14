![](../../assets/Logo_Yellow.png)

# Objects

## ¿Qué es un objeto?
Un `objeto` es un tipo de dato de JavaScript que sirve para almacenar otros datos (strings, numbers, booleans, arrays, etc.). Sin embargo, los `objetos` tienen ciertas particularidades.  
A diferencia de los arrays, los objetos no tienen índices para ordenar los datos en su interior y, por lo tanto, tampoco tienen lenght.   
¿Cómo se estructuran los datos dentro de un objeto, entonces? Mediante pares de key / value, es decir, asignando a cada valor un nombre que lo identifica:
```javascript
const user = {
	name: "John",
	lastname: "Doe",
	age: 24,
	isMarried: false
}
```
Como se ve, los obejetos se declaran entre llaves `{}`. Dentro, para cada dato que queramos guardar (el valor o **value**), debemos asignarle un nombre que lo identifique (la clave o **key**): `name: "John"`. El string "John" está guardado bajo la **key** "name" (el nombre de la key se lo damos nosotros, podría ser cualquiera, pero lo suyo es que sea descriptivo de lo que contiene).
De este modo, todos lo datos guardados en un objeto tienen una **key** que les identifica y nos permite acceder a su valor.

Como decíamos antes, los objetos no tienen índices, y por lo tanto no tienen length:
```javascript
const user = {
	name: "John",
	lastname: "Doe",
	age: 24,
	isMarried: false
}

console.log(user[1]); // undefined
console.log(user.length); // undefined
```


### Acceder y modificar un objeto
Accedemos a un objeto como a cualquier otra variable, y a cada uno de sus valores mediante sus **keys**. Si queremos saber cuál es el `name` del objeto `user`, podemos hacerlo llamando al objeto y especificando la clave con un punto:
```javascript
const user = {
	name: "John",
	lastname: "Doe",
	age: 24,
	isMarried: false
}

console.log(user.name); // "John"
console.log(user.age); // 24
```

Para modificar el valor de un objeto, o crear una nueva propiedad:
```javascript
user.age = 31;
user.friends = ["Peter", "Anna", "Jack"];

console.log(user.age); // 31
console.log(user.friends); // ["Peter", "Anna", "Jack"]
```

Los objetos pueden tener dentro otros objetos. Para acceder a ellos, lo hacemos en orden:
```javascript
const users = {
  Alex: {
    email: 'alex@alex.com',
    age: 20
  },
  Paul: {
    email: 'paul@paul.com',
    age: 25
  }
}

console.log(users.Alex.age);    // 20
console.log(users.Paul.email);  // 'paul@paul.com'
```

También pueden contener arrays. Para acceder a ellas, primero entramos en la propiedad que tiene el array, y luego en el array mismo:
```javascript
const user = {
	name: "Alex",
    age: 20,
    skills: ["HTML", "CSS", "JavaScript"]
}

console.log(user.skills);      // ["HTML", "CSS", "JavaScript"]
console.log(user.skills[1]);   // "CSS"
```

### Borrar una propiedad de un objeto
No existe ningún método para borrar propiedades de objetos, pero sí existe el operador `delete`:
```javascript
const cat = {
	name: "Patty",
	legs: 4
}

delete cat.legs;

console.log(cat); // { name: "Patty" }
```


## Métodos de objeto
Hay muchos métodos de objeto, por lo que nos centraremos en los más comunes:

#### `hasOwn()`
Con este método podemos preguntar si el objeto tiene una determinada propiedad o **key**. Devuelve un booleano:
```javascript
const cat = {
	name: "Patty",
	legs: 4
}

console.log(Object.hasOwn(cat, "legs")); // true
console.log(Object.hasOwn(cat, "foods")); // false
```

Como habrás visto, el método no se llama sobre el objeto (`cat.hasOwn()`), si no que se aplica sobre `Object` (que es el prototipo general de objeto) y se especifica el objeto particular en los argumentos. Esto será así para todos los métodos de objeto.

#### `keys()`
Devuelve un array con las **keys** del objeto:
```javascript
const cat = {
	name: "Patty",
	legs: 4
}

console.log(Object.keys(cat)); // ["name", "legs"]
```

#### `values()`
Devuelve un array con los valores del objeto:
```javascript
const cat = {
	name: "Patty",
	legs: 4
}

console.log(Object.values(cat)); // ["Patty", 4]
```

#### `entries()`
Devuelve un array que contiene las keys y values del objeto:
Devuelve un array con las **keys** del objeto:
```javascript
const cat = {
	name: "Patty",
	legs: 4
}

console.log(Object.entries(cat)); // [["name", "Patty"], ["legs", 4]]
```

### Creación métodos de objeto
Además de los métodos que acabamos de ver, podemos construir nuestros propios métodos. Para ello, no tenemos más que crear una función dentro del objeto:
```javascript
const person = {
	name: "John",
	age: 35,
	sayHi() {
		console.log("Hi!");
	}
}

person.sayHi();   // Hi!
```

Si queremos hacer referencia a una propiedad interna del propio objeto, podemos hacerlo usando `this` para referirnos al objeto:
```javascript
const person = {
	name: "John",
	age: 35,
	sayName() {
		console.log("Hello, I'm " + this.name);
	}
}

person.sayName();  // Hello, I'm John
```

### Acceder a un objeto con `[]`
A veces no podemos acceder a los valores de un objeto usando el punto (`user.name`, `user.age`). Veamos un ejemplo:
```javascript
const user = {
"name" = "Paco",
"lastName-1": "García",
"lastName-2": "López"
}
```

Si usáramos el punto para acceder a la propiedad `lastName-1`, JS lo leería como una resta y devolvería NaN (not a number), ya que se estaría intentando restar 1 a lastName:
```javascript
console.log(user.lastName-1); // NaN
```

Lo mismo ocurriría si quisiérmos acceder usando una variable:
```javascript
const user = {
	"name" = "Paco"
}

const prop = "name";

console.log(user.prop); // undefined
```

Para estos casos, podemos usar `[]` para acceder a los valores del objeto:
```javascript
const user = {
	"name" = "Paco",
	"lastName-1": "García",
	"lastName-2": "López"
}

const prop = "name";

console.log(user[prop]); // "Paco"
console.log(user["lastName-1"]); // "García"
```

### Loopear un objeto
Dado que los objetos no tienen índices cómo los arrays, puede parecer que no son iterables con un bucle que recorra todas sus propiedades. Pero, esto no es así. Ya hemos visto el método `keys()` que devuelve un array con todas las claves del objeto. Podemos usar ese array para loopear el objeto y sacar todos sus valores:
```javascript
const user = {
	name: "John",
	lastname: "Doe",
	age: 24,
	isMarried: false
}

const keys = Object.keys(user);

for (let i = 0; i < keys.length; i++) {
	console.log(user[keys[i]]);
}
```

Este script irá imprimiendo por consola todos los valores del objeto, usando cada **key** para acceder a ellos.
