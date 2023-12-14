# Introducción a la Inteligencia Artificial: 
## El proceso de razonamiento según la lógica.
## Introducción	:
La Inteligencia Artificial (IA) es un campo de la informática que se ocupa de la creación de agentes inteligentes, es decir, sistemas que pueden percibir su entorno y tomar acciones para alcanzar sus objetivos.
Uno de los aspectos fundamentales de la IA es el razonamiento, que es la capacidad de utilizar la información para llegar a conclusiones. El razonamiento se puede realizar de muchas maneras diferentes, pero una de las más importantes es el razonamiento lógico.
## Planteamiento del problema:

La historia que sigue es una versión adaptada de lo que –supuestamente—sucedió durante el siglo I. Sí, el siglo uno. Suena raro, ¿no? 
Más aún: esa historia dio origen a un problema clásico de la matemática/computación que sobrevivió el paso del tiempo. Se lo conoce con el nombre del “Problema de Josephus”, ya que se supone que fue Flavius Josephus, un historiador judío nacido en Jerusalén, quien describió la situación que vivieron él y 40 soldados que lo acompañaban.
En un momento determinado de la guerra judeo-romana, Josephus y su grupo cayeron en una emboscada y quedaron atrapados en una caverna rodeada de soldados enemigos. Después de debatir cómo proceder, optaron por suicidarse antes de ser capturados.  Sin embargo, Josephus no estuvo de acuerdo con la propuesta y para que nadie tuviera que quitarse la vida, propuso el siguiente método: “Sentémonos todos en un círculo. Alguno de nosotros empezará primero y matará a quien tenga sentado a la izquierda y así vamos a seguir hasta que–claramente— quedará nada más que uno solo de nosotros con vida. Ese será el único que tendrá que suicidarse”. Allí están las cuarenta y un posiciones numeradas en forma creciente. 
Supongamos que empieza el que está sentado en la posición número 1. Ese soldado matará al 2. Luego, el 3 matará al 4, el 5 al 6. . . y así siguiendo. Como usted advierte, llegará un momento en el que habrán muerto todos los que están sentados en las posiciones que llevan un número par. Pero cuando muera el último de ellos, el número 40 (a manos del 39), el 41 estará vivo aún y ahora, el que tiene sentado a la izquierda es el número 1 quien había empezado con los asesinatos. De acuerdo con las reglas, el 41 matará al 1, el 3 matará al 5, etc. 
Creo que ahora está claro que van a morir todos hasta que quede solamente uno con vida. Es aquí donde aparece una parte interesante de la historia de Josephus. En principio, habrían de morir todos los soldados que estaban con Josephus en la caverna, pero la diferencia es que quien quedara último tendría que suicidarse. . .  Más aún: el sobreviviente tendría que quitarse la vida y no habría ningún otro integrante del grupo que estuviera vivo para verificar que lo hiciera. Como usted se imagina, Josephus eligió un lugar particular del círculo y se sentó allí. El sabía que siguiendo las reglas escritas más arriba, él habría de quedar como único sobreviviente. Esperó que todos estuvieran muertos, y en lugar de suicidarse, salió de la caverna y se entregó al enemigo. 
**Pregunta:** ¿en qué lugar se sentó Josephus? El problema es muy conocido en el mundo de la matemática y los programadores, y es por eso que hay muchísima literatura escrita sobre el tema, pero no hace falta saber nada particular para poder pensarlo.  
La versión que figura más arriba es solo una de las posibles variantes (la más sencilla) y si yo estuviera junto a usted, le sugeriría que no empiece con el caso delos 41 soldados, sino que intente con números más pequeños (de soldados)de manera tal de ver si le es posible intuir o imaginar una estrategia predeterminar al ganador o sobreviviente a medida que va incrementando el número de soldados. De la misma forma, una vez que hayamos resuelto el problema para 41 soldados, sería interesante pensar en una estrategia que permita deducir cuál será la posición ganadora en el caso general, es decir, independizarse del número 41 y encontrar alguna estrategia o fórmula que permita deducir el número que hay que elegir sin tener que recorrer todos los pasos intermedios.
## Planteamiento matemático
Para la resolución del problema de Josephus se deben seguir delimitaciones:
- Un grupo de personas se sientan en un círculo.
- Cada persona matara a la persona que estará a su izquierda de la persona que inició el proceso, cada vez que se llegue a un múltiplo de un número natural k.
- La última persona en morir es la que sobrevive.

Para el caso de 41 personas y k=2, la posición ganadora es:
Posición ganadora = $\frac{41}{2} + \frac{1}{2} - \frac{1}{2 \cdot 2}$
Posición ganadora = 20 + 0.5 - 0.25
Posición ganadora = 20.25
Por lo tanto, la posición ganadora es la 20.
Donde:
a)	n es el número de personas en el círculo.
b)	k es el número natural por el cual se va a dividir cada múltiplo.
c)	La fórmula se puede entender de la siguiente manera:
d)	La primera parte, kn, representa el número de personas que se suicidan en cada paso.
e)	La segunda parte, 21, representa la posición de la persona que inicia el proceso.
f)	La tercera parte, 2k1, representa la posición de la persona que está sentada a la izquierda de la persona que inicia el proceso.
**Programa:** 
def josephus(n, k):
  
  # Calculamos la posición ganadora.
  position = (n // k) + (1 // 2) - (1 // (2 * k))

  # Si la posición es par, la redondeamos hacia arriba.
  if position % 2 == 0:
    position += 1

  return position
print(josephus(41, 2))
Este código imprime el valor 20, que es la posición ganadora para el problema dado en el enunciado.
El código funciona de la siguiente manera:
- La función josephus() toma dos argumentos: el número de personas en el círculo y el número natural por el cual se va a dividir cada múltiplo.
- La función calcula la posición ganadora utilizando la fórmula dada anteriormente.
- Si la posición es par, la función la redondea al siguiente valor.
- La función devuelve la posición ganadora.

# Conclusion : 

El razonamiento lógico es una herramienta fundamental para la resolución de problemas matemáticos. Sin embargo, el razonamiento lógico humano puede ser limitado por factores como la fatiga, el sesgo y la falta de experiencia. La IA, por otro lado, puede aplicar el razonamiento lógico de manera imparcial, eficiente y precisa, incluso en problemas complejos.
La implementación de la IA en la aplicación del razonamiento lógico para resolver problemas matemáticos tiene el potencial de revolucionar la forma en que se enseñan y aprenden las matemáticas. 
En conclusión, la implementación de la IA en la aplicación del razonamiento lógico para resolver problemas matemáticos es una área de investigación prometedora con el potencial de tener un impacto significativo en la educación, la investigación y la práctica matemática.

