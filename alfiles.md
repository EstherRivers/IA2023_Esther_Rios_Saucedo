## Introducción
El pensamiento cognitivo es una de las principales cuestionantes en la
rama de la inteligencia Artificial. Ya que en algunas aplicaciones se ha intentado
que las máquinas lleguen a pensar de la misma manera en que lo hace
el ser humano.
Es cierto que se ha logrado que las máquinas resuelvan problemas complejos
de una manera más rápida, incluso hasta más eficiente que el ser humano
aparentemente, pero que ha sido el resultado de diversos estudios, una gran
cantidad de tiempo y fuertes inversiones económicas, que talvez en la enseñanza
de una persona habría implicado una menor cantidad de recursos.
##  El problema
El problema consiste en lo siguiente: Coloca ocho alfiles (cuatro negros
y cuatro blancos) en un tablero de ajedrez reducido, tal como se ve en la
figura. El problema consiste en hacer que los alfiles negros intercambien sus
posiciones con los blancos, ningún alfil debe atacar en ningún momento otro
del color opuesto. Se deben alternar los movimientos, primero uno blanco,
luego uno negro, luego uno blanco y así sucesivamente.

![texto_alternativo](https://i0.wp.com/divulgadores.com/wp-content/uploads/2015/01/intercambiar_alfiles_dudeney_2.png)

## Solución
Para llegar a la solucion de esta practica como primer paso estuve analizando los primeros tres movimientos para poder establecer una estrategia a medida que fuera avanzando , basandome en las limitaciones establecidas en el problema estuve haciendo el conocido (prueba y error), lo primero que hice fue empeza a mover los alfiles del centro ya que si cuando trate de empezar por los extremos habia un momento que no podia avanzar.

Estas con las coordenas que obtuve las cuales siguen la siguiente estructura:
(posicion inicial-posicion final alfiles negros )(posicion inicial-posicion final alfiles blancos)
La manera que se utilizo para errar en las pieza ya cambiadas de posición, coloque numeros del 1-20 :
| 1 | 2 | 3 | 4 |
|---|---|---|---|
| 5 | 6 | 7 | 8 |
| 9 |10 |11 |12 |
|13 |14 |15 |16 |
|17 |18 |19 |20 |

Coordenas de solicion:
(18-15)(3-6) 
(17-8)(4-13)
 (19-14)(2-7)
 (15-5)(6-16) 
(8-3)(13-18) 
(14-9)(7-12) 
(5-10)(16-11) 
(9-19)(12-2) 
(10-13)(11-8)
(8-11)(13-4)
(2-12)(19-9)
(11-17)(20-5)
(12-15)(5-2)
(1-11)(9-19)
(15-20)(19-9)
(11-14)(9-6)
(14-19)(6-1)

[ PROCEDIMIENTO DE SOLUCION ](https://docs.google.com/spreadsheets/d/1IqNGAYZ7suI1gxzOFVA2eBKLXESXVvAz/edit?usp=sharing&ouid=100323583357984919556&rtpof=true&sd=true)



## Conclusión
La enseñanza que me dejo este problema es que más allá de valorar un resultado debemos enfocarnos en desarrollar un proceso que nos de la mejor solucion y nos ahorre de muchos errores al no  profundizar en la totalidad del problema y buscar soluciones rapidas y simples , un buen ejemplo es el cubo rubik si buscamos la solucion armando cara por cara esta seria practicamente imposible , en lugar de  esto la mejor recomendacion es analizar el problema,desarrollar la estregia y ahorrarnos de muchos procedimientos inecesarios
5. Referencias
1. Russell, S. J., Norvig, P. (2009). Inteligencia artificial (2.a ed.). Pearson
Educación.
4
Figura 4: Las líneas tienen la misma intenpretación de la Figura 3.
2. A. (2015, 31 enero). Ajedrez y matemática recreativa: Soluciones. divulgadores.
com. https://divulgadores.com/ajedrez-y-matematica-recreativasoluciones/
5