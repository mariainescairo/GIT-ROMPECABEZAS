# GIT-ROMPECABEZAS
Empezando con el Rompecabezas
Preparación
Para hacer esta primera parte del proyecto vas a poder aprovechar código pre-existente para no perder tiempo y concentrarte en aprender los temas importantes de estilado y maquetado web.

En la carpeta de recursos descargables, abrí el archivo juego.html en tu editor de texto. Si todavía no descargaste los recursos, podés hacerlo en el curso “Rompecabezas: Introducción”

En el HTML y CSS existentes vas a encontrar una estructura básica, que incluye el body con dos columnas:

col-40: una columna que ocupa 40% del tamaño del body e incluye las secciones instrucciones, objetivo y ultimo-mov
col-60: una columna que ocupa 60% del tamaño del body que contendrá al tablero.

Paso 1: Armar tablero del juego en HTML
Lo primero que vamos a hacer para empezar a darle vida a este juego es armar el tablero del juego con sus piezas. Para esto, ya contamos con un elemento con id juego que nos servirá de contenedor.

Dentro de este elemento juego tendremos que agregar las piezas. Cada una de ellas deberá ser un div y tendrá un id que la identifique: pieza1 será el id de la primera pieza, y así sucesivamente hasta pieza9. Además, deberán estar agrupadas bajo una misma clase para poder darles estilado. A la clase podés ponerle el nombre que te parezca apropiado.

Ojo: Es muy importante que las piezas tengan este id para que después funcione el juego. Si no, las funciones de JavaScript que vienen dadas no van a poder tomar el id correcto de tu HTML y no van a funcionar.
Paso 2: Agregar las imágenes a las piezas del Rompecabezas
Como próximo paso vas a tener que agregar las imágenes correspondientes que se encuentran en la carpeta images a cada uno de los <div> que representan las piezas. Cada elemento <div> que ya creaste en el paso anterior, va a tener una <img> dentro.

Todas las piezas tendrán una imagen asociada, excepto la pieza 9 que es la vacía. 
Para pensar: ¿Por qué será que las imágenes quedaron de ese tamaño y ubicadas en esos lugares?

Paso 3: Acomodar el Tamaño de los Elementos con CSS
Ahora sí, llegó la hora de darle un diseño con sentido a tu juego. Cómo pudiste ver en la imagen de ejemplo, el rompecabezas es una grilla de 3x3 elementos, es decir, 9 piezas. Ya creaste los elementos necesarios del esqueleto, ahora le vamos a dar la vida que merecen.

Para eso, debés darle al tablero del juego un alto y ancho. Para facilitar las cuentas, hacelo múltiplo de 3 y mayor a 300px.
Para identificar la grilla del juego en la pantalla, podés darle un background-color con css. En la imagen se ve el elemento HTML que representa al tablero del juego con un tamaño de 600x600px y un fondo rojizo para poder identificarlo…
Paso 4: Tamaño de las Piezas en el Tablero de Juego
Ahora tenemos que hacer que las piezas (y las imágenes contenidas en ellas) logren entrar en la grilla.

Modifica el CSS de las piezas y también el de las imágenes pensando en porcentajes. ¿Qué porcentaje del tablero ocupa una pieza? ¿Y la imagen que porcentaje del div que la contiene deberá ocupar?

Podés agregarle un borde a las imágenes para delimitarlas. Tené en cuenta que los bordes también ocupan pixeles, por lo que vas a tener que revisar el tamaño de las imágenes para que encajen en la grilla correctamente.

Probablemente, las imágenes quedaron del tamaño correcto pero no se ubicaron dentro del tablero.
Paso 5: Ubicar las Piezas en el Tablero
Solo nos queda resolver este problema: ¿Cómo hacemos que las piezas se ubiquen en el lugar que queremos?

Pista: ¿Te acordás del float? ¿Cómo lo usarías para ubicar las piezas correctamente?

Paso 6: Terminar el Estilado de la Página
Falta sólamente agregar y darle estilo a los títulos, las instrucciones y el footer. Para esto podés seguir los colores del modelo, o elegir los que más te gusten. Las instrucciones no las tendrás que agregar por ahora, serán agregadas dinámicamente desde JavaScript.

En la sección objetivo agregá la imagen final.png y dale una tamaño adecuado. Esta imagen nos mostrará cómo será el rompecabezas una vez que esté terminado.
Preparación
Abrí con el navegador el archivo que veníamos usando, juego.html.
Abrí el archivo juego.js en una pestaña del editor de texto que estés usando. Este está en la carpeta js de los recursos descargables.
Paso 1: Familiarizate con las Variables y Funciones Existentes
Variables
El arreglo de instrucciones donde cada elemento será una instrucción del juego
var instrucciones = []
El arreglo de movimientos donde iremos agregando el último movimiento realizado
var movimientos = []

El arreglo de arreglos grilla donde cada número representa a una pieza del rompecabezas
 var grilla = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
  ];
filaVacia que guarda la fila de la pieza que se encuentra vacía
columnaVacia que guarda la columna de la pieza que se encuentra vacía
var filaVacia = 2;
  var columnaVacia = 2;

Funciones ya implementadas
capturarTeclas() que detecta cuando presionan las teclas para luego poder mover las piezas.
mezclarPiezas() que mezcla las piezas aleatoriamente en el tablero cuando iniciamos el juego.
mostrarInstruccionesEnLista(arreglo, idLista) que muestra las elementos del arreglo en el elemento de HTML idLista
intercambiarPosicionesDOM(pieza1, pieza2) que intercambia la posición de las piezas en el documento HTML.
iniciar() que comienza el juego, ejecutando las funciones mezclarPiezas() y capturarTeclas().
Tené en cuenta que muchas de estas funciones van a depender de otras que tendrás que implementar vos, por lo que no todas funcionarán correctamente desde el principio.

Además, se incluyen funciones incompletas, con comentarios descriptivos de lo que cada función debería hacer. En los distintos pasos vamos a ir viendo qué funciones necesitamos completar para avanzar en el proyecto.

Nota: Asegurate de trabajar sobre el archivo juego.js y de ir completando las funciones correspondientes en cada etapa.

Paso 1: Escribir instrucciones
El objetivo de este primer paso es agregar los textos correspondientes a las instrucciones del juego. Para ello las tendrás que agregar al arreglo instrucciones que se encuentra en el código. Podés agregar todas las instrucciones que quieras, teniendo en cuenta que tengan sentido con el 
objetivo del juego.

Recordá que siempre podés chequear lo que acabas de programar desde la consola. Por ejemplo, para ver si las instrucciones las colocaste correctamente en el arreglo, podés ejecutarlo abriendo la consola y chequeando cuales son sus elementos.

Paso 2: Mostrar instrucciones
En este paso terminaremos el agregado dinámico de instrucciones al juego. Para eso debemos completar la función mostrarInstrucciones(instrucciones). Tenemos que ir recorriendo cada uno de los elementos del arreglo pasado por parámetro y aplicarle a cada instrucción la función ya implementada mostrarInstrucciónEnLista(instruccion, idLista).

Abrí el archivo HTML y fijate cuál es el id de la lista dónde deberás agregar las instrucciones.
Paso 3: Mostrar último movimiento
El arreglo de movimientos es el encargado de guardar todos los movimientos realizados en el juego desde el comienzo hasta el final. Pero esta funcionalidad no está implementada. Es por eso que tenemos que implementar una función que agregue la última dirección al arreglo de movimientos y, además, ejecutar a continuación la función ya implementada actualizarUltimoMovimiento para que se actualice el HTML.

Pista: recordá qué método de los arreglos se utiliza para agregar un nuevo elemento.

Para testear que esta función esté correctamente implementada, abrí la consola y ejecutala pasándole como parámetro un código de dirección qué podés encontrar en el código. Por ejemplo: nombreQueLeDisteALaFuncion(codigosDireccion.ABAJO). Esto debería hacer que aparezca en el HTML una flecha hacia abajo.
Preparación
Abrí con el editor de texto el archivo que veníamos usando, juego.html. Si estás usando Atom, podés hacer clic derecho sobre el código y seleccionar “Preview HTML” para ver los cambios en tiempo real de tu documento.
Usá el archivo juego.js en otra pestaña del editor de texto. Este está en la carpeta de recursos descargables que ya deberías tener guardada en tu computadora, Drive, o repositorio.
Paso 1: Definir el Tablero Ganador
El objetivo de este primer paso es completar la función chequearSiGano(), que recorra la variable grilla y devuelva true para las grillas ganadoras (ordenadas) y false para las grillas desordenadas.
Recordá que la variable grilla representa cada pieza del HTML con un número. Esta variable está en orden originalmente, pero la función mezclarPiezas() la va a desordenar cuando ejecutemos la función iniciar().

Por ejemplo, esta grilla es ganadora, porque cada pieza está en su posición correcta:

[[1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]];
Pero la siguiente grilla no es ganadora, porque las fichas 2, 3, 5 y 9 no están en sus posiciones correctas:

[[1, 5, 9],
 [4, 2, 6],
 [7, 8, 3]];
 
 Pista: Para poder resolver esto vas a tener que pensar cómo recorrer la grilla elemento por elemento. ¿Bastará con usar un sólo bucle for como en un arreglo simple?

Buenas prácticas: Es útil plantear primero todas las ideas en papel. Una vez que resuelvas como hacerlo, pasá al código. Lo importante en la programación es el pensamiento que te lleva a resolver un problema, el código es algo secundario necesario para que la computadora nos entienda.

Paso 2: Alerta Ganadora
No sólo queremos que se gane el juego cuando tenemos la grilla ganadora, sino que también queremos mostrar una alerta que avise que ganamos.

Para eso, hay que implementar la función mostrarCartelGanador(). Tenés que hacer que aparezca de alguna forma un cartel demostrando que ganaste cuando la grilla sea la correcta. Podría ser una alerta, o cualquier cosa que se te ocurra. Existen infinitas posibilidades.
Buenas prácticas: Podés usar console.log() para hacer un seguimiento del código, mostrando variables y texto, y viendo si algo falla. Para chequear si funciona, desde la consola podés escribir chequearSiGano() y debería devolver true.

Recordá que, en este primer momento, la variable grilla ya está ordenada. Por eso, apenas abras tu aplicación (refrescando el documento) y toques cualquier tecla te va a mostrar el mensaje que definiste en la función mostrarCartelGanador().

Buenas prácticas: Podés definir en el HTML y en el CSS el cartel ganador con la fuente, los colores y el tamaño que más te guste. El que damos es solo un ejemplo. ¡Dale rienda suelta a tu imaginación!

Paso 3: Intercambiar las piezas
Para intercambiar las posiciones de las piezas, tendremos que poder 
intercambiar posiciones en el arreglo de arreglo grilla.

Sabías qué: Esto es lo que llamamos un intercambio lógico y está separado de lo que es la representación visual del intercambio (que es el cambio que se realizará en la pantalla). Siempre conviene separar la lógica de lo visual para tener un mayor control sobre los cambios en nuestro proyecto. En este proyecto, la parte del intercambio ya viene implementada ya que es algo que aprenderás a hacer más adelante.

Intercambio Lógico
Para concretar el intercambio, debemos completar la función intercambiarPosiciones(filaPos1, columnaPos1, filaPos2, columnaPos2). Y sólo tendremos que interactuar con la variable grilla.

Pista: Las posiciones de la grilla se definen por su número de fila y número de columna. Empieza desde la fila cero y columna cero (0, 0), ubicada en la esquina superior izquierda. Desde ahí los números aumentan hacia la derecha y hacia abajo. La esquina de abajo a la derecha es la posición (2, 2).
Si tenemos la siguiente grilla:

[[1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]];
y aplicamos la función intercambiarPosiciones(1, 1, 1, 2) obtendremos como resultado la grilla:

[[1, 2, 3],
 [4, 6, 5],
 [7, 8, 9]];
Paso 4: Definir Movimientos Válidos
En este paso, hay que terminar la función posicionValida(fila,columna). Esta deberá avisar si la pieza puede moverse para donde queremos que se mueva (entra en el tablero de juego) o no puede (se sale del tablero).
Paso 5: Movimiento de las Piezas con el Teclado
Por último, la función moverEnDireccion(direccion) deberá hacer que cuando el/la usuario/a toca una tecla (arriba, abajo, izquierda, derecha), la pieza vacía se intercambie con la ficha vecina correspondiente. La función actualizarPosicionVacia deberá estar implementada, para que cada vez que se mueva una ficha se actualicen las variables filaVacia y columnaVacia.

Cada vez que los/as usuarios muevan las flechas del teclado, se va a ejecutar 
esta función. Para ganar el juego, esta función se ejecutará las veces necesarias hasta que el tablero esté ordenado, es decir, hasta que chequearSiGano() devuelva true.

Esta es la parte principal de la lógica del juego. Así que, primero, te recomendamos tomarte un tiempo para pensar cómo la resolverías. Leé y releé el código dado hasta entenderlo e intentá deducir cómo realizar los movimientos faltantes.

Si el movimiento es válido, se deberá agregar al arreglo de movimientos. Para es implementaste una función que hacía este trabajo. ¡No te olvides de invocarla cada vez que hagas un movimiento, así se suma correctamente!

Buenas prácticas: Pensá en papel tu solución. Si estás participando de un programa presencial o estás estudiando con un/a compañero/a, siempre es bueno pensar en grupo. ¡Dos cabezas piensan mejor que una!

Paso 6: Terminá el Juego
Tenés que completar los datos y funciones faltantes para que el juego funcione correctamente.

Recomendación: Releé todas las funciones dadas, tanto las completas como las incompletas. Fijate que estén usadas correctamente.

Ejecutá tu juego y evaluá su funcionamiento. ¿Está todo bien? ¿Podés identificar si hay algún error?
