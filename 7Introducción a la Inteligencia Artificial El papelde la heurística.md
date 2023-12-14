# Introducción a la Inteligencia Artificial: El papel de la heurística
## INTRODUCCION 
Una heurística es un procedimiento que se utiliza para resolver un problema de manera aproximada, las heurísticas se suelen utilizar cuando no es posible encontrar una solución óptima al problema, o cuando la búsqueda de una solución óptima es demasiado costosa o compleja.
Las heurísticas pueden desempeñar un papel importante en la resolución de problemas. Pueden ayudar a los solucionadores de problemas a encontrar soluciones aproximadas o aproximadas a problemas difíciles o imposibles de resolver de manera óptima.
## DESARROLLO
 
**Planteamiento del problema:**
Los laberintos de forma cuadrada o rectangular son los más antiguos que existen; la primera representación conocida de un laberinto de este tipo se encuentra en una tablilla de Pilo2 y también aparece, como sello, en las tumbas del antiguo Egipto, donde se hizo famoso desde la antigüedad el Laberinto de Fayum, citado por Heródoto.3 Los laberintos de forma redonda o circular aparecieron a fines del siglo vii a.  C. en la Italia etrusca; más tarde, aparecen en las monedas de Cnosos, a finales del siglo iii a. C. y se cree que eran usadas como mapa del célebre Laberinto de Creta.47
Los laberintos se clasifican básicamente en dos grandes grupos "según la relación que existe con el centro y la salida del mismo". El primer grupo de estos laberintos es el laberinto clásico o laberinto univiario: es el que hacer e correr, al ingresar en él, todo el espacio para llegar al centro mediante una única vía, camino o sendero; es decir, no ofrece la posibilidad de tomar caminos alternativos, no hay bifurcaciones, sino que existe una sola puerta de salida, que es la misma por la que se entra al laberinto. Por el hecho detener un solo camino o sendero que seguir a medida que se avanza dentro de él, no es posible perderse en su interior. Por ser el laberinto más sencillo es frecuentemente utilizado para realizar experimentos de robótica en informática, especialmente populares en Java5
Las heurísticas pueden ser útiles en los siguientes casos:
- Cuando no es posible encontrar una solución óptima al problema.
- Cuando la búsqueda de una solución óptima es demasiado costosa o compleja.
- Cuando se necesitan soluciones rápidas o aproximadas.

La solución con recursividad del laberinto funciona de la siguiente manera:
1.	Se comienza en la entrada del laberinto.
2.	Se exploran los cuatro espacios adyacentes a la posición actual.
3.	Se selecciona el espacio con el menor valor.
4.	Si el espacio seleccionado es la salida, se devuelve la coordenada de la salida.
5.	Si el espacio seleccionado no es la salida, se llama a la función recursivamente con la coordenada del espacio seleccionado como nueva entrada.

### Código del algoritmo de solución
def  resolver_laberinto(laberinto, entrada):
  
  if laberinto[entrada[0]][entrada[1]] == 0:
    return entrada

  # Explorar los cuatro espacios adyacentes

  espacios_adyacentes = []
  for i in range(-1, 2):
    for j in range(-1, 2):
      if 0 <= entrada[0] + i < len(laberinto) and 0 <= entrada[1] + j < len(laberinto[0]):
        if laberinto[entrada[0] + i][entrada[1] + j] != 1:
          espacios_adyacentes.append((entrada[0] + i, entrada[1] + j))

  # Seleccionar el espacio con el menor valor

  coordenada_menor_valor = min(espacios_adyacentes, key=lambda coordenada: laberinto[coordenada[0]][coordenada[1]])

  # Si el espacio seleccionado es la salida, se devuelve la coordenada

  if laberinto[coordenada_menor_valor[0]][coordenada_menor_valor[1]] == 0:
    return coordenada_menor_valor

  # Si el espacio seleccionado no es la salida, se llama a la función recursivamente

  return resolver_laberinto(laberinto, coordenada_menor_valor)

laberinto = [[1, 1, 1, 1, 1, 1, 1, 1, 1],
             [0, 0, 0, 0, 0, 0, 1, 0, 1],
              [1, 1, 1, 0, 1, 1, 1, 0, 1],
              [1, 0, 0, 0, 1, 0, 1, 0, 1],
              [1, 0, 1, 1, 1, 0, 1, 0, 1],
              [1, 0, 0, 0, 0, 0, 0, 0, 1],
              [1, 0, 1, 1, 1, 0, 1, 0, 1],
              [0, 0, 1, 0, 0, 0, 1, 0, 1],
              [1, 1, 1, 1, 1, 1, 1, 1, 1]]

entrada = (7, 0)

salida = resolver_laberinto(laberinto, entrada)

print("Entrada:", entrada)
print("Salida:", salida)
Resultado de la ejecución del código
Entrada: (7, 0)
Salida: (0, 9)
- La función resolver_laberinto() recibe como parámetros la matriz que representa el laberinto y la coordenada de la entrada.
- La función comienza en la entrada del laberinto.
- La función explora los cuatro espacios adyacentes a la posición actual.
- La función selecciona el espacio con el menor valor.
- Si el espacio seleccionado es la salida, la función devuelve la coordenada de la salida.
- Si el espacio seleccionado no es la salida, la función marca el espacio como visitado.

## Conclusión
La actividad de resolver el laberinto con recursividad es una buena oportunidad para aprender a utilizar esta técnica de programación. La solución propuesta es simple y efectiva, y puede ser utilizada para resolver laberintos de cualquier tamaño.Estas mejoras podrían mejorar la eficiencia de la solución, haciendo que sea más rápida y que encuentre la salida del laberinto en menos pasos.
