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

<!-- Table of Contents -->
# :notebook_with_decorative_cover: TABLA DE CONTENIDOS

- [Explicación del ejercicio](#explication)
  * [¿Como funciona?](#ejemplo)
  * [Preparando mi Slider](#preparando)
  * [Animation-delay](#delay)
  * [Resultado final](#resultado)
- [Estilos adicionales](#adicionales)



  <!-- ABOUT THE PROJECT -->
<div align="center" id="explication">
  <img src="https://user-images.githubusercontent.com/74038190/216122041-518ac897-8d92-4c6b-9b3f-ca01dcaf38ee.png" alt="Fire" width="120" />
</div>

## :space_invader: EXPLICACIÓN DEL EJERCICIO

👽Lo primero que debemos entender en este ejercicio es que la idea principal es crear una animación en la que cada uno de los elementos del slider se desplace de derecha a izquierda.
<div align="center">
  <img src="/assets/img/readme/ejemplo1.gif"/>
</div>

<br>
<br>
Para realizar el ejercicio creé una lista desordenada que contiene 9 items, los posicione de manera horizontal, agregando un par de estilos básicos a mi elemento ul así border: 1px red solid; además display: flex; list-style: none; y por último le voy a dar un ancho predeterminado a mi slider width; 1350px; 
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
<div align="center" id="ejemplo">
  <img src="/assets/img/readme/ejemplo2.gif"/>
</div>

<br>
<br>
No era el resultado que esperábamos ¿cierto? y es que no tuvimos en cuenta varios factores.<br>
El primero es que se generan espacios en blanco en nuestro slider mientras inicia y finaliza la animación, en vez de que se genere un efecto 360 donde después del último se muestra nuevamente el primero y así sucesivamente. Pero además, la animación como tal no parece ir fluida por que entran en juegos 3 factores básicos en un slider que no tuvimos en cuenta:<br>
<ul>
  <li>Tiempo de duración de la animación. </li>
  <li>Cantidad de objetos que van a recorrer en la animación durante ese tiempo.</li>
  <li>El ancho de cada objeto para calcular la distancia del recorrido.
</li>
</ul><br>
Por lo que aunque estamos utilizando contenido estático, el slider debe ser dinámico en cierto sentido y "esta es la razón por la que siempre todos utilizamos javaScript para crear un slider en vez de usar CSS".
<br><br>
Pero…. estamos trabajando con el poder de CSS3 moderno! aún tenemos un as bajo la manga, aquí es donde empieza la magia.<br>
<p id="preparando">Hagamos lo siguiente, vamos a separar los elementos de mi slider posicionandolos de manera absoluta cada uno</p><br>

```css
li img {
    position: absolute;
    width: 200px;
}
```

esto hará que mis imágenes se monten una encima de la otra, por ahora, pero lo importante es que las separamos posicionando cada una de manera obsoluta para poder aplicarles luego la magia. Para ubicarlas de manera horizontal una al lado de la otra nuevamente vamos a jugar con el ancho de cada imagen y el del slider, restableciendo 2 variables   --width y --height

```css
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  --width:150px;
  --height:220px;
}

```

y esas variables las vamos a utilizar para otorgarle tamañno a mi  ```<li></li> ```  y ahora si vamos a cambiar tambien el tamaño de cada imagen que anteriormente le habia puesto 200px, lo vamos a cambiar a 100% para que se acomode al tamaño que le hemos dado a su contenedor  ```<li></li> ```


```css
li{
    position: relative;
    width: var(--width) ;
    height: var(--height);
    animation: AutoRun  infinite linear 9s;
  }& img {
    position: absolute;
    width: 100%;
}
```

Y walaaaaaaa que conseguimos con esto, mantener los elementos del slider en formato horizontal pero aun más importante cada uno de ellos ahora está posicionado absolutamente ocupando el total de nuestro slider y vamos a poder manipular cada uno de ellos de forma más sencilla, ahora es cuando la magia ocuerre...
<div align="center">
  <img src="/assets/img/readme/3.png"/>
</div>
<br><br>
En esta punto podemos ajustar el alto de nuestro slider para evitar el espacio vacío o agregar una linea más de código para hacer que el slider se expanda y se ajuste a la suma del ancho de todas las imagenes y de esta manera se no quede un espacio vacío en nuestro slider, te explico esto por que es importante: si te fijas e inspeccionamos mi ejercicio, las imágenes no tienen exactamente la medida que les dimos que es 150px * 220px 
<div align="center">
  <img src="/assets/img/readme/4.png"/>
</div>
<br><br>

La razon es por que el tamaño de la lista o de mi slider no es lo suficiente para contener los elementos, por lo que se acomodan para poder ocupar el tamaño del slide podemos agregar una linea de código para solucionar esto y hacer que el slider empiece a ser dinámico,
agregando una nueva variable -quantity, la cual vamos a utilizar para contar cuantos elementos va a contener el slider, en mi caso voy a mostrar 9 imágenes.


```css
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  --width:200px;
  --height:300px;
  --quantity: 9;
}

```
Ahora simplemente calculamos la suma del ancho de todas las imágenes y le damos ese valor a nuestro slider de forma dinamica usando la propiedad  ```min-width ```  así

```css
ul{
  display: flex;
  list-style: none;
  width: 1350px;
  min-width: calc(var(--width) * var(--quantity));
  height: var(--height);
  border: 1px red solid;
  overflow: hidden;
}

```

Esto se entiende fácilmente, si el contenido de mi slider es menor de 1350px, pues acomoda el contenido a ese ancho, pero si el contenido es mayor que el slider, acomoda el slider calculando el ancho del total de los elementos. (ancho * cantidad), sencillo.<br><br>
AHORA SIIIII podemos hacer magia, ya tenemos nuestro slider preparado y si te fijas más hemos hecho par de lineas de código solamente. y el slider lo vamos a crear con solo 1 linea más de código, para entender como funciona he preparado estas 2 imágenes <br><br>
Utilizamos la propiedad  ```animation-delay```
<div align="center" id="delay">
  <img src="/assets/img/readme/animationdelay.png"/>
</div>

Lo que va a hacer esta propiedad es darle un tiempo de espera a cada elemento del slider de forma individual y de esta manera hacemos que se muevan de forma independiente en la animación así.
<div align="center">
  <img src="/assets/img/readme/mesa1.png" width="45%"/>
  <img src="/assets/img/readme/mesa2.png" width="45%"/>
</div>
En la gráfica, cada elemento tiene un tiempo de delay independiente, esto hace que cada uno se desplace 1 segundo despues que el otro pero una vez finalice la animación, nuevamente el elemento 1 se va a mostrar en el slider evitando los espacios en blanco y generando el efecto 360 que queríamos al principio, pero esto lo vamos a hacer de manera dinámica sólo usando el poder de CSS3 moderno.<br><br>

Para lograrlo vamos a darle un index o id a cada elemento de nuestro slider desde el html, utilizando la etiqueta  ```<style></style> ``` así:

```html
    <li style="--index: 1;"><img src="img/1.jpg"></li>
    <li style="--index: 2;"><img src="img/2.jpg"></li>
    <li style="--index: 3;"><img src="img/3.jpg"></li>
    <li style="--index: 4;"><img src="img/4.jpg"></li>
    <li style="--index: 5;"><img src="img/5.jpg"></li>
    <li style="--index: 6;"><img src="img/6.jpg"></li>
    <li style="--index: 7;"><img src="img/7.jpg"></li>
    <li style="--index: 8;"><img src="img/8.jpg"></li>
    <li style="--index: 9;"><img src="img/9.jpg"></li>

```

Ahora cada elemento tiene un valor de index intependiente que podemos utilizar para calcular de manera dinámica la animación que vamos a crear, pero antes debemos agregar un   ```left:100%``` a cada uno de los elementos del slider, esto podemos hacerlo por que recordemos que nuestros elementos son absolutos ahora y de esta manera los movemos hacia la derecha y hacemos que salgan de nuestro slider para que podamos ahora con la animación empezar a moverlos uno por uno hacia la derecha. y por último ahora si agregamos la animación de esta manera y ya les explico el código

```css
  li{
    width: var(--width) ;
    height: var(--height);
    position: absolute;
    left: 100%;
    animation: AutoRun  infinite linear var(--time);
    animation-delay: calc(var(--time) / var(--quantity) * (var(--index) - 1));
  }

```
Como lo puedes haber notado he agregado una nueva variable, que va a ser el tiempo de ejecución de mi animacion, en mi caso son 9s entonces la formula calcula el: tiempo/cantidad osea que sería 1 segundo para cada elemento 9/9=1 y esto lo multiplicamos por el index del elemento - 1, es decir si es el index 1 =>  ``` 1-1= 0 ```    y al multiplicar   ```1 * 0 = 0```  nos da el delay dinamico para el elemento 1, luego calcula el siguiente index 2 =>   ```2-1= 1 ```  y al multiplicar  ```1 * 1= 1```  entonces el delay dinamico para el elemento 2 es 1 y así sucesivamente y el resultado es este:
<div align="center">
  <img src="/assets/img/readme/ejemplo3.gif"/>
</div>

Walaaaaaaa conseguimos el efecto 360 que queriamos!!! ahora tenemos un slider, aunque al inicio seguimos teniendo un espacio en blanco, eso lo podemos corregir agregandole una última parámetro a la formula del delay, con esto lo que vamos a conseguir es adelantarnos al tiempo y que nuestro slider inicie como si ya hubiera pasado la primera ronda de animación! así, restamos al final el tiempo de animación


```css
   li{
    width: var(--width) ;
    height: var(--height);
    position: absolute;
    left: 100%;
    animation: AutoRun  infinite linear var(--time);
    animation-delay: calc(var(--time) / var(--quantity) * (var(--index) - 1) - var(--time));
  }

```
Por fín ya tenemos el ejercicio finalizado si recargamos la página nunca vemos espacios en blaco!!!.
<div align="center" id="resultado">
  <img src="/assets/img/readme/ejemplo4.gif"/>
</div>
<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- Ajustes Adicionales -->
### :camera: ESTILOS ADICIONALES 
 <p id="adicionales">Ya sabes como crear tu propio slider usando solo CSS3 pero en el demo que he diseñado para este ejercicio, le agregué un par de efectos adicionales y también quiero enseñartelos</p>
 1.DETENER LA ANIMACIÓN:<br>
 simplemente un animation-play-state: paused !important;<br><br>

 2.TRANSPARENCIA EN EL SLIDER<br>
Agregamos una mascara con un degradado de 3 puntos, al inicio transparente, en el medio negro y al finalizar transparente nuevamente, así 

```css
  mask-image: linear-gradient(to right, transparent, rgba(0, 0, 0, 0.8), transparent);
```


