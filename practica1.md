- [Volver al menú principal](README.md)
  
# Práctica 1. Introducción a la Inteligencia Artificial Actividad 1
## Ensayo 1.1: Inteligencia Artificial, un enfoque moderno

#### Introducción 
La inteligencia artificial (IA) ha emergido como un campo fascinante y trascendental en el ámbito de la tecnología y la ciencia. Este ensayo se sumergirá en los capítulos 1, 2, 26 y 27 del libro "Inteligencia Artificial: Un Enfoque Moderno" de Stuart Russell y Peter Norvig. Ya que con estos capitulos nos permite desentrañar los fundamentos esenciales, los desarrollos actuales y las perspectivas futuras presentadas por los renombrados autores.

En los primeros capítulos, Russell y Norvig establecen los cimientos teóricos de la inteligencia artificial, explorando sus definiciones, objetivos y desafíos inherentes. A medida que avanzamos hacia el capítulo 26 y 27, el foco se desplaza hacia áreas más avanzadas, probablemente tocando temas cruciales que moldean la IA en el contexto moderno.

Este ensayo se propone explorar cómo los autores desarrollan y conectan conceptos a lo largo de estos capítulos, examinando las implicaciones de sus ideas en el panorama actual de la inteligencia artificial.

#### Desarrollo
***Capitulo 1: Introducción***
En el ámbito de la inteligencia artificial, la búsqueda por replicar los procesos mentales y el razonamiento humano ha sido un enfoque fascinante. Este enfoque, según Russell y Norvig, se centra en la idea de construir sistemas que imiten la cognición humana. Algunos ejemplos notables incluyen algoritmos de aprendizaje profundo que intentan modelar la estructura y la función del cerebro humano. Sin embargo, este camino no está exento de desafíos éticos, ya que la imitación ciega de la mente humana plantea preguntas sobre la originalidad y la singularidad de la inteligencia artificial. ¿Hasta qué punto podemos considerar que un sistema que imita el pensamiento humano es, de hecho, inteligente? Este enigma plantea cuestionamientos cruciales sobre la ética y la identidad en el desarrollo de la inteligencia artificial.

En este primer capítulo se establece los fundamentos esenciales de la inteligencia artificial (IA). En este apartado introductorio, los autores exploran los conceptos fundamentales de la IA, su historia y sus aplicaciones actuales y potenciales.

La IA se define como el estudio de agentes inteligentes: cualquier dispositivo que perciba su entorno y tome acciones que maximicen sus posibilidades de éxito para alcanzar sus objetivos. Este enfoque ofrece una visión amplia, desde sistemas simples hasta complejas redes neuronales, con el objetivo de emular el pensamiento humano y las capacidades cognitivas.
También se resaltan la evolución histórica de la IA, desde sus inicios con Alan Turing y su concepto de máquinas capaces de pensar, hasta los avances contemporáneos que han llevado a la creación de sistemas expertos, aprendizaje automático y procesamiento del lenguaje natural. Además de que explican los diferentes enfoques en la IA, incluyendo sistemas basados en reglas, aprendizaje automático, redes neuronales y procesamiento del lenguaje natural. Discuten cómo cada uno de estos enfoques aborda problemas específicos y cómo pueden combinarse para crear sistemas más complejos y versátiles.
Hay diversas aplicaciones de la IA que se exploran en este capítulo enfocado en la vida cotidiana, desde los motores de búsqueda hasta los sistemas de recomendación en plataformas de streaming y las tecnologías utilizadas en vehículos autónomos. Se resalta cómo la IA ha permeado múltiples sectores, transformando la forma en que interactuamos con la tecnología y con el mundo que nos rodea.
Los autores también plantean la importancia de considerar las implicaciones éticas y sociales de la IA. Se aborda el impacto en el empleo, la privacidad, la equidad y la responsabilidad de los sistemas de IA, destacando la necesidad de un enfoque ético en el desarrollo y aplicación de esta tecnología. Por ejemplo, en una parte del capitulo se plantea de que varios psicólogos adoptaron la idea de que los humanos y los animales podían considerarse máquinas de procesamiento de información. Esto con el enfoque más ético y hasta filosófico el cual se tiene en este apartado.

***Capitulo 2: Agentes inteligentes***
Ya entendiendo las cuestiones de que puede ser la inteligencia artificial y varios de los muchos factores que involucra esta nueva tecnología, ahora sigue hablar de un componente elemental de la Inteligencia Artificial: *los agentes inteligentes*. Este capitulo nos sumerge en la definición de un agente, revelando su capacidad de percibir y actuar en un entorno a través de sensores y actuadores. El texto resalta la diversidad de agentes, desde humanos con órganos sensoriales y partes del cuerpo para actuar hasta robots que reciben información digital y se comunican a través de redes.

Se establece que la percepción de un agente consiste en recibir entradas en cualquier momento, reflejando un historial completo de lo que ha recibido. Además, se subraya la importancia de la secuencia de percepciones en la toma de decisiones de un agente. Esta secuencia completa guía las acciones y decisiones del agente, definiendo su comportamiento. Esta relación entre percepción y acción se describe matemáticamente a través de la función del agente, que mapea percepciones a acciones posibles.

La complejidad de esta función se reconoce, mencionando que, en teoría, se podría caracterizar todo el comportamiento de un agente a través de una tabla que relacione todas las posibles secuencias de percepciones con las acciones correspondientes. Sin embargo, se enfatiza que esta tabla sería impracticable en la mayoría de los casos debido a su tamaño infinito, a menos que se limite la secuencia de percepciones considerada.

Además, se distingue entre la función del agente, una descripción abstracta y matemática, y el programa del agente, que representa la implementación concreta sobre la arquitectura del agente.

También se menciona que un agente racional se caracteriza por su habilidad para tomar decisiones correctas, es decir, para seleccionar acciones que conduzcan a resultados favorables. La noción de "lo correcto" se vincula estrechamente con la obtención de un resultado superior. Es esencial, por tanto, establecer medidas de rendimiento que determinen el éxito en el desempeño del agente.

Estas medidas de rendimiento se basan en los criterios que evalúan la idoneidad del comportamiento del agente en su entorno. Al interactuar con su medio, el agente genera una secuencia de acciones que afectan directamente los estados del entorno. Si esta secuencia de acciones conduce al estado deseado del entorno, se considera que el agente ha actuado de manera acertada.

Sin embargo, la determinación de medidas de rendimiento adecuadas no es una tarea universal. Cada agente puede requerir criterios específicos de evaluación, lo que complica la búsqueda de una medida única para todos los casos. La tentación de obtener opiniones subjetivas del agente sobre su desempeño surge, pero esto puede ser problemático, ya que muchos agentes no pueden expresar su opinión o podrían engañarse a sí mismos.

En este contexto, la necesidad de emplear medidas de rendimiento objetivas cobra relevancia. Estas medidas, por lo general, son determinadas por el diseñador responsable de la creación del agente. La objetividad en estas medidas se erige como un pilar fundamental para garantizar la eficacia y coherencia en la evaluación del desempeño del agente en su entorno.

La racionalidad de un agente se fundamenta en cuatro elementos clave que moldean su comportamiento en un entorno dado: la medida de rendimiento que establece el criterio de éxito, el conocimiento adquirido sobre el medio, las acciones disponibles para el agente y la secuencia de percepciones hasta el momento presente. En consecuencia, la definición de un agente racional se asienta en la premisa de que, en cada secuencia de percepciones, el agente debe ejecutar la acción que maximice su medida de rendimiento. Esta elección se basa en las pruebas proporcionadas por la secuencia de percepciones y en el conocimiento previamente almacenado por el agente.

Lo más interesante de este capitulo es sobre a lo que se refiere a los programas de agentes los cuales son 4. Los agentes reactivos simples son aquellos que reaccionan directamente a las percepciones que reciben en un momento dado, sin mantener un estado interno complejo. Su comportamiento se centra únicamente en responder a estímulos inmediatos sin considerar un contexto más amplio. Por otro lado, los agentes reactivos basados en modelos tienen la capacidad de mantener un estado interno que les permite rastrear aspectos del mundo que pueden no ser evidentes en las percepciones actuales. Esto les otorga la capacidad de tomar decisiones más informadas al considerar un contexto más amplio que trasciende las percepciones inmediatas.
Los agentes basados en objetivos actúan con la intención de alcanzar metas específicas establecidas para ellos. Su comportamiento se dirige hacia la consecución de estos objetivos, y sus acciones están guiadas por la búsqueda activa de lograr resultados específicos.
En contraste, los agentes basados en utilidad buscan maximizar una "felicidad" deseada, donde esta "felicidad" se define en términos de una función de utilidad que cuantifica la preferencia del agente por los diferentes resultados posibles. Estos agentes toman decisiones con el objetivo de maximizar esta utilidad, considerando las posibles consecuencias de sus acciones a largo plazo.

***Capitulo 26: Fundamentos filosóficos***
En esta parte del libro se establecen varios fundamentos mucho más filosóficos sobre la inteligencia que son muy interesantes de analizar y tomar en cuenta en lo que se refiere a la inteligencia como concepto y una cuestión filosófica por si misma.

Primero se habla sobre la distinción entre IA débil y fuerte. Aquí se plantea una división crucial en la comprensión de la capacidad de las máquinas para comportarse de manera inteligente. La IA débil sugiere la posibilidad de que las máquinas puedan simular comportamientos inteligentes sin poseer una mente real, mientras que la IA fuerte desafía la noción al afirmar que estas máquinas poseen mentes reales. Este debate filosófico se convierte en el epicentro de la discusión sobre la verdadera naturaleza de la inteligencia artificial y sus implicaciones éticas y cognitivas. Para este tema se toma habla de algo que me intereso el cual es el *teorema de la incompletitud de Gödel* o el *argumento de la informalidad*.

Ya hablando más de lo que es la inteligencia fuerte, la que se asemejaría a la nuestra, se habla de Alan Turing. Éste propuso un enfoque pragmático al rechazar la pregunta abstracta sobre la capacidad de las máquinas para pensar y, en su lugar, propuso el famoso Test de Turing, centrándose en el comportamiento observable de las máquinas. A pesar de la importancia histórica del test, muchos investigadores contemporáneos en IA prefieren evaluar el rendimiento de los sistemas en tareas prácticas en lugar de aspirar a una imitación completa del pensamiento humano.

Después de hablar sobre la IA débil y fuerte, el capitulo se adentra a cuestiones ya filosoficas que llevan presentandose desde hace mucho tiempo sobre el cuestionamiento de la mente y el cuerpo. El consenso actual apunta a que los estados mentales están intrínsecamente ligados a los estados cerebrales. Esta noción, respaldada por avances en neurociencia cognitiva, plantea la idea de que la mente y la conciencia tienen una base física en el cerebro, lo que influye en cómo se comprende y se aborda la creación de sistemas de inteligencia artificial.

Un punto muy interesante e importante de este capitulo es el enigma de la conciencia. A pesar de los avances en el campo, la consciencia sigue siendo un misterio sin resolver. La comprensión de cómo emerge la conciencia en el cerebro y cómo podría ser replicada o emulada en sistemas artificiales sigue siendo un área de gran interrogante y especulación.

Y por último se habla de las amenzas o riesgos que puede generar la IA y las cuales son cuestiones que de las que se hablan hoy en día. Para esto se identificaron ocho amenazas potenciales para la sociedad relacionadas con la IA y tecnologías afines destaca preocupaciones éticas significativas. Entre estas amenazas se encuentran escenarios en los que máquinas ultrainteligentes podrían redefinir radicalmente nuestro futuro, y la preocupación de que la robótica facilite a individuos con psicopatías el acceso a armas de destrucción masiva. Sin embargo, se argumenta que estas preocupaciones pueden estar más arraigadas en la biotecnología y nanotecnología que en la propia robótica.

***Capitulo 27: IA presente y futuro***
Y para el último capitulo del libro, se sumerge a cuestiones de lo que representa la IA en nuestro presente y lo que podría representar ésta en un futuro. El ascenso imparable de los computadores inteligentes plantea una interrogante fundamental: ¿se usará esta potencia para el bien o el mal? Aquellos involucrados en el desarrollo de la IA cargan con la responsabilidad de garantizar un impacto positivo de sus creaciones. Los modestos logros ya alcanzados han transformado la pedagogía informática y las prácticas de desarrollo de software. La IA ha propiciado aplicaciones revolucionarias como los sistemas de reconocimiento de voz, control de inventarios, vigilancia, robots y motores de búsqueda.

Los éxitos a nivel medio en IA se anticipa que influenciarán la vida cotidiana de personas de todo ámbito. Aunque las redes de comunicación computarizadas, como los teléfonos móviles e Internet, han tenido un efecto penetrante en la sociedad, la IA aún no ha logrado un impacto similar. Imaginamos que asistentes personales realmente útiles podrían mejorar las vidas, aunque podrían generar perturbaciones económicas a corto plazo. A gran escala, el éxito en la IA, alcanzando e incluso superando la inteligencia humana, transformaría la vida de la mayoría de la humanidad. Este nivel de avance podría suponer una amenaza directa para la autonomía, la libertad y, posiblemente, la supervivencia humana. Por estas razones, la investigación en IA no puede obviar sus implicaciones éticas.

Y en la última parte del capitulo nos hace preguntarnos: ¿Qué depara el futuro? Las visiones de los autores de ciencia ficción tienden hacia futuros anti-utópicos, probablemente por la riqueza de los debates que generan. No obstante, hasta el momento, la IA se alinea con otras tecnologías revolucionarias cuyos aspectos negativos son compensados por sus avances positivos en la sociedad.

#### Conclusión
En los primeros capítulos, la claridad conceptual al definir la IA y abordar su complejidad ha establecido una base sólida para entender su alcance y sus desafíos. A medida que avanzamos hacia los capítulos posteriores, la exploración de temas como el aprendizaje automático, la ética y la toma de decisiones en entornos inciertos refleja la riqueza y la amplitud de este campo multidisciplinario.

El apartado de los capítulos 26 y 27 ha proporcionado una perspectiva detallada sobre áreas específicas, llevándonos a reflexionar sobre cuestiones filosóficas de las que tal vez no se pasaron por la cabeza en su momento cuando oimos hablar de la IA y todo lo que conlleva más allá de una simple amenaza u oportunidad que nos presenta la tecnología hoy en día.

Este recorrido no solo ha ofrecido una comprensión más profunda de la IA, sino que también ha suscitado preguntas cruciales sobre el papel de la humanidad en el desarrollo y la implementación de esta tecnología. La responsabilidad ética y la preocupación por el impacto social deben acompañar cada avance tecnológico, como destacan Russell y Norvig.

En conclusión, esta obra no solo representa un compendio exhaustivo de conocimientos sobre inteligencia artificial, sino que también sirve como un llamado a la reflexión y la acción consciente en el diseño y la utilización de estas herramientas poderosas. Con este libro se nos recuerda que la IA no solo se trata de capacidades técnicas, sino también de la responsabilidad y el impacto en la sociedad que debe acompañar cada avance.

## Ensayo 1.2 - Inteligencia Artificial - (Documental IBM) 

#### Introducción 

#### Desarrollo 

#### Conclusión



- [Volver al menú principal](README.md)