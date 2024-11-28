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
Para realizar el ejercicio cree una lista desordenada, que contiene 9 items los posicione de manera horizontal, para ello agregaré un par de estilos básicos a mi elemento <ul> así: border: 1px red solid; además display: flex; list-style: none; y por último le voy a dar un ancho predeterminado a mi slider width; 1350px; 
<div align="center">
  <img src="/assets/img/readme/2.png"/>
</div>
Básico, le di un tamaño de momento a las imagenes de mi lista, solo por ahora ya mas adelante se daran cuenta que lo cambiamos pero por ahora les doy un width; 200px; y señalo el border en la capatura para que tengamos en cuenta el ancho maximo que le hemos dado anteriormente al slider y obviamente tenemos que agregar un overflow: hidden; para apreciarlo mejor y lo que vamos a hacer. 

<div align="center">
  <img src="/assets/img/readme/2.png"/>
</div>
<br>
<br>
Ahora analicemos esto, lo fácil podriamos pensar, si mi slider tiene un ancho total de 1350px, voy a desplazar todos mis imganeges en forma negativa desde -1350px hasta 1350px así provocamos que todos los elementos se muestren en el desplazamiento y agregamos el atributo infinite a nuestra animación para que se repita en bucle y lo logramos!, pues… ¿si funcionará? veamos el resultado.

<div align="center">
  <img src="/assets/img/readme/ejemplo2.gif"/>
</div>
<p align="right">(<a href="#readme-top">back to top</a>)</p>

