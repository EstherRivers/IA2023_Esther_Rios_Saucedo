# Ensayo: Identificador de Islas
                             Esther Ríos Saucedo
## Introducción

La inteligencia artificial (IA) ha experimentado un crecimiento exponencial en las últimas décadas, impulsada por avances en el aprendizaje automático, la computación en la nube y la disponibilidad de grandes cantidades de datos. Sin embargo, a pesar de estos avances, la IA aún enfrenta desafíos importantes en la resolución de problemas que requieren lógica y razonamiento. En este contexto, la introspección emerge como una herramienta prometedora que puede potenciar la IA para abordar estos desafíos.

La introspección, en términos simples, es la capacidad de un sistema para examinar sus propios estados internos, incluyendo sus conocimientos, creencias, objetivos y procesos de razonamiento
Identificación de las islas
La forma en en la que trate de analizar el problema es visualizando una tabla donde se podrían relacionar el 1 como un espacio lleno y 0 como un espacio vacío, ahora bien, para se se puede considerar una isla con respecto a la siguiente imagen es que varios espacios llenos estén en secuencia.
 
Se podría usar como base el ejemplo que se planteado en clase de las barredoras automáticas ya que ellas al detectan un objeto que impide su paso rodean buscan un camino libre para seguir, desarrollando los contornos de la ubicación de los objetos de esta manera crean un mapa con la ubicación de estos mismos, de igual manera podemos basarnos en esta premisa para la búsqueda de islas. 
Para identificar las islas, se puede utilizar un algoritmo de exploración. El cual comienza en un punto de la imagen y luego explora los puntos adyacentes. Si el punto adyacente tiene el mismo color que el punto inicial, se considera parte de la misma isla.
| 1 | 2 |3 |
| - | - |--|


De esta manera empezaría con el primer recuadro hasta el tercero determinado que la unión de estos forma una isla, tomando en cuenta que no todas las islas tendrían la misma longitud se tendría que hacer un barrido de derecha a izquierda y de arriba hacia abajo.

En este caso, se puede utilizar un algoritmo de exploración BFS (Breadth-First Search). El algoritmo BFS comienza en un punto de la imagen y luego explora los puntos adyacentes en orden. Si el punto adyacente tiene el mismo color que el punto inicial, se agrega al conjunto de islas posteriormente se realiza un contador par cuando encuentre una incremente el número de islas encontradas.

## Enfoque iterativo
Este enfoque hace un recorrido de la imagen pixel a pixel, y para cada pixel, determinar si pertenece a una isla o no. Si pertenece a una isla, se incrementa el contador de islas.
Variables: cont =contador, c=columna, f=fila.
def contar_islas_iterativo(imagen):
 cont = 0
  for f in imagen:
    for c in f:
      if c == 1:
        cont += 1
  return cont
 
La desventaja de este enfoque es que si queremos analizar imágenes grandes no es muy recomendable por el tiempo.
Enfoque recursivo
El enfoque recursivo consiste en segmentar la imagen en regiones más pequeñas, y posteriormente contar el número de islas en cada sección. Las divisiones de las imágenes podrán adaptarse según la necesidad.
Variables: fi=fila_inicial, ff= fila_final, ci= columna_inicial y cf= columna_final
def contar_islas_recursivo(imagen, fi, ci, ff, cf):
  if fi == ff or ci == cf:
    return 0
  else:
    if imagen[fi][ci] == 0:
      return 0
    else:
      return 1 + contar_islas_recursivo(imagen, fi + 1, ci, ff, cf) + \
            contar_islas_recursivo(imagen, fi, ci + 1, ff, cf) + \
            contar_islas_recursivo(imagen, fi + 1, ci + 1, ff, cf)

 

## Conclusiones
La implementación de dichos enfoques dependerá desde el tamaño de las imágenes como sus características, pero en general ambos enfoques nos dan una solución efectiva.

