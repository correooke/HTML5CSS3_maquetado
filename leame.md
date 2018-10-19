

#2

agregamos el contenedor principal "main" y el contenedor del pie "footer"
en el css agregamos selector de id que lleva el simbolo numeral o hash seguido del nombre del identificador del elemento. Vamos a utilizar el alto con vh que nos refiere a la altura del viewport (que sería view height), donde 100 vh será equivalente al alto total de la pantalla. 


El ancho lo establecemos a 100vw, para los dos elementos. 

También vamos a utilizar background-color para establecer el color de fondo de cada contenedor. El primero vamos a utilizar un color con nombre "orange", y el segundo vamos a utilizar la función rgb. 

#3

Ahora tenemos el contenedor principal y el pie que se ajustan de manera proporcional, lo que en realidad no es un efecto deseado. 
Para lograr que el pie tenga un tamaño fijo vamos a utilizar la unidad de medida "pixeles". Para que el contenedor principal ocupe el espacio restante de la pantalla vamos a utilizar la función de CSS3 "calc". Esta función nos permite realizar cálculos y mezclar diferentes tipos de unidades. Es una función bastante nueva, pero ya es soportada por todos los navegadores actuales.   
Utilizando calc y restando el alto que le vamos a otorgar al pie, que va a ser de 50 pixeles, vamos a darle tamaño al contenedor principal. 

Importante: 
las operaciones + y - siempre deben de estar separados de sus operandos mediante espacios en blanco

https://developer.mozilla.org/es/docs/Web/CSS/calc

#4 

Al contenedor principal le definimos un ancho máximo para que cuando la pantalla tenga un ancho mayor a 400 pixeles los elementos que tenemos en nuestra página no se exparsan ni ocupen más espacio del que queremos. Tambien utilizamos el margin auto, para que este bloque quede centrado. 

Vamos a definir también un ancho y un alto mínimo, así no se "rompe" el diseño si el usuario achica demasiado la pantalla o se ve en un teléfono con pantalla pequeña. Una vez que se achique a un tamaño inferior a 520 px de alto, o 320 px de ancho, van a aparecer las barras de scroll. 

#5

Vamos a ver cómo agregar un texto en el pie de pagina, centrarlo y aplicarle un estilo de fuente.
Primero agregamos el elemento "p", principalmente utilizado para párrafos, y escribimos el texto que estaba definido en el diseño. 
Luego en el css vamos a asignar un color de fuente al selector del elemento contenedor principal, así todo el texto que ubiquemos dentro de este contenedor adquiere ese color por defecto. En este caso vamos a utilizar un color con nombre, con una palabra clave que representa al color blanco. 

Luego para que el texto quede centrado horizontalmente vamos a utilizar "text-align" center. 

Al texto podemos cambiarle el tamaño y la tipografía, mediante la propiedad "font". Primero definimos el tamaño en 14 pixeles, (tambien se suele utilizar la medida em) y seguido, definimos el tipo de fuente a Helvetica. Si el navegador no tuviera ese tipo de fuente, definimos una fuente por defecto genérica, "sans-serif".
Por último, le vamos a establecer el grosor de la fuente en bold, esto se hacer mediante la propiedad font-weight.

https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color

#6 

Vamos a centrar el texto del footer en la vertical. Para eso vamos a utilizar un tipo de selector CSS que nos permite hacer referencia a elementos que se encuentran dentro de un elemento contenedor. En este caso vamos a hacer referencia a todos los elementos del tipo "p" que esten dentro del elemento identificado como "footer-cont". Para el caso, tenemos un único elemento, pero podrían ser varios, y este selector estaría afectando a todos los que existiesen. 
Vamos a establecer el alto de línea con la propiedad "line-height", y vamos a igualar este alto al alto del contenedor. Por eso le asignamos el valor de 50 pixeles. 

#7

Vamos a agregar el logo que se va a ubicar en la parte superior del contenedor principal. 
Para eso primero vamos a descargar el recurso y vamos a crear una carpeta llamada "img" y lo vamos a copiar dentro de esa carpeta. 
Luego, dentro de "main-cont" creamos un elemento img con el identificador "logo". 
En la propiedad src del elemento indicamos en forma relativa la carpeta donde se encuentra el archivo de la imagen del logo y en "alt" ponemos un texto alternativo que aparecerá cuando la imagen no pueda cargar correctamente.
También ayudará a usuarios que tengan problemas de visión. Las reglas generales son que el texto debería describir la información que contiene la imagen, pero en caso de ser una imagen totalmente decorativa esta propiedad puede quedar vacía. Por eso en este caso lo vamos a dejar vacío. 
Creamos un selector de id en css para el logo, y le establecemos el ancho a 100%, esto significa que va a ocupar la totalidad del ancho.

#8

Para respetar el diseño, todos los elementos que esten dentro del contenedor principal main-cont, deberían tener un margen o distancia que los separe de los bordes del contenedor (a pesar que estos bordes no van a ser visibles).
Por eso podríamos aplicar un margen a cada uno de los elementos, o aplicar un espacio de "relleno" al contenedor. Este espacio de relleno se logra hacer con padding, y a diferencia de utilizar el margin, es un espacio que se ubica por dentro del componente y no por fuera. 
Lo podemos ver en este diagrama que aparece en la consola de programación del Chrome. 
Para eso le vamos a establecer la propiedad padding al elemento "main-cont" con cuatro valores. Se establece en forma de las agujas del reloj, empezando desde arriba, 0 30px 0 30px. Esto como vemos agranda el cuadrado naranja, entonces si queremos que el padding no modifique el tamaño que nosotros definimos, debemos utilizar la propiedad box-sizing. 
Por defecto esta propiedad esta establecida con el valor "content-box", y eso significa que al establecer una altura o ancho, este número no contempla el padding o relleno, entonces para conocer el tamaño total del elemento, deberíamos sumar esas dos cantidades. En vez de hacer esa cuenta, si queremos que el "relleno" actúe como tal y sea contemplado dentro del tamaño que fijamos, debemos establecer el valor de la propiedad "box-sizing" a border-box. De esta manera no sólo el padding será contemplado como parte del tamaño, sino también el tamaño que el borde pudiera tener. 

https://www.w3schools.com/cssref/css3_pr_box-sizing.asp

#9

En caso que la imagen cargue lentamente, o debido a algún problema no pueda cargar correctamente, todo el contenido que este por debajo de la imagen se moverá causando un efecto desagradable para el usuario. Por esta razón, lo recomendable es establecer un tamaño por defecto a la imagen, y de esta manera conservará su espacio aún a pesar que demore su carga o directamente no cargue. 
Para conseguir esto voy a establecer el max-height, el alto máximo de la imagen, a 170 px. 

#10

En este video vamos a crear tres contenedores, donde vamos a ubicar la información de la mesa, las acciones que puede hacer el usuario y debajo un cuadro con estrellas para que el usuario pueda calificar la atención del mozo. 

Vamos a utilizar tres técnicas de posicionamiento diferente. El primer div va a tener un alto fijo, el segundo va a adecuarse al tamaño de su contenido, y el tercero va a tener un tamaño absoluto y se va a posicionar en la parte inferior de su contenedor, el main-cont.
Para que sean visibles, vamos a otorgarles los colores rojo, verde y azul, respectivamente. 

#11

Vamos a establecer las características básicas del texto que se va a mostrar dentro de la sección de información de la mesa. Para eso vamos a crear un span.

Luego, en el CSS le aplicamos estilo al texto, lo centramos, establecemos el alto de línea igual al contenedor y asignamos una fuente y estilo bold. 

#12

Vamos a jugar con las posibilidades de transparencia en el color de fondo mediante la utilización de rgba, y transparencia en todo el elemento mediante "opacity".

#13 

Vamos a conocer cómo lograr bordes redondeados utilizando border-radius. Primero vamos a ver cómo establecer los bordes uno por uno, empezando por el superior izquierdo, en sentido de las agujas de reloj, y luego lo dejamos finalmente establecido en 20px para todos los bordes por igual.

#14

Utilizando lo aprendido, vamos a hacer un fondo con gradiente lineal, con dirección hacia la derecha y tres puntos de color.
Vamos a utilizar la propiedad "background" en vez de background color, ya que vamos a definir algo más complejo que simplemente un único color. Utilizamos la función "linear-gradient".
Dentro de los colores clave, vamos a utilizar colores con rgba y alfa definido.
Definimos también el color del texto, a un color marrón clarito.  

Página de ayuda: CSS Matic

#15

Vamos a utilizar la propiedad margin para aplicar un margen y conocer las diferencias con respecto a utilizar "padding". Mientras padding se ubica por dentro del elemento, el margin, siempre esta por fuera. Se puede aplicar un margen diferente a cada uno de los costados del elemento, utilizando cuatro valores diferentes separados por espacios. En este caso vamos a aplicar 5px arriba y 5 px abajo del elemento contenedor de la información de la mesa. También lo podríamos aplicar por separado, utilizando las propiedades margin-top y margin-bottom.

#16 

Vamos a agregar las imágenes correspondiente a las acciones que puede hacer el usuario.
Para eso vamos a crear tres divs contenedores, y dentro de estos divs vamos a ubicar una imagen y un texto que va a ayudar a indicar la acción, debajo de la imagen.
Para crear todos los elementos de una forma muy rápida vamos a utilizar un truco, una abreviatura de Emmet, que es un herramienta que permite aumentar la velocidad de codificación. 
Para generar los elementos vamos a tipear div.action*3>img+span y presionar la tecla tab. 
Luego de hacer eso, vamos a indicar las rutas relativas a cada una de las imágenes, los textos para la propiedad "alt" de cada imagen, y el texto que va debajo, indicando cada acción.
Por el momento ni veamos el resultado, ya que las imágenes se ven muy grandes porque al ser imágenes del tipo svg, esta sigla significa gráficos vectoriales escalables y a diferencia de otros formatos, no contiene un tamaño asignado, y son perfectamente escalables, esto quiere decir que se pueden agrandar o achicar sin perder resolución. Otra ventaja de este formato de imágenes es que son muy livianas y cargan muy rápidamente. 

Para poder conocer todas las acciones que se pueden realizar se puede visitar la página:
https://docs.emmet.io

#17 

En este video vamos a hacer que las tres acciones se ubiquen en una misma línea, una al lado de la otra. Para lograr eso vamos darle a cada acción 1/3 del espacio, eso equivale a decir que cada acción tiene un ancho igual a 33.3 porciento. Con esto solo no es suficiente, ya que los divs tienen por defecto el tipo de display "block" que hace que se ubiquen uno debajo del otro en vez de ubicarse al lado. Por eso vamos a establecer el display en "inline-block". Al ser "inline" permite que otros elementos se posicionen en la misma línea. Guardamos, y vemos el resultado. Aún no queda como esperamos. Puede ser difícil de entender a primera vista, pero los espacios que existen entre cada uno de los divs, hacen que haya una muy pequeña separación, y eso hace que a pesar de que hayamos divido el espacio perfectamente en 3 partes, con esta pequeña separación, los tres elementos no caben en la misma línea. Un truco para lograr que las tres acciones quepan perfectamente, es "juntar" los divs de apertura y cierre.
Esto puede resultar un poco desprolijo, entonces otro truco es establecer el font-size del contenedor a 0. Tampoco es muy bonito pero funciona. 

Guardamos y vemos el resultado. Han desaparecido los texto de los span, esto sucede por haber puesto el font-size en 0. Por eso vamos a establecer el font a 14 pixeles y la variable tipográfica Helvética. También centramos el texto con "text-align" igual a center. 

Por último, observamos que en el diseño existe una pequeña separación entre cada imagen de acción, entonces agregamos un padding de 10px y cambiamos el box-sizing a boder-box.

#18

Descargamos de recursos la imagen "estrella.svg". Después mediante el atajo span{PUNTUAR MOZO}+div.stars>img.star*5 agregamos el texto "puntuar mozo" y cinco imágenes de estrella que van a servir para otorgar la calificación al mozo que atiende al usuario del sistema.
Luego vamos a hacer uso de las potencialidades de la hoja de estilo en cascada y vamos a hacer referencia mediante un selector a todos los elementos img que esten dentro de un elemento que contenga la clase "stars", que a su vez este dentro de un elemento llamado "score-cont". Cabe decir que en este caso puede ser redundante este nivel de especificación, pero sirve para mostrar cómo funciona CSS. Ante dos selectores que apliquen una misma propiedad, tendrá prioridad el que mayor nivel de especificación tenga. Este es un dato a tener muy presente, ya que muchas veces vemos que la propiedad que queremos aplicar no es aplicada porque otro selector esta "matando" lo que nosotros establecemos. 
En el selector que acabos de crear vamos a hacer que las estrellas tengan como alto el 100% de su contenedor y "floten" hacia la derecha. Con esto logramos que se posicionen en el lado derecho del contenedor.

Guardamos y vemos el resultado.

Por el momento, vemos que todavía faltan muchos detalles, ya que les estrellas se ven una línea debajo de "puntuar mozo" y en orden inverso al que las pusimos, es decir, la primer estrella en el html será la que se vea última.

Vamos a seguir mejorando el diseño en la próxima clase. 

#19

Primero, vamos a lograr que el texto se centre verticalmente. Eso lo vamos a hacer utilizando una técnica que ya vimos, otorgar al alto de la línea el mismo valor del alto del contenedor.

Hacemos referencia al span que contiene el texto mediante el selector .score-cont span y ponemos el line-height en 50 px.

La fuente tipográfica tampoco es la adecuada, así que en el contenedor "score-cont" vamos a establecer una fuente de 12 px y de la familia tipográfica helvética. 

Después de las últimas modificaciones, las imágenes de las estrellas se ubican en una linea inferior al texto que dice "puntuar mozo". Para evitar eso tenemos diferentes formas de lograrlo, en este caso vamos a utilizar la posición absoluta. 

Vamos a crear un selector de la clase start que este dentro de score-cont, y primero ponemos la position en absolute, luego el top igual a 0, y como queremos que este pegado al borde derecho vamos a poner el right también en 0. 

Para lograr que las estrellas se achiquen un poco, en vez de determinar el tamaño de la imagen, vamos a reducir el contenedor agregandole un relleno, un padding de 13 y un el box-sizing establecido en border-box. Luego el alto total vamos a hacer que se ajuste al contenedor.

Falta un toque más para que el diseño sea el que esperamos, una línea por arriba de la sección de calificación. Eso lo vamos a lograr mediante la propiedad border-top, style, width, y color en el selector de "score-cont". El estilo le ponemos "solid", al grosor de la línea lo definimos en 2 px, y el color le ponemos rgb(62,46,34). 

Por último le sacamos el color de fondo, que utilizamos de referencia, tanto en el contenedor principal como en la sección de calificación, para observar mejor el progreso que hicimos hasta acá.

Por el momento vamos a dejar acá, y luego seguimos. 

#20

Al hacer click sobre alguna de las acciones, podría desplegarse un mensaje por sobre los botones de las acciones. Para eso vamos a utilizar una imagen nueva, que pueden descargar desde los recursos de la clase. Este archivo se llama "message.svg" y también es un gráfico vectorial. Lo vamos a copiar en la carpeta "img".

En el archivo index.html vamos a crear un div con la clase "message" y dentro un img donde vamos a ver la imagen que descargamos. Lo vamos a poner en la primera posición, dentro del contenedor "actions-cont". 

Una vez que creamos el contenedor y la imagen para el mensaje, vamos a sacar el color verde de referencia, que habiamos puesto en el fondo del contenedor de las acciones.

De esta manera, ya la maqueta html de la página se parece al diseño que se había definido en primer momento. Podemos ver que al cambiar el tamaño de pantalla, achicarlo o agrandarlo, se sigue viendo correctamente. Hacemos todas las pruebas necesarias y revisamos que el resultado sea el esperado. 

En los próximos videos vamos a aplicarle algunos estilos dinámicos que le van a dar calidad profesional a nuestro diseño. 

#21

En este video vamos a conocer una técnica que permite modificar componentes cuando pasamos el mouse por encima de ellos. 

En el archivo de estilos vamos a ver un nuevo concepto que nos va a ayudar con esta tarea. Vamos a generar algo llamado "pseudo-clase CSS". Esto se trata de una palabra clave que se pone después del nombre del selector y representa un estado especial. Por ejemplo, podemos decirle al componente "aplica este estilo sólo mientras el usuario este pasando el mouse por encima". Para hacer eso, la palabra clave es "hover". Existe otras pseudoclases, pero vamos a ver sólo esa por el momento. 
Vamos a verlo en funcionamiento. Creamos un selector que tome todas las "star" dentro de "stars". La particularidad es que vamos a agregar los dos puntos detrás de "star" y luego vamos a escribir la palabra "hover" (con h y v corta o uve).
Dentro vamos a especificar la propiedad border: 1px solid; grabamos y vemos el resultado.
Ahora al pasar el cursor por cada estrella se dibuja un pequeño borde a su alrededor.  

Bien, espero que les haya salido. En el próximo video vamos a hacer algo aún más interesante.

#22

En este video vamos a hacer que al pasar el mouse por encima de las estrellas, estas cambien de color. Para lograr ese efecto, lo primero que vamos a hacer es descargar la imagen que esta en los recursos que se llama "estrella_sel.svg" y la vamos a copiar sobre la carpeta "img".

Dentro del pseudo selector que creamos en el anterior video, vamos a indicarle que cambie la imagen de fondo al pasar el cursor. Para eso vamos a utilizar una función de CSS relativamente nueva que es "content". Luego utilizamos la función url y entre paréntesis escrimos la ruta relativa hasta encontrar la imagen "estrella_sel.svg". Este paso es clave, ya que si no ponemos la ruta correcta no se mostrará la imagen. 
Tenemos que recordar, que la ruta que vamos a poner es relativa a donde estamos, al archivo style.css que esta dentro de la carpeta CSS, por eso lo primero que debemos hacer es "salir un nivel" hacia afuera. Eso lo logramos con los "dos puntos". La url debe quedar así:
content: url('./../img/estrella_sel.svg');

Guardamos lo que hicimos, y probamos. Si al pasar el mouse por arriba de cada una de las estrellas pueden ver este efecto, donde la estrella cambia de color, ¡felicitaciones!. Si por algún motivo, no sucede esto, revisen haber copiado el archivo en la carpeta correcta y que la url tenga el valor exacto y correcto. 















 


