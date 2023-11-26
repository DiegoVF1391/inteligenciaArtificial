- [Volver al menú principal](README.md)
- [Regresar a practica 6](practica6.md)
- [Continuar a practica 8](practica8.md)
## La heurística y su papel en la resolución de problemas
La heurística es una técnica o método que se utiliza en la resolución de problemas para encontrar soluciones aproximadas cuando las soluciones exactas son computacionalmente costosas o imprácticas de obtener. En el contexto de la inteligencia artificial y la búsqueda de caminos como en el algoritmo A*, la heurística es una función que estima cuánto falta para llegar desde un estado actual a un estado objetivo.

En la resolución de problemas, la heurística cumple un papel fundamental al guiar la búsqueda hacia la solución óptima o más cercana a esta, reduciendo el espacio de búsqueda y permitiendo tomar decisiones más informadas sobre qué camino seguir. En el caso del algoritmo A*, la heurística es utilizada para priorizar qué nodos o caminos explorar, considerando una estimación del costo desde un estado actual hasta el objetivo.

La heurística en A* se expresa a través de una función que estima el costo restante desde un estado actual hasta el estado objetivo. En el contexto de búsqueda de caminos, la heurística se utiliza para predecir cuánto falta para llegar al objetivo, lo que permite al algoritmo tomar decisiones informadas sobre qué nodos explorar primero.

La elección de una buena heurística puede tener un impacto significativo en la eficiencia y la calidad de la solución encontrada. Una heurística admissible es aquella que nunca sobreestima el costo para llegar al objetivo, mientras que una heurística consistente (o también llamada monótona) tiene la propiedad de que la estimación nunca decrece a lo largo del camino hacia el objetivo. Estas propiedades garantizan que el algoritmo A* encuentre una solución óptima cuando se utiliza con una heurística admissible y consistente.

# Laberinto (Recursividad)
```python:
laberinto = [
    [1, 1, 1, 1, 1, 1, 1, 1, 1],
    [0, 0, 0, 0, 0, 0, 1, 0, 1],
    [1, 1, 1, 0, 1, 1, 1, 0, 1],
    [1, 0, 0, 0, 1, 0, 1, 0, 1],
    [1, 0, 1, 1, 1, 0, 1, 0, 1],
    [1, 0, 0, 0, 0, 0, 0, 0, 1],
    [1, 0, 1, 1, 1, 0, 1, 0, 1],
    [0, 0, 1, 0, 0, 0, 1, 0, 1],
    [1, 1, 1, 1, 1, 1, 1, 1, 1]
]

def heuristica(start, objetivo):
    return abs(start[0] - objetivo[0]) + abs(start[1] - objetivo[1])

movimientos = [(-1, 0), (1, 0), (0, -1), (0, 1)]

def a_estrella_recursiva(laberinto, actual, objetivo, antecesores, g_score, visitados):
    if actual == objetivo:
        camino = []
        while actual:
            camino.append(actual)
            actual = antecesores[actual]
        return camino[::-1], visitados

    for movimiento in movimientos:
        nueva_posicion = (actual[0] + movimiento[0], actual[1] + movimiento[1])

        if nueva_posicion[0] < 0 or nueva_posicion[1] < 0 or nueva_posicion[0] >= len(laberinto) or nueva_posicion[1] >= len(laberinto[0]):
            continue

        if laberinto[nueva_posicion[0]][nueva_posicion[1]] == 1:
            continue

        nuevo_g_score = g_score[actual] + 1

        if nueva_posicion not in g_score or nuevo_g_score < g_score[nueva_posicion]:
            g_score[nueva_posicion] = nuevo_g_score
            antecesores[nueva_posicion] = actual
            visitados.add(nueva_posicion)
            camino_encontrado, visitados = a_estrella_recursiva(laberinto, nueva_posicion, objetivo, antecesores, g_score, visitados)
            if camino_encontrado:
                return camino_encontrado, visitados

    return None, visitados

punto_inicio = (1, 0)
punto_final = (7, 0)
antecesores = {punto_inicio: None}
g_score = {punto_inicio: 0}
visitados = set([punto_inicio])

resultado, visitados = a_estrella_recursiva(laberinto, punto_inicio, punto_final, antecesores, g_score, visitados)

if resultado:
    print("El camino encontrado es:", resultado)
    for fila in range(len(laberinto)):
        for columna in range(len(laberinto[0])):
            if (fila, columna) in visitados:
                print("V", end=" ")  # Mostrar celdas visitadas
            else:
                print(laberinto[fila][columna], end=" ")
        print()
else:
    print("No se encontró un camino válido.")
```
## Laberinto (Algoritmo)
Claro, el algoritmo A* es un algoritmo de búsqueda informada que encuentra el camino más corto desde un nodo de inicio a un nodo objetivo en un grafo o, en este caso, en un laberinto representado como una matriz.

### Pasos principales del algoritmo A*:

1. **Inicialización**: Se inicializan algunas estructuras de datos como una cola de prioridad para almacenar los nodos a explorar, diccionarios para registrar los costos y los antecesores de cada nodo, y un conjunto para llevar un registro de los nodos visitados.

2. **Heurística**: Se define una función heurística que estima el costo desde un nodo dado hasta el nodo objetivo. En este caso, se utiliza la distancia Manhattan, que es la suma de las distancias horizontales y verticales entre dos puntos en una cuadrícula.

3. **Bucle de exploración**: Se realiza un bucle mientras hay nodos por explorar en la cola de prioridad. En cada iteración, se toma el nodo con el menor costo total esperado (función de costo acumulado más la heurística) desde la cola de prioridad.

4. **Generación de vecinos**: Se generan los vecinos válidos (celdas adyacentes no bloqueadas) del nodo actual y se calculan sus costos acumulados desde el nodo de inicio. Se actualizan los costos y se añaden a la cola de prioridad si no se han visitado o si se ha encontrado un camino más corto hasta ese nodo.

5. **Recorrido del camino**: Cuando se alcanza el nodo objetivo, se reconstruye el camino desde el nodo de inicio hasta el objetivo utilizando los antecesores registrados en el diccionario.

### Funciones principales:

- `heuristica(start, objetivo)`: Calcula la heurística entre dos puntos en la cuadrícula (distancia Manhattan en este caso).
- `a_estrella(laberinto, inicio, objetivo)`: Implementa el algoritmo A* para encontrar el camino desde el nodo de inicio hasta el nodo objetivo en el laberinto.
- *resultado, visitados = a_estrella(...)*: Ejecuta el algoritmo A* y devuelve el camino encontrado y el conjunto de nodos visitados.

El algoritmo A* utiliza la heurística para priorizar la exploración hacia la dirección que parezca más prometedora en términos de llegar al objetivo. 

A continuación se muestra el siguiente código:
```python:
# Laberinto
laberinto = [
    [1, 1, 1, 1, 1, 1, 1, 1, 1],
    [0, 0, 0, 0, 0, 0, 1, 0, 1],
    [1, 1, 1, 0, 1, 1, 1, 0, 1],
    [1, 0, 0, 0, 1, 0, 1, 0, 1],
    [1, 0, 1, 1, 1, 0, 1, 0, 1],
    [1, 0, 0, 0, 0, 0, 0, 0, 1],
    [1, 0, 1, 1, 1, 0, 1, 0, 1],
    [0, 0, 1, 0, 0, 0, 1, 0, 1],
    [1, 1, 1, 1, 1, 1, 1, 1, 1]
]

# Función de heurística (distancia Manhattan)
def heuristica(start, objetivo):
    return abs(start[0] - objetivo[0]) + abs(start[1] - objetivo[1])

# Movimientos posibles: arriba, abajo, izquierda, derecha
movimientos = [(-1, 0), (1, 0), (0, -1), (0, 1)]

def a_estrella(laberinto, inicio, objetivo):
    filas, columnas = len(laberinto), len(laberinto[0])
    cola_prioritaria = [(0, inicio)]
    antecesores = {inicio: None}
    g_score = {inicio: 0}
    visitados = set()

    while cola_prioritaria:
        costo_actual, actual = min(cola_prioritaria)
        cola_prioritaria.remove((costo_actual, actual))
        visitados.add(actual)

        if actual == objetivo:
            camino = []
            while actual:
                camino.append(actual)
                actual = antecesores[actual]
            return camino[::-1], visitados

        for movimiento in movimientos:
            nueva_posicion = (actual[0] + movimiento[0], actual[1] + movimiento[1])

            if 0 <= nueva_posicion[0] < filas and 0 <= nueva_posicion[1] < columnas and laberinto[nueva_posicion[0]][nueva_posicion[1]] == 0:
                nuevo_g_score = g_score[actual] + 1

                if nueva_posicion not in g_score or nuevo_g_score < g_score[nueva_posicion]:
                    g_score[nueva_posicion] = nuevo_g_score
                    f_score = nuevo_g_score + heuristica(nueva_posicion, objetivo)
                    cola_prioritaria.append((f_score, nueva_posicion))
                    antecesores[nueva_posicion] = actual

    return None, visitados

# Punto de inicio y objetivo
punto_inicio = (1, 0)
punto_final = (7, 0)

# Resolución del laberinto
resultado, visitados = a_estrella(laberinto, punto_inicio, punto_final)
if resultado:
    print("El camino encontrado es:", resultado)
    for fila in range(len(laberinto)):
        for columna in range(len(laberinto[0])):
            if (fila, columna) in visitados:
                print("V", end=" ")  # Mostrar celdas visitadas
            else:
                print(laberinto[fila][columna], end=" ")
        print()
else:
    print("No se encontró un camino válido.")
```

- [Volver al menú principal](README.md)