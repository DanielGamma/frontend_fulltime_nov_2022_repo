![](../../assets/Logo_Yellow.png)

# Ejercicios JS - Destructuring

### Exercise 1
Reescribe el código para usar `destructuring` en vez de asignar cada variable individualmente.
```javascript
let item = ["Egg", 0.25, 12];
let name = item[0];
let price = item[1];
let quantity = item[2];

console.log(`Item: ${name}, Quantity: ${quantity}, Price: ${price}`);
```

### Exercise 2
Reescribe el código para asignar a cada variable el número correcto.
```javascript
let numbers = [3, 5, 4, 2, 6, 1];
let [one, two, three, four, five, six] = numbers;

console.log(`One: ${one}, Two: ${two}, Three: ${three}, Four: ${four}, Five: ${five}, Six: ${six}`);
```

### Exercise 3
Tenemos el objeto `user`. Desestructura sus propiedades en las variables `name`, `age` y `isAdmin` (esta última no existe, tendrás que crear un valor predeterminado `false`).
```javascript
let user = { name: "John", years: 30 };

let {} = user;

console.log(name); // John
console.log(age); // 30
console.log(isAdmin); // false
```

### Exercise 4
Reescribe el código para desestructurar el array.
```javascript
let person = [12, "Chris", "Owen"];

let firstName = person[1];
let lastName = person[2];
let age = person[0];

console.log(`Person - Age: ${age}, Name: ${firstName} ${lastName}`);
```

### Exercise 5
Reescribe el código para usar `desestructuring`, teniendo en cuenta que no debes crear ninguna variable vacía:
```javascript
let person = ["Chris", 12, "Owen"];

let firstName = person[0];
let lastName = person[2];

console.log(`Name: ${firstName} ${lastName}`);
```

### Exercise 6
Desestructura el último elemento del array.
```javascript
const students = ['Christina', 'Jon', 'Alexandare'];

const [] = students;

console.log(lastName);
```

### Exercise 7
Usando `destructuring`, obtén sólo los nombres de los arrays dentro del array.
```javascript
const moreStudents = [
	'Chris',
	['Ahmad', 'Antigoni'],
	['Toby', 'Sam']
];

const [] = moreStudents;

console.log(student1, student2, student3, student4, student5);
```