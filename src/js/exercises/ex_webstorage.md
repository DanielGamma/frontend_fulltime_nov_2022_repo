![](../../assets/Logo_Yellow.png)

# Ejercicios DOM - WebStorage

### Ejercicio 1
Introduce en `LocalStorage` 3 variables distintas (no en forma de objeto) con tu nombre, edad y ciudad de origen.

### Ejercicio 2
- En tu archivo JS, crea la variable `counter` y asígnale un valor de `5`. Guárdala en `LocalStorage`.
- Muestra el contenido del `LocalStorage` en HTML.
- Ahora crea un botón que, cuando sea pulsado, aumente dicho contador en `1`. El aumento se producirá en `LocalStorage`, y el HTML debe reflejar el cambio leyendo de `LocalStorage` también. **En ningún momento el botón cambiará directamente el contador de HTML**.

### Ejercicio 3
Crea un formulario con los campos `nombre`, `email` y `contraseña`. Cuando se envíe el formulario, se guardará la información en un único objeto de `LocalStorage` llamado `users`.

### Ejercicio 4
Vamos a crear una web de compra-venta ilegal de pokemons. Se te proporcionará un `JSON` con información sobre pokemons. Debes crear `2` páginas de HTML: `index` y `cart`.
1. Pinta en `index` la información de cada pokemon en forma de *card*, y añádele un botón de comprar a cada *card*, como si fuera una tienda online.
2. El botón debe guardar la información de cada pokemon en `LocalStorage`, como si fuera un carrito de la compra.
3. La página `cart` debe mostrar aquellos pokemons que hayan sido guardados en el `LocalStorage`. Si no hubiera ninguno, deberá mostrar: `"Carrito vacío..."`.
4. Por último, en `cart`, añade a cada pokemon que esté en el carrito un botón para eliminarlo del mismo.

```javascript 
const pokemons = [
	{ id: 1, name: 'bulbasaur', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/1.png' },
	{ id: 2, name: 'ivysaur', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/2.png' },
	{ id: 3, name: 'venusaur', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/3.png' },
	{ id: 4, name: 'charmander', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/4.png' },
	{ id: 5, name: 'charmeleon', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/5.png' },
	{ id: 6, name: 'charizard', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/6.png' },
	{ id: 7, name: 'squirtle', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/7.png' },
	{ id: 8, name: 'wartortle', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/8.png' },
	{ id: 9, name: 'blastoise', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/9.png' },
	{ id: 10, name: 'caterpie', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/10.png' },
	{ id: 11, name: 'metapod', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/11.png' },
	{ id: 12, name: 'butterfree', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/12.png' },
	{ id: 13, name: 'weedle', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/13.png' },
	{ id: 14, name: 'kakuna', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/14.png' },
	{ id: 15, name: 'beedrill', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/15.png' },
	{ id: 16, name: 'pidgey', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/16.png' },
	{ id: 17, name: 'pidgeotto', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/17.png' },
	{ id: 18, name: 'pidgeot', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/18.png' },
	{ id: 19, name: 'rattata', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/19.png' },
	{ id: 20, name: 'raticate', img: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/20.png' }
]
```
