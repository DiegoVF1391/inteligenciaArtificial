- [Volver al menú principal](README.md)
- [Regresar a practica 5](practica5.md)
- [Continuar a practica 7](practica7.md)
# Práctica 6 - Introducción a la Inteligencia Artificial: El proceso de razonamiento según la lógica

El problema de Josephus planteado aquí implica encontrar la posición específica en la que Josephus se sentó para ser el último sobreviviente. En este caso, el patrón es que se eliminan secuencialmente cada segundo soldado hasta que queda uno vivo. Para poder solucionar el problema y poder encontrar una solución, se tendrá que realizar con pocos soldados e ir incrementando mientras se vayan resolviendo.

- Primero, si hubiera nada más que un solo soldado, no hay nada que pensar. El sobreviviente es el único participante (o soldado) que hay, y lo declaramos ganador.

- En cambio, si hubiera dos soldados, entonces, el uno elimina al dos y allí se termina el juego también. Ganador: el número uno.

- Si ahora fueran tres soldados: 1-2-3. En este caso, el 1 elimina al 2 pero el 3 está vivo aún y siguiendo el orden del círculo, el 3 elimina al 1. Ganador: número 3

- Si fueran cuatro soldados: 1-2-3-4. Entonces 1 elimina a 2, y 3 elimina a 4. Quedan 1 y 3. El turno es otra vez para el número 1 que elimina al 3 y queda como único sobreviviente. Ganador: número 1.

- Si fueran cinco soldados: 1-2-3-4-5. Quedan eliminados los dos pares (2 y 4), pero fíjese que ni bien queda eliminado el 4, el turno le corresponde al 5. O sea: sobreviven 5-1-3, pero 5 es el que empieza. Luego, 5 elimina al 1 y le toca el turno al 3. El 3 elimina al 5, y queda como sobreviviente. Ganador: número 3.

- Si fueran seis soldados: 1-2-3-4-5-6. En el primer paso quedan eliminados todos los pares. Sobreviven 1-3-5.  Después que 5 eliminó a 6, le toca una vez más al número 1. El 1 elimina al 3 y por último, el 5 elimina al 3. Ganador: número 5.

- Para siete soldados: 1-2-3-4-5-6-7. En el primer paso quedan eliminados todos los pares, pero cuando queda afuera el número 6 (que es el último par), le toca el turno al número 7. Los que quedan son: 7-1-3-5, en ese orden. El 7 elimina al 1, el 3 al 5, y quedan: 7 y 3, y es el turno del 7, que elimina al 3. Ganador: número 7.

Ahora voy a escribir una lista de los resultados que se obtienen al aumentar el número de soldados que participan:

| Cantidad de soldados | Soldado Eliminado |
|-------|-------------------|
| 1     | 1                 |
| 2     | 1                 |
| 3     | 3                 |
| 4     | 1                 |
| 5     | 3                |
| 6     | 5                |
| 7     | 7                |
| 8     | 1                |
| 9     | 3                |
| 10    | 5                |
| 11    | 7                |
| 12    | 9                |
| 13    | 11                |
| 14    | 13                |
| 15    | 15                |
| 16    | 1               |
| 17    | 3                 |
| 18    | 5                 |
| 19    | 7                 |
| 20    | 9                 |
| 21    | 11                 |
| 22    | 13                |
| 23    | 15                |
| 24    | 17                |
| 25    | 19                |
| 26    | 21                |
| 27    | 23                |
| 28    | 25                |
| 29    | 27                |
| 30    | 29                |
| 31    | 31                |
| 32    | 1                |

Con esta tabla y varios ejercicios resueltos, el problema nos indica que el número de soldados que es una potencia de dos, el ganador será siempre el número 1. Por lo que nos dice que posiblemente tiene algo que ver éste simple hecho.

Ahora, también tiene que ver que los numeros que siguen de las potencias del 2 van en secuencia de numeros impares. Lo cual nos plantea que posiblemente se pueda usar la formula para numeros impares la cual es:
> 2n * 1.


Ya teniendo en cuenta estos dos hechos, el problema de Josephus planteado en este escenario específico con 41 soldados nos lleva a una solución directa. Empezando desde el soldado número 1, siguiendo una regla de eliminación donde cada segundo soldado muere, se encuentra que el último sobreviviente está en la posición 19.

Identificamos que cuando agregamos el resultado de la potencia de 2 anterior o igual al numero total de soldados y lo restamos al numero de soldados. Y el resultado de esta operación remplazamos la variable *n* de la formula para numeros impares, al parecer encontramos la posición en la que debemos estar. Solo que para expresar la potencia anterior o igual al número de soldados necesitamos a logaritmo de 2 para obtener la potencia de 2 y así lograr obtenerla fácilmente.

Por lo que a medida que el número de soldados aumenta, el patrón nos lleva a la fórmula: 
>1 + (*n* − 2 ^ ⌊log2 (*n*)⌋) × 2

Donde **n** es el número total de soldados junto a Josephus.

Este enfoque nos permite encontrar la posición ganadora sin recorrer todos los pasos intermedios, siendo independientes del número específico de soldados. La estrategia consiste en identificar la potencia de 2 más cercana al número total de soldados y aplicar la fórmula mencionada para obtener la posición en la que Josephus debe sentarse para ser el último sobreviviente.

##### Código
Ya habiendo descubierto la formula que nos permite obtener la posición en la que debe estar posicionado para sobrevivir, podremos trasladarlo a un programa en Python. A continuación se muestra el código:
```python:
import math

def grupo_potencia(numero):
    exponente = int(math.log(numero, 2))  # Calcula el logaritmo en base 2 del número
    potencia = 2 ** exponente  # Calcula 2 elevado a ese exponente
    return potencia

numero_soldados = int(input("Ingresa un número: ")) #Pide el numero de soldados

potencia = grupo_potencia(numero_soldados)
posicion_josephus = 1 + (numero_soldados-potencia) * 2 #Aplicamos la formula matemática para obtener la posición
print(f"Josephus se sentó en la posición número {posicion_josephus}")
```
### Conclusión

- [Volver al menú principal](README.md)