<a id="readme-top"></a>
<!-- PROJECT LOGO -->
<div align="center">
  <a href="https://www.linkedin.com/in/creativesth/">
    <img src="assets/img/logo.svg" alt="Logo" width="280">
  </a>

  <h3 align="center">Vanilla CSS3 y HTML | Incredible Pure Css Slider</h3>

  <p align="center">
    ESPECTACULAR ejercicio CSS3 Slider, Sin una sola línea de JavaScript, hemos creado una experiencia visual impresionante utilizando solo CSS moderno con variables y la propiedad cal() para ejecutar algunas funciones y hacerlo dinámico.
    <br />
    <a href="https://creativesth.github.io/Incredible-Pure-Css-Slider-/"><strong>Demo »</strong></a>
    <br />
  </p>
</div>

  <!-- ABOUT THE PROJECT -->
<div align="center">
  <img src="https://user-images.githubusercontent.com/74038190/216122041-518ac897-8d92-4c6b-9b3f-ca01dcaf38ee.png" alt="Fire" width="120" />
</div>

## EXPLICACIÓN DEL EJERCICIO

👽Lo primero que debemos entender en este ejercicio es que la idea principal es crear una animación en la que cada uno de los elementos del slider se desplace de derecha a izquierda.
<div align="center">
  <img src="/assets/img/readme/ejemplo1.gif"/>
</div>

<br>
<br>
Para realizar el ejercicio cree una lista desordenada que contiene 9 items, los posicione de manera horizontal, agregando un par de estilos básicos a mi elemento ul así border: 1px red solid; además display: flex; list-style: none; y por último le voy a dar un ancho predeterminado a mi slider width; 1350px; 
<div align="center">
  <img src="/assets/img/readme/1.png"/>
</div>

<br><br>
También le di un tamaño de "momento" a las imagenes de mi lista, solo por ahora, ya mas adelante se daran cuenta que lo cambiamos, pero por ahora les doy un width; 200px; y señalo el border en la capatura para que tengamos en cuenta el ancho maximo que le hemos dado anteriormente al slider y obviamente tenemos que agregar un overflow: hidden; para apreciarlo mejor y lo que vamos a hacer. 

<div align="center">
  <img src="/assets/img/readme/2.png"/>
</div>

<br>
<br>
Ahora analicemos esto, lo fácil podriamos pensar, si mi slider tiene un ancho total de 1350px, voy a desplazar todos mis imganeges en forma negativa desde -1350px hasta 1350px así provocamos que todos los elementos se muestren en el desplazamiento y agregamos el atributo infinite a nuestra animación para que se repita en bucle y lo logramos!, pues… ¿si funcionará? veamos el resultado.
<div align="center">
  <img src="/assets/img/readme/ejemplo2.gif"/>
</div>

<br>
<br>
No era el resultado que esperábamos ¿cierto? y es que no tuvimos en cuenta varios factores.<br>
El primero es que se generan espacios en blanco en nuestro slider mientras inicia y finaliza la animación, en vez de que se genere un efecto 360 donde después del último se muestra nuevamente el primero y así sucesivamente.Pero además;<br>
La animación como tal no parece ir fluida por que entran en juegos 3 factores básicos en un slider que no tuvimos en cuenta:
<ul>
  <li>Tiempo de duración de la animación. </li>
  <li>Cantidad de objetos que van a recorrer en la animación durante ese tiempo.</li>
  <li>El ancho de cada objeto para calcular la distancia del recorrido.
</li>
</ul><br>
Por lo que aunque estamos utilizando contenido estático, el slider debe ser dinámico en cierto sentido y "esta es la razón por la que siempre todos utilizamos javaScript para crear un slider en vez de usar CSS".<br>
pero…. estamos trabajando con el poder de CSS3 moderno!, aún tenemos un as bajo la manga, aquí es donde empieza la magia.




 
<p align="right">(<a href="#readme-top">back to top</a>)</p>

