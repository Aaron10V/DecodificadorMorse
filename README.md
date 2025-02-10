Explicación del proceso

1. Creamos proyecto consola .NET 8
2. Mapeamos cada letra del abecedario a su representación Morse 
3. Creamos el diccionario de palabras (Para esto le pedi a chatgpt que me creara una lista tipo string pasandole las palabras del ejercicio)
4. Declaro un Dictionary que me permite almacenar la asociación de una palabra (la clave) y su modo en Morse (el valor)
5. Defino la secuencia Morse para encontrar las posibles frases en palabras
6. Creamos otro diccionario para hacer el proceso de memoización (El memo lo que hacemos es almacenar los resultados que vamos calculando para no repetir calculos) y almacenamos las frases encontradas
7. Creamos el metodo main:
	1) Recorremos la lista de palabras del diccionario:
		a) Convertir a mayúscula
		b) Construimos la representación a codigo Morse utilizando el diccionario letraAMorse
		c) Comprobamosa que todas sus letras esten en el mapeo y si es asi lo ñadimos al diccionario palabraAMorse junto con su representación en Morse.
	2) Invocamos la función recursiva que decodifica la secuencia Morse
	3) Mostramos los resultados
	4) Evitamos que la consola se cierre al instante
8. Creamos el metodo Decodificar:
	1) Comprobamos si el indice ha llegado al final de la cadena secuenciaMorse
	2) Verificaos si se han calculado las soluciones partiendo del indice de este momento
	3) Creamos una lista vacía que almacenará todas las posibles frases 
	4) Recorremos cada par (clave-valor) del diccionario (clave es la palabra del texto y valor la codificacion morse)
    5) Despues comprabamos que al sumar la longitud del codigo morse de la palabra no sea mayor que la longitud total de la secuencia y que la subcadena sea igual al codigo Morse de la palabra
    6) Llamamos recursivamente al metodo Decodificar para hacer el resto de la secuencia
    7) Construimos las frases para ello tenemos que comprobar si son cadenas vacias o no. Si es vacia es que es la ultima y si no se concatena y se añade un espacio para formar la frase
    8) Guardamos la lista de frases obtenidas para el indice actual en el diccionario
    9) Por último, retornamos la lista de todas las frases posibles
