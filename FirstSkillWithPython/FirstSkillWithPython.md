Desarrollando una skill para Alexa utilizando Python

Amazon ha hecho un gran esfuerzo en acercar el desarrollo de skills para Alexa a las diferentes comunidades de desarrolladores, ofreciendo SDKs para distintos lenguajes de programación, entre ellos esta Python. Lenguaje de scripting muy elegante, sencillo, flexible sin embargo poderoso; con un amplísimo apoyo de la comunidad FLOSS y muy utilizado en diferentes industrias.

El desarrollo de skills para Alexa comprende un conjunto de pasos que describiré en este artículo, ademas incluiré referencias a otros artículos que me han sido de gran ayuda.

Considero importante que al dar los primeros pasos para desarrollar una skill nos identifiquemos, si es posible plenamente, con el motivo que nos lleva a emprender este desarrollo, puesto que, siendo muy divertido, tiene una curva de aprendizaje, que aunque no es pronunciada, requiere un esfuerzo.

En mi caso particular, al ser Católico, el querer evangelizar es algo que me atrae mucho y es inherente a mis creencias y siempre he querido hacerlo utilizando mis conocimientos de informática. Es por esto que he decidido crear una skill relacionada a la devoción por excelencia de nuestra Iglesia como lo es el Santo Rosario.

El objetivo de esta skill es bastante simple: indicar cuales son los Misterios del Santo Rosario según solicite el usuario. 

Una vez que hemos decidido que hara nuestra skill, podemos hacer una tormenta de ideas sobre frases que puedan servir para interactuar con esta. Es importante tomar en cuenta que según, se indica en el proceso de creacion de las frases que indicaran a Alexa las intenciones del usuario, estas deben ser simples y directas sin embargo no deben parecer comandos, hay ciertas recomendaciones al momento de escribir estas frases (https://developer.amazon.com/blogs/alexa/post/a3149c48-b81b-4b89-8fc3-2d11ec28a3a3/effective-ways-to-write-sample-utterances). 

### Para la skill que vamos a crear utilizaremos las siguientes frases:

- cuales son los misterios de hoy
- cuales son los misterios de mañana
- misterios de hoy
- misterios de mañana
- que misterios tocan hoy
- que misterios tocan mañana
- los misterios de hoy
- los misterios de mañana
- cuales son los misterios luminosos
- cuales son los misterios gozosos
- cuales son los misterios gloriosos
- cuales son los misterios dolorosos
- cuales son los misterios del lunes
- cuales son los misterios del martes
- cuales son los misterios del miercoles
- cuales son los misterios del jueves
- cuales son los misterios del viernes
- cuales son los misterios del sabado
- cuales son los misterios del domingo
- que misterios tocan el lunes
- que misterios tocan el martes
- que misterios tocan el miercoles
- que misterios tocan el jueves
- que misterios tocan el viernes
- que misterios tocan el sabado
- que misterios tocan el domingo
- los misterios luminosos son
- los misterios gozosos son
- los misterios gloriosos son
- los misterios dolorosos son

Afortunadamente no tenemos que escribirlas todas, podemos utilizar wildcards para los dias de la semana o incluso para los nombres de los Misterios. En este caso vamos a utilizar 2 wildcards, las llamaremos "dia" y "mysteria" (Misterios en Latin, cuestión de gustos). De esta forma las frases quedarian de la siguiente forma:

- cuales son los misterios de {dia}
- misterios de {dia}
- que misterios tocan {dia}
- los misterios de {dia}
- cuales son los misterios {mysteria}
- cuales son los misterios del {dia}
- que misterios tocan el {dia}
- los misterios {mysteria} son

/Users/fran/Desktop/Screen Shot 2018-09-20 at 15.46.32.png


### {dia} tendra los siguientes valores:
- lunes, martes, miercoles, jueves, viernes, sabado, domingo, hoy y mañana

### {mysteria} tendra los siguientes valores:
- dolorosos, gozosos, gloriosos, luminosos

