- [Volver al menú principal](README.md)
- [Regresar a practica 7](practica7.md)
- [Continuar a practica 9](practica9.md)

# Práctica 8 - Reglas y Búsquedas : Espacio de Estados

#### Juego de las ranas
El espacio de estados para el juego de las ranas se refiere a todas las posibles configuraciones en las que pueden encontrarse las ranas en el tablero, considerando las reglas del juego.

Para este problema en particular, donde hay 3 ranas verdes y 3 ranas marrones que deben intercambiar sus posiciones en un tablero de 7 espacios (3 espacios para cada color de rana y un espacio vacío), podríamos representar las configuraciones como sigue:

Supongamos que 'V' representa una rana verde, 'M' representa una rana marrón y 'E' representa un espacio vacío.

**Espacio de estados:**
Estado inicial: **V V V E M M M**
Estados:
- V V V E M M M
- V V E V M M M
- V V M V E M M
- V V M V M E M
- V V M E M V M
- V E M V M V M
- E V M V M V M
- M V E V M V M
- M V M V E V M
- M V M V M V E
- M V M V M E V
- M V M E M V V
- M E M V M V V
- M M E V M V V
- M M M V E V V
- M M M E V V V
Y finalmente, el estado objetivo sería: **M M M E V V V**

Este conjunto de estados muestra todas las configuraciones posibles desde el estado inicial hasta el estado objetivo siguiendo las reglas del juego.


#### Los tres misioneros y tres canibales
Se tienen 3 misioneros y 3 caníbales en un lado de un río. Tienen un bote que puede llevar como máximo dos personas (ya sean misioneros o caníbales). El objetivo es llevar a todos al otro lado del río sin dejar que en ningún momento haya más caníbales que misioneros en un lado, ya que los caníbales podrían comer a los misioneros.

Por lo que para resolver este problema, representamos los estados posibles con la siguiente notación: M para misioneros, C para caníbales y el bote es representado con las dos barras "|  |".

**Espacio de estados:**
Estado inicial: **| | C C C M M M**
Estados:
- | C M | C C M M
- C | M | C C M M
- C | C C | M M M
- C C | C | M M M
- C C | M M | C M 
- C C M | M | C M 
- C M | C M | C M 
- C M | M | C C M 
- C M | M M | C C 
- M M M | C | C C 
- M M M | C C | C 
- M M M C | C | C 
- M M M C | C C |
- M M M C C C | |

Y finalmente, el estado objetivo sería: **M M M C C C | |**

Este conjunto de estados muestra todas las configuraciones posibles desde el estado inicial hasta el estado objetivo siguiendo las reglas del problema.

- [Volver al menú principal](README.md)