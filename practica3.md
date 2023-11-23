- [Volver al menú principal](README.md)
- [Regresar a practica 2](practica2.md)
- [Continuar a practica 4](practica4.md)

# Práctica 3. Introspección (Solución al problema de los alfiles)

### Introducción
El ajedrez, ese milenario juego de estrategia y destreza mental, ha desafiado a mentes ávidas de complejidad y resolución de problemas a lo largo de la historia. Entre sus variantes y desafíos, se plantean situaciones que demandan no solo conocimiento de las reglas, sino también agudeza para encontrar soluciones creativas y eficientes. Uno de estos desafíos es el problema de intercambiar las posiciones de alfiles negros y blancos en un tablero reducido, sin que se ataquen mutuamente en ningún momento.

Este enigma plantea la interrogante sobre la mínima cantidad de movimientos necesarios para lograr tal cambio sin incumplir las reglas fundamentales del ajedrez. El objetivo es encontrar una secuencia estratégica que permita a los alfiles intercambiar sus posiciones de manera alterna, manteniendo la integridad de ambos bandos y evitando cualquier confrontación entre alfiles del mismo color.

En este ensayo, exploraremos la estrategia detrás de la solución mínima para este problema. Analizaremos paso a paso los movimientos necesarios, la lógica detrás de cada uno de ellos y cómo se articulan en una secuencia que resuelve el enigma planteado en la menor cantidad de pasos posible. Adentrémonos en el tablero de ajedrez y en la mente estratégica requerida para resolver este desafío.

### Desarrollo
##### Planteamiento del problema
La meta es intercambiar las posiciones de los alfiles negros y blancos sin que se ataquen entre sí durante el proceso. Para lograrlo, necesitamos una estrategia que permita mover los alfiles de manera alternada y gradual hacia sus nuevas posiciones.

##### Movimiento del alfil
Primero, es esencial comprender las reglas del movimiento de los alfiles en el ajedrez. Los alfiles se mueven en diagonales a lo largo del tablero, y cada alfil está restringido a las casillas de su color inicial. En este tablero reducido, hay dos alfiles negros en casillas blancas, dos alfiles negros en casillas negras, dos alfiles blancos en casillas blancas y dos alfiles blancos en casillas negras.

##### Coordenadas y notación para ubicar las piezas
En el ajedrez, las casillas del tablero se identifican mediante un sistema de coordenadas que combina letras y números. Este sistema se utiliza para especificar la posición de cada pieza en el tablero.

En el caso de este problema con un tablero de ajedrez reducido, se emplea una notación para designar las cinco filas y cuatro columnas. En el sistema algebraico, las filas están numeradas de 1 a 8, siendo la fila 1 correspondiente a la primera fila de piezas blancas y la 8 es la fila de las piezas negras. Las columnas son denominadas alfabéticamente de a a h siendo la fila de la izquierda de las piezas blancas la que se refiere como a.

Por lo tanto, las casillas del tablero se identifican combinando la letra de la fila y el número de la columna correspondiente. Aquí está la representación de las casillas en este tablero reducido:

- Las letras 'a', 'b', 'c' y 'd' representan las columnas.
- Los números del '1' al '5' representan las filas.

Por ejemplo:
- La casilla en la esquina superior izquierda sería a5.
- La casilla en la esquina superior derecha sería d5.
- La casilla en la esquina inferior izquierda sería a1.
- La casilla en la esquina inferior derecha sería d1.

En el caso específico de este problema con alfiles intercambiando posiciones, las posiciones iniciales de los alfiles se mencionan usando esta notación. Por ejemplo, a2 se refiere a la casilla en la columna 'a' y fila '2'. Esto se aplica a todas las casillas del tablero para identificar la ubicación de cada alfil al inicio del problema.

Esta notación es fundamental en ajedrez para comunicar movimientos, estrategias y posiciones de piezas de manera precisa y unificada. 

#### Solución del problema
Empezamos con la disposición inicial de los alfiles:

- Alfiles negros: a5, b5, c5, d5
- Alfiles blancos: a1, b1, c1, d1
  
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | ♝₁ | ♝₁ |
>| * | * | * | * |
>| * | * | * | * |
>| * | * | * | * |
>| ♝₂ | ♝₂ | ♝₂ | ♝₂ |

Para intercambiar sus posiciones, trazamos una estrategia de movimiento intercalado entre los alfiles blancos y negros. Podemos describir cada movimiento en detalle:

Mover el alfil blanco de b1 a c2:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | ♝₁ | ♝₁ |
>| * | * | * | * |
>| * | * | * | * |
>| * | * | ♝₂ | * |
>| ♝₂ | * | ♝₂ | ♝₂ |

Mover el alfil negro de c5 a b4:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | * | ♝₁ |
>| * | ♝₁ | * | * |
>| * | * | * | * |
>| * | * | ♝₂ | * |
>| ♝₂ | * | ♝₂ | ♝₂ |

Mover el alfil blanco de a1 a d4:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | * | ♝₁ |
>| * | ♝₁ | * | ♝₂ |
>| * | * | * | * |
>| * | * | ♝₂ | * |
>| * | * | ♝₂ | ♝₂ |

Mover el alfil negro de d5 a a2:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | * | * |
>| * | ♝₁ | * | ♝₂ |
>| * | * | * | * |
>| ♝₁ | * | ♝₂ | * |
>| * | * | ♝₂ | ♝₂ |

Mover el alfil blanco de c1 a b2:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | * | * |
>| * | ♝₁ | * | ♝₂ |
>| * | * | * | * |
>| ♝₁ | ♝₂ | ♝₂ | * |
>| * | * | * | ♝₂ |

Mover el alfil negro de b5 a c4:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | * | * |
>| * | ♝₁ | ♝₁ | ♝₂ |
>| * | * | * | * |
>| ♝₁ | ♝₂ | ♝₂ | * |
>| * | * | * | ♝₂ |

Mover el alfil blanco de c2 a a4:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | * | * |
>| ♝₂ | ♝₁ | ♝₁ | ♝₂ |
>| * | * | * | * |
>| ♝₁ | ♝₂ | * | * |
>| * | * | * | ♝₂ |


Mover el alfil negro de b4 a d2:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | * | * |
>| ♝₂ | * | ♝₁ | ♝₂ |
>| * | * | * | * |
>| ♝₁ | ♝₂ | * | ♝₁ |
>| * | * | * | ♝₂ |


Mover el alfil blanco de d4 a c5:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | ♝₂ | * |
>| ♝₂ | * | ♝₁ | * |
>| * | * | * | * |
>| ♝₁ | ♝₂ | * | ♝₁ |
>| * | * | * | ♝₂ |

Mover el alfil negro de a2 a b1:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | ♝₂ | * |
>| ♝₂ | * | ♝₁ | * |
>| * | * | * | * |
>| * | ♝₂ | * | ♝₁ |
>| * | ♝₁ | * | ♝₂ |

Mover el alfil blanco de b2 a a3:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | ♝₂ | * |
>| ♝₂ | * | ♝₁ | * |
>| ♝₂ | * | * | * |
>| * | * | * | ♝₁ |
>| * | ♝₁ | * | ♝₂ |

Mover el alfil negro de c4 a d3:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | ♝₂ | * |
>| ♝₂ | * | * | * |
>| ♝₂ | * | * | ♝₁ |
>| * | * | * | ♝₁ |
>| * | ♝₁ | * | ♝₂ |


Mover el alfil blanco de a4 a b3:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | ♝₂ | * |
>| * | * | * | * |
>| ♝₂ | ♝₂ | * | ♝₁ |
>| * | * | * | ♝₁ |
>| * | ♝₁ | * | ♝₂ |

Mover el alfil negro de d2 a c3:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | ♝₂ | * |
>| * | * | * | * |
>| ♝₂ | ♝₂ | ♝₁ | ♝₁ |
>| * | * | * | * |
>| * | ♝₁ | * | ♝₂ |


Mover el alfil blanco de a3 a c1:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | * | ♝₂ | * |
>| * | * | * | * |
>| * | ♝₂ | ♝₁ | ♝₁ |
>| * | * | * | * |
>| * | ♝₁ | ♝₂ | ♝₂ |

Mover el alfil negro de d3 a b5:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | ♝₂ | * |
>| * | * | * | * |
>| * | ♝₂ | ♝₁ | * |
>| * | * | * | * |
>| * | ♝₁ | ♝₂ | ♝₂ |

Mover el alfil blanco de b3 a d5:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | ♝₂ | ♝₂ |
>| * | * | * | * |
>| * | * | ♝₁ | * |
>| * | * | * | * |
>| * | ♝₁ | ♝₂ | ♝₂ |

Mover el alfil negro de c3 a a1:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | ♝₂ | ♝₂ |
>| * | * | * | * |
>| * | * | * | * |
>| * | * | * | * |
>| ♝₁ | ♝₁ | ♝₂ | ♝₂ |

Mover el alfil blanco de d1 a b3:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₁ | ♝₁ | ♝₂ | ♝₂ |
>| * | * | * | * |
>| * | ♝₂ | * | * |
>| * | * | * | * |
>| ♝₁ | ♝₁ | ♝₂ | * |

Mover el alfil negro de a5 a c3:
>|  |  |  |  | 
>|---|---|---|---|
>| * | ♝₁ | ♝₂ | ♝₂ |
>| * | * | * | * |
>| * | ♝₂ | ♝₁ | * |
>| * | * | * | * |
>| ♝₁ | ♝₁ | ♝₂ | * |

Mover el alfil blanco de c5 a a3:
>|  |  |  |  | 
>|---|---|---|---|
>| * | ♝₁ | * | ♝₂ |
>| * | * | * | * |
>| ♝₂ | ♝₂ | ♝₁ | * |
>| * | * | * | * |
>| ♝₁ | ♝₁ | ♝₂ | * |

Mover el alfil negro de b1 a d3:
>|  |  |  |  | 
>|---|---|---|---|
>| * | ♝₁ | * | ♝₂ |
>| * | * | * | * |
>| ♝₂ | ♝₂ | ♝₁ | ♝₁ |
>| * | * | * | * |
>| ♝₁ | * | ♝₂ | * |

Mover el alfil blanco de b3 a a2:
>|  |  |  |  | 
>|---|---|---|---|
>| * | ♝₁ | * | ♝₂ |
>| * | * | * | * |
>| ♝₂ | * | ♝₁ | ♝₁ |
>| ♝₂ | * | * | * |
>| ♝₁ | * | ♝₂ | * |

Mover el alfil negro de c3 a d4:
>|  |  |  |  | 
>|---|---|---|---|
>| * | ♝₁ | * | ♝₂ |
>| * | * | * | ♝₁ |
>| ♝₂ | * | * | ♝₁ |
>| ♝₂ | * | * | * |
>| ♝₁ | * | ♝₂ | * |

Mover el alfil blanco de c1 a d2:
>|  |  |  |  | 
>|---|---|---|---|
>| * | ♝₁ | * | ♝₂ |
>| * | * | * | ♝₁ |
>| ♝₂ | * | * | ♝₁ |
>| ♝₂ | * | * | ♝₂ |
>| ♝₁ | * | * | * |

Mover el alfil negro de b5 a a4:
>|  |  |  |  | 
>|---|---|---|---|
>| * | * | * | ♝₂ |
>| ♝₁ | * | * | ♝₁ |
>| ♝₂ | * | * | ♝₁ |
>| ♝₂ | * | * | ♝₂ |
>| ♝₁ | * | * | * |

Mover el alfil blanco de d2 a a5:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | * | * | ♝₂ |
>| ♝₁ | * | * | ♝₁ |
>| ♝₂ | * | * | ♝₁ |
>| ♝₂ | * | * | * |
>| ♝₁ | * | * | * |

Mover el alfil negro de a4 a d1:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | * | * | ♝₂ |
>| * | * | * | ♝₁ |
>| ♝₂ | * | * | ♝₁ |
>| ♝₂ | * | * | * |
>| ♝₁ | * | * | ♝₁ |

Mover el alfil blanco de a3 a b4:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | * | * | ♝₂ |
>| * | ♝₂ | * | ♝₁ |
>| * | * | * | ♝₁ |
>| ♝₂ | * | * | * |
>| ♝₁ | * | * | ♝₁ |

Mover el alfil negro de d3 a c2:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | * | * | ♝₂ |
>| * | ♝₂ | * | ♝₁ |
>| * | * | * | * |
>| ♝₂ | * | ♝₁ | * |
>| ♝₁ | * | * | ♝₁ |

Mover el alfil blanco de a2 a c4:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | * | * | ♝₂ |
>| * | ♝₂ | ♝₂ | ♝₁ |
>| * | * | * | * |
>| * | * | ♝₁ | * |
>| ♝₁ | * | * | ♝₁ |

Mover el alfil negro de d4 a b2:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | * | * | ♝₂ |
>| * | ♝₂ | ♝₂ | * |
>| * | * | * | * |
>| * | ♝₁ | ♝₁ | * |
>| ♝₁ | * | * | ♝₁ |


Mover el alfil blanco de c4 a b5:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | ♝₂ | * | ♝₂ |
>| * | ♝₂ | * | * |
>| * | * | * | * |
>| * | ♝₁ | ♝₁ | * |
>| ♝₁ | * | * | ♝₁ |

Mover el alfil negro de b2 a c1:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | ♝₂ | * | ♝₂ |
>| * | ♝₂ | * | * |
>| * | * | * | * |
>| * | * | ♝₁ | * |
>| ♝₁ | * | ♝₁ | ♝₁ |

Mover el alfil blanco de b4 a c5:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | ♝₂ | ♝₂ | ♝₂ |
>| * | * | * | * |
>| * | * | * | * |
>| * | * | ♝₁ | * |
>| ♝₁ | * | ♝₁ | ♝₁ |

Mover el alfil negro de c2 a b1:
>|  |  |  |  | 
>|---|---|---|---|
>| ♝₂ | ♝₂ | ♝₂ | ♝₂ |
>| * | * | * | * |
>| * | * | * | * |
>| * | * | * | * |
>| ♝₁ | ♝₁ | ♝₁ | ♝₁ |

Se completa el intercambio final entre alfiles.

Al final de estos 36 movimientos, hemos logrado el intercambio de las posiciones de los alfiles negros y blancos sin que ninguno ataque a otro del color opuesto. Este método de movimientos alternados y estratégicos es la clave para resolver este problema en el menor número de pasos posible.

### Conclusión
Resolver este desafío no solo implica mover piezas en un tablero, sino también desarrollar un pensamiento estratégico y lógico. La solución óptima, lograda en 8 movimientos, destaca la importancia de un enfoque sistemático y alternado para resolver problemas complejos incluso en situaciones aparentemente simples como esta.

La complejidad inherente a este problema ha sido evidente a lo largo de la búsqueda de la solución. Cada movimiento requería una consideración meticulosa para asegurar que ningún alfil atacara a otro del color opuesto en ningún momento. La necesidad de encontrar la secuencia más eficiente ha sido un reto, y la satisfacción al llegar a la solución mínima en ocho movimientos ha sido gratificante.

Sin embargo, vale la pena considerar que, al igual que en el ajedrez, donde las posibilidades son vastas y las estrategias son diversas, es probable que existan múltiples enfoques para resolver este desafío. La solución encontrada aquí representa una ruta posible, pero no necesariamente la única. Otros enfoques estratégicos podrían llevar a soluciones igualmente válidas.

- [Volver al menú principal](README.md)