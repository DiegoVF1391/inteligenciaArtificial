- [Volver al menú principal](README.md)
- [Regresar a practica 3](practica3.md)
- [Continuar a practica 5](practica5.md)
  
# Práctica 4 - Introducción a la Inteligencia Artificial: Introspección (Islas)
### Introducción
En el vasto mundo de la programación, la resolución de problemas relacionados con matrices y estructuras de datos bidimensionales es un desafío común. 

Por lo que para este ensayo, exploramos la solución a un problema específico:  el de contar "islas" en una matriz, donde '1' representa tierra y '0' representa agua. El objetivo es identificar y contar conjuntos de tierra conectados entre sí horizontal o verticalmente, considerándolos como "islas". Este problema tiene aplicaciones en diversos campos, como la cartografía digital, el procesamiento de imágenes y la inteligencia artificial.

Examinaremos dos enfoques fundamentales para abordar este desafío: el método recursivo y el iterativo. Estos enfoques no solo proporcionan soluciones al problema, sino que también revelan la versatilidad de las estrategias algorítmicas en la resolución de problemas complejos de manera eficiente y estructurada.

A través de la implementación de estos métodos en Python, desentrañaremos la lógica detrás de la identificación de islas, destacando las sutilezas algorítmicas y la diferencia en el enfoque entre ambas estrategias.

### Desarrollo
#### Método recursivo
El código presentado utiliza esta técnica para identificar y contar las islas dentro de una matriz binaria. En primer lugar, es crucial comprender la lógica detrás de este enfoque recursivo.

La función ***contar_islas_recursivo*** se convierte en el corazón del algoritmo. Esta función toma como parámetros la matriz original, una matriz de visitados para rastrear las celdas exploradas, las coordenadas de la celda actual, y las dimensiones de la matriz.

El flujo del algoritmo es simple pero poderoso: verifica si la celda actual es tierra (representada por '1') y si no ha sido visitada anteriormente. Si ambos criterios se cumplen, marca la celda como visitada y procede a explorar recursivamente las celdas adyacentes que también son tierra. Esto se logra mediante un bucle que analiza las celdas vecinas en la matriz, considerando tanto las filas como las columnas.

La llamada recursiva en esta función es crucial, ya que permite explorar todas las celdas adyacentes de manera sistemática, siguiendo el patrón de tierra y expandiendo la región de una isla en particular hasta agotar todas las celdas conectadas.

La función ***contar_islas*** inicia el proceso recorriendo todas las celdas de la matriz. Cuando encuentra una celda que representa tierra y aún no ha sido visitada, invoca la función recursiva contar_islas_recursivo para explorar todas las celdas adyacentes de esa isla. Cada vez que se encuentra una nueva isla, se incrementa el contador de islas.

**Código por recursividad:**

```python:
def contar_islas_recursivo(matrix, visitado, fila, columna, filas, columnas):
    # Verificar si las coordenadas están dentro de la matriz y si la celda no ha sido visitada
    if fila >= 0 and fila < filas and columna >= 0 and columna < columnas and matrix[fila][columna] == 1 and not visitado[fila][columna]:
        # Marcar la celda como visitada
        visitado[fila][columna] = True
        
        # Recursivamente explorar las celdas adyacentes
        for i in range(-1, 2):
            for j in range(-1, 2):
                if not (i == 0 and j == 0):
                    contar_islas_recursivo(matrix, visitado, fila + i, columna + j, filas, columnas)

def contar_islas(matrix):
    if not matrix:
        return 0
    
    filas = len(matrix)
    columnas = len(matrix[0])
    
    # Inicializar una matriz para rastrear las celdas visitadas
    visitado = [[False for _ in range(columnas)] for _ in range(filas)]
    
    conteo_islas = 0
    # Recorrer la matriz y contar las islas
    for i in range(filas):
        for j in range(columnas):
            if matrix[i][j] == 1 and not visitado[i][j]:
                contar_islas_recursivo(matrix, visitado, i, j, filas, columnas)
                conteo_islas += 1
    
    return conteo_islas

# Ejemplo de uso:
matriz_ejemplo = [
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 1, 1, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0],
    [0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0],
    [0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 0, 0],
    [0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 1, 0],
    [0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 1, 0],
    [0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
]

resultado = contar_islas(matriz_ejemplo)
print("Número de islas:", resultado)
```

La recursividad permite una representación natural de la estructura jerárquica del problema: la matriz completa se divide en subproblemas más pequeños, cada uno encargado de explorar un área conectada de tierra. Además, la función recursiva aprovecha la pila de llamadas del sistema para mantener un rastro implícito de las celdas a explorar, simplificando la lógica del código.

Sin embargo, es crucial tener en cuenta que, en matrices muy grandes o con una estructura compleja, este enfoque puede alcanzar los límites de la pila de llamadas recursivas, lo que podría afectar la eficiencia del algoritmo.


#### Método iterativo
El método iterativo comienza con la definición de la función ***contar_islas_iterativo***, que toma la matriz como entrada. A diferencia del enfoque recursivo, este método emplea una estructura de bucle para iterar a través de cada celda de la matriz, explorando áreas conectadas de tierra sin utilizar la recursividad.

Al encontrar una celda de tierra no visitada, se inicia un proceso de exploración. La estrategia se basa en una pila para rastrear las celdas adyacentes que deben ser exploradas. Esta pila se inicia con la celda actual y, mediante un bucle, se examinan todas las celdas adyacentes. Si una celda adyacente es tierra y no ha sido visitada, se marca como visitada y se agrega a la pila para su posterior exploración.

La simplicidad de la lógica iterativa ofrece una comprensión clara del proceso de exploración. A diferencia de la recursividad, donde se utiliza la pila de llamadas del sistema, aquí se emplea una pila explícita, lo que proporciona un control más directo sobre el flujo de exploración.

**Código por iteración:**
```python:
def contar_islas(matrix):
    if not matrix:
        return 0
    
    filas = len(matrix)
    columnas = len(matrix[0])
    
    visitado = [[False for _ in range(columnas)] for _ in range(filas)]
    
    conteo_islas = 0
    for i in range(filas):
        for j in range(columnas):
            if matrix[i][j] == 1 and not visitado[i][j]:
                conteo_islas += 1
                stack = [(i, j)]
                while stack:
                    x, y = stack.pop()
                    if 0 <= x < filas and 0 <= y < columnas and matrix[x][y] == 1 and not visitado[x][y]:
                        visitado[x][y] = True
                        # Agregar celdas adyacentes al stack
                        stack.extend([(x+1, y), (x-1, y), (x, y+1), (x, y-1)])
    
    return conteo_islas

# Ejemplo de uso:
matriz_ejemplo = [
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 1, 1, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0],
    [0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0],
    [0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 0, 0],
    [0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 1, 0],
    [0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 1, 0],
    [0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
]

resultado_iterativo = contar_islas(matriz_ejemplo)
print("Número de islas:", resultado_iterativo)
```

Este enfoque iterativo aprovecha la estructura de datos de pila para mantener un seguimiento eficiente de las celdas por explorar. Al utilizar un bucle mientras la pila no esté vacía, el algoritmo asegura que se explore exhaustivamente cada área conectada de tierra, contabilizando así una isla completa antes de pasar a la siguiente.

### Conclusión
La exploración de estrategias algorítmicas para contar islas en una matriz bidimensional revela la intersección entre la programación y la resolución de problemas complejos. La implementación de enfoques recursivos e iterativos para abordar este desafío específico no solo proporciona soluciones funcionales, sino que también ilustra la diversidad y versatilidad de las herramientas disponibles en el mundo de la programación.

El enfoque recursivo, con su elegante recursividad y capacidad para dividir el problema en subproblemas manejables, ofrece una representación natural de la estructura jerárquica del problema. Este método permite una exploración profunda y sistemática del arreglo que se nos da, identificando cada isla con precisión mientras navega a través de conexiones de celdas de tierra.

Por otro lado, el enfoque iterativo ofrece ventajas en términos de eficiencia y control sobre el uso de recursos. La eliminación de la sobrecarga asociada con las llamadas recursivas puede resultar beneficioso en escenarios donde se trabaja con matrices grandes o en entornos con restricciones de memoria. Además, la claridad en la estructura del bucle permite una fácil comprensión y mantenimiento del código. La secuencialidad del proceso iterativo ofrece una representación más lineal del flujo de exploración, facilitando así la depuración y el seguimiento del algoritmo.

En conclusión, la exploración iterativa, aunque distinta en su enfoque al recursivo, demuestra ser una herramienta igualmente poderosa en la caja de herramientas del programador. La elección entre métodos recursivos o iterativos para abordar problemas algorítmicos depende en gran medida de las necesidades específicas del problema, la eficiencia computacional y la facilidad de implementación.

- [Volver al menú principal](README.md)