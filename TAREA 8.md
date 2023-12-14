
## 8.- Reglas y Búsquedas : Espacio de Estados

# Introducción: 
**Definición de espacio de estados**
En Inteligencia Artificial (IA), un espacio de estados es una representación abstracta de un problema. Se compone de un conjunto de estados, un conjunto de reglas que definen cómo se pueden transformar los estados entre sí, y una función de meta que indica si un estado es una solución al problema.
**Funciones de reglas**
Las reglas son un conjunto de instrucciones que definen cómo se pueden transformar los estados. En un espacio de estados, las reglas pueden definir acciones que pueden realizarse, cambios que pueden ocurrir en el entorno, o cualquier otra condición que pueda afectar a un estado.
Las funciones de reglas tienen las siguientes funciones:
- Definir el conjunto de estados posibles
- Definir las acciones que se pueden realizar
- Definir los cambios que pueden ocurrir en el entorno
- Definir las condiciones que deben cumplirse para alcanzar una solución
**Búsquedas**
Una búsqueda es un proceso que se utiliza para encontrar una solución a un problema. En el contexto de los espacios de estados, una búsqueda consiste en explorar el espacio de estados para encontrar un estado que cumpla la función de meta.
Existen muchos algoritmos de búsqueda diferentes, cada uno con sus propias ventajas y desventajas. 

Algunos de los algoritmos de búsqueda más comunes son:
- Búsqueda en anchura (BFS): Explora el espacio de estados de forma secuencial, comenzando por el estado inicial y expandiendo cada estado uno a uno.
- Búsqueda en profundidad (DFS): Explora el espacio de estados de forma recursiva, expandiendo cada estado hasta llegar a un estado sin sucesores.
- Búsqueda A:* Es un algoritmo de búsqueda heurística que utiliza una función de evaluación para priorizar los estados que parecen ser más prometedores.

Generar el espacio de estados de los siguientes problemas:

El juego consiste en pasar las 3 ranas verdes a la derecha y las 3 ranas marrones a la izquierda.  Las ranas pueden saltar a una piedra vacía que tengan delante, o saltar por encima de otra rana si en medio de ambas hay una piedra vacía. Pulsa sobre la rana que quieres que salte.

El espacio de estados del problema del juego de las ranas se define como sigue:
- Conjunto de estados: Un estado del espacio de estados es una representación de la disposición actual de las ranas en el tablero. Cada estado se representa como una cadena de 6 caracteres, donde cada carácter representa la posición de una rana. Los caracteres posibles son: 
    - A: rana verde
    - M: rana marrón
    - x: piedra vacía
    
Por ejemplo, el siguiente estado representa una disposición inicial del tablero:
VMVMVMVM
-   Reglas: Las reglas del espacio de estados definen cómo se pueden transformar los estados entre sí. En el caso del juego de las ranas, las reglas son las siguientes:
    - Una rana puede saltar a una piedra vacía que tenga delante.
    - Una rana puede saltar por encima de otra rana si en medio de ambas hay una piedra vacía.
-   Función de meta: La función de meta del espacio de estados indica si un estado es una solución al problema. En el caso del juego de las ranas, un estado es una solución si las ranas verdes están todas a la derecha y las ranas marrones están todas a la izquierda.

Cantidad de estados
El número de estados posibles en el espacio de estados del juego de las ranas es finito, pero muy grande. Se puede calcular como sigue:
N = (6!) * 3! * 3!
donde:
•	6! es el número de permutaciones de 6 elementos
•	3! es el número de permutaciones de 3 elementos
•	3! es el número de permutaciones de 3 elementos
Por ejemplo, para el caso de un tablero de 3x3, el número de estados posibles es:
N = (6!) * 3! * 3! = 4320

Tres misioneros se perdieron explorando una jungla. Separados de sus compañeros, sin alimento y sin radio, solo sabían que para llegar a su destino debían ir siempre hacia adelante.  Los tres misioneros se detuvieron frente a un río que les bloqueaba el paso, preguntándose que podían hacer. De repente, aparecieron tres caníbales llevando un bote, pues también el los querían cruzar el río. Ya anteriormente se habían encontrado grupos de misioneros y caníbales, y cada uno respetaba a los otros, pero sin confiaren ellos.  
Conjunto de estados: Un estado del espacio de estados es una representación de la disposición actual de los misioneros y los caníbales en el bote. Cada estado se representa como una cadena de 6 caracteres, donde cada carácter representa la posición de una persona. Los caracteres posibles son: 
- M: misionero
- C: caníbal
- x: piedra vacía

Por ejemplo, el siguiente estado representa una disposición inicial de los misioneros y los caníbales en el bote:
MCMCM
- Reglas: Las reglas del espacio de estados definen cómo se pueden transformar los estados entre sí. En el caso del problema de los misioneros y los caníbales, las reglas son las siguientes:
  - El bote puede transportar hasta tres personas.
  - El número de misioneros en el bote debe ser igual o mayor que el número de caníbales en el bote.
   - No se puede dejar a un misionero solo en un lado del río.

•	Función de meta: La función de meta del espacio de estados indica si un estado es una solución al problema. En el caso del problema de los misioneros y los caníbales, un estado es una solución si todos los misioneros están en el mismo lado del río, y todos los caníbales están en el otro lado del río.
Ejemplo de estados
A continuación se muestran algunos ejemplos de estados del espacio de estados del problema de los misioneros y los caníbales:
MCMCM
MCMCC
CMCMM
CMMMC
CCMMM
CMCCC
Cantidad de estados
El número de estados posibles en el espacio de estados del problema de los misioneros y los caníbales es finito, pero muy grande. Se puede calcular como sigue:
N = (6!) / (3! * 3!)
donde:
- 6! es el número de permutaciones de 6 elementos
- 3! es el número de permutaciones de 3 elementos
Por ejemplo, para el caso de un río de dos lados, el número de estados posibles es:
N = (6!) / (3! * 3!) = 20
**Algoritmos de búsqueda**
El espacio de estados del problema de los misioneros y los caníbales puede ser explorado utilizando algoritmos de búsqueda como BFS, DFS o A*.

- BFS: BFS explorará el espacio de estados de forma secuencial, comenzando por el estado inicial y expandiendo cada estado uno a uno. BFS encontrará la solución más corta al problema, pero puede ser muy lento si el espacio de estados es muy grande.

- DFS: DFS explorará el espacio de estados de forma recursiva, expandiendo cada estado hasta llegar a un estado sin sucesores. DFS puede encontrar una solución más larga al problema, pero puede encontrarla más rápidamente que BFS si el espacio de estados es muy grande.
-
- A:* A* es un algoritmo de búsqueda heurística que utiliza una función de evaluación para priorizar los estados que parecen ser más prometedores. A* puede encontrar la solución más corta al problema, pero puede ser más complejo de implementar que BFS o DFS.

Solución al problema
El problema de los misioneros y los caníbales se puede resolver utilizando un algoritmo de búsqueda. Un algoritmo de búsqueda es un proceso que se utiliza para encontrar una solución a un problema. En el caso del problema de los misioneros y los caníbales, el problema es encontrar una secuencia de movimientos que lleve a todos los misioneros a un lado del río, y a todos los caníbales al otro lado del río.
Una solución al problema de los misioneros y los caníbales es la siguiente:
1.	Llevar dos misioneros y un caníbal al lado opuesto del río.
2.	Volver con un misionero.
3.	Llevar dos caníbales al lado opuesto del río.
4.	Volver con el último misionero.

Los caníbales se daban un festín con los misioneros cuando les superaban en número. Los tres caníbales deseaban ayudar a los misioneros a cruzar el río, pero su bote no podía llevar más de dos personas a la vez y los misioneros no querían que los caníbales les superaran en número. ¿Cómo puede resolverse el problema, sin que en ningún momento haya más caníbales que misioneros en cualquier orilla del río? recuerda que un misionero y un caníbal en una orilla del río más uno o dos caníbales en el bote al mismo lado, significa que los misioneros tendrán problemas.
El espacio de estados del problema de los misioneros, los caníbales y el bote se define como sigue:
- Conjunto de estados: Un estado del espacio de estados es una representación de la disposición actual de los misioneros, los caníbales y el bote. Cada estado se representa como una cadena de 9 caracteres, donde cada carácter representa la posición de una persona. Los caracteres posibles son: 
    - M: misionero
    - C: caníbal
    - x: piedra vacía

Por ejemplo, el siguiente estado representa una disposición inicial de los misioneros, los caníbales y el bote:
MCMCCM
Reglas: Las reglas del espacio de estados definen cómo se pueden transformar los estados entre sí. En el caso del problema de los misioneros, los caníbales y el bote, las reglas son las siguientes

- El bote puede transportar hasta dos personas.
- El número de misioneros en el bote debe ser igual o mayor que el número de caníbales en el bote.
- No se puede dejar a un misionero solo en un lado del río.
- No se puede dejar a un misionero y un caníbal en el mismo lado del río, con dos o tres caníbales en el bote.
- Función de meta: La función de meta del espacio de estados indica si un estado es una solución al problema. En el caso del problema de los misioneros, los caníbales y el bote, un estado es una solución si todos los misioneros están en el mismo lado del río, y todos los caníbales están en el otro lado del río.

Ejemplo de estados
A continuación se muestran algunos ejemplos de estados del espacio de estados del problema de los misioneros, los caníbales y el bote:
MCMCCM
MCMCCx
CMCMMx
CMMMCx
CCMMMx
CMCCCx
MCMxCx
MCMxCM
Cantidad de estados
El número de estados posibles en el espacio de estados del problema de los misioneros, los caníbales y el bote es finito, pero muy grande. Se puede calcular como sigue:
N = (9!) / (3! * 3!)
donde:
- 9! es el número de permutaciones de 9 elementos
- 3! es el número de permutaciones de 3 elementos

Por ejemplo, para el caso de un río de dos lados, el número de estados posibles es:
N = (9!) / (3! * 3!) = 504
Solución al problema

El problema de los misioneros, los caníbales y el bote se puede resolver utilizando un algoritmo de búsqueda. Un algoritmo de búsqueda es un proceso que se utiliza para encontrar una solución a un problema. En el caso del problema de los misioneros, los caníbales y el bote, el problema es encontrar una secuencia de movimientos que lleve a todos los misioneros a un lado del río, y a todos los caníbales al otro lado del río, sin que en ningún momento haya más caníbales que misioneros en cualquier orilla del río.
Una solución al problema de los misioneros, los caníbales y el bote es la siguiente:
1.	Llevar dos misioneros al lado opuesto del río.
2.	Volver con un misionero.
3.	Llevar un caníbal al lado opuesto del río.
4.	Volver con un misionero.
5.	Llevar un misionero al lado opuesto del río.
6.	Volver con un caníbal.
7.	Llevar un caníbal al lado opuesto del río.
Esta solución es la más eficiente, ya que requiere solo siete movimientos. Sin embargo, existen otras soluciones posibles, algunas de ellas más complejas.
Una solución alternativa
Una solución alternativa al problema de los misioneros, los caníbales y el bote es la siguiente:
1.	Llevar un misionero al lado opuesto del río.
2.	Volver con un caníbal.
3.	Llevar un misionero al lado opuesto del río.
4.	Volver con un misionero.
5.	Llevar un caníbal al lado opuesto del río.
6.	Llevar un misionero al lado opuesto del río.
Esta solución también requiere solo siete movimientos, pero es diferente de la solución anterior.
## Conclusión :

El uso de generadores de estados, reglas y búsquedas ha permitido a la IA resolver problemas que antes eran imposibles o muy difíciles de resolver. Por ejemplo, la IA se ha utilizado para desarrollar sistemas de planificación que pueden planificar rutas de vuelo para aviones, sistemas de juegos que pueden jugar a juegos complejos como el ajedrez o el go, y robots que pueden realizar tareas complejas en entornos peligrosos.
En conclusión, los generadores de estados, las reglas y las búsquedas son herramientas poderosas que permiten a la IA resolver problemas de manera eficiente y eficaz.

