![](../../../assets/Logo_Yellow.png)

# Travel Calculator
Vamos a hacer una aplicación que se encargará de calcular el coste de un viaje. 

La información la recibiremos de un formulario que rellenerá el usuario. El formulario lo tienes en la imagen al final del ejercicio.

Una vez que el usuario envíe el formulario con la información, debemos calcular el precio del viaje. Para ello tendremos que usar `4` funciones:

#### `calcularCoste()`
- Será llamada cuando se envíe el formulario.
- Se encargará de llamar a las otras `3` funciones.
- Cuando se realicen todos los cálculos, pintará en el DOM el resultado.

#### `costeHotel()`
- **Parámetros**: número de noches de hotel.
- **Output**: coste total del hotel teniendo en cuenta que cada noche cuesta siempre `140€`.

#### `costeAvion()`
- **Parámetros**: nombre de la ciudad y número de noches.
- **Output**: coste del viaje teniendo en cuenta los siguiente:
	- Los costes del viaje por ciudad son:
		- Barcelona: 90€
		- Madrid: 90€
		- Sevilla: 50€
		- Valencia: 40€
	- Si se contratas **más** de `3` noches de hotel, la agencia te descuenta un `10%` sobre el coste normal del avión.

#### `costeCoche()`
  - **Parámetros**: número de días de alquiler del coche.
  - **Output**: coste del alquiler del coche para el número de días seleccionados, teniendo en cuenta lo siguiente:
	  - Cada día de alquiler son `40€`.
	  - Si alquilas un coche `3` o más días, obtienes un descuento de `20€` sobre el coste normal del alquiler total.
	  - Si alquilas un coche `7` o más días, obtienes un descuento de `50€` sobre el coste normal del alquiler total (no acumulable con los `20€` de la oferta anterior). 
  
![](travel_price_calculator_img.png)