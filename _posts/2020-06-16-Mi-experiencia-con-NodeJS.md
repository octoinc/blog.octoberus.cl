---
layout: post
title:  "Mi experiencia con NodeJS en un proyecto de un gran retail"
day:  16 junio, 2020
categories: [Experencia personal,Programar]
description: La experiencia que he tenido trabajando en el área del backend ha sido por ya aproximadamente 3 años, en algunos lenguajes como ruby on rails, php nativo, php o con framework Laravel, al igual que el uso de bases de datos mysql y postgresql principalmente. Todos los lenguajes que he mencionado...
image: "https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/lenguaje-programacion.jpg"
alt-image: Programando

author: Matías Castro
job: Software Developer
image-author: https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/Team/Matias.jpg
alt-image-author: Foto Matías Castro
---

<div class="row post-text">
    <div class="col-md-2"></div>
    <div class="col-md-7">
    <br>

<h2>Experiencia </h2>

<p>La experiencia que he tenido trabajando en el área del <b>backend</b> ha sido por ya aproximadamente 3 años, en algunos lenguajes como ruby on rails, php nativo, php o con framework Laravel, al igual que el uso de bases de datos mysql y postgresql principalmente. Todos los lenguajes que he mencionado han sido utilizados en trabajos para la universidad como también un par de trabajos de freelance, donde tuve que desarrollar un sistema de gestión de turnos para los empaquetadores de supermercados y una aplicación de ventas online de productos de oficina ubicados en el barrio meiggs. Mi fuerte ha sido trabajar lo que es backend ya que lo que es diseño o programación de front siempre me ha costado.</p>

<p>Soy parte del equipo de desarrollo en <a href="https://octo.is/" target="_blank" rel="noopener">Octo Inc.</a>, hace 1 año y 2 meses aproximadamente, al principio inicié como practicante en donde tuve que aprender las metodologías de trabajo y los lenguajes que utilizan. Fue un reto para mí, ya que trabajar en una empresa y poder cumplir con las tareas que se me pedían y a la vez con la universidad no ha sido nada fácil.</p>

<h2>Experiencia Follow Regional</h2>

<p>Desde que empecé como practicante hasta el día de hoy, se me ha asignado al proyecto <b>Follow Regional para la empresa Cencosud</b>, el cual consiste en optimizar el actual proceso de cotización de productos a sus distintos proveedores mediante una <b>aplicación web desarrollada en Nodejs con ExpressJs en el back y AngularJs con redux en el front</b>. Esta aplicación permitirá que los usuarios de Cencosud puedan de mejor manera administrar productos para su posterior proceso de compra.</p>

<p>Al principio empecé haciendo algunas incidencias pequeñas como añadir datos masivos a la base de datos, implementación de triggers y procedimientos de almacenados en postgresql, arreglando filtros de búsqueda, implementación de Full Text Search, que es una función de postgresql para búsqueda de texto, hasta lo que actualmente hago, que es manipulación de templates con Node, y trabajos en segundo plano con Jobs.</p>

<p>Todo ha sido de menos a más, mientras más iba haciendo más iba aprendiendo, también he podido desarrollar mi capacidad para interactuar con los clientes, claro que al principio cuando empecé a ir a las reuniones con Cencosud, no hablaba y solo tomaba notas, pero ahora ya tengo más interacción y en tiempos de pandemia como lo estamos ahora, más hay reuniones y por ende, más interacción.</p>

<h2>Experiencia con NodeJs</h2>

<p>Como comentaba al principio, entré a esta empresa sin conocer lo que era <b>NodeJs</b> o <b>ExpressJs</b>, tuve que iniciar un curso en Udemy para poder tener alguna noción, para ello se me dio una semana para familiarizarme con este lenguaje antes de integrarme definitivamente, al principio no entendía nada y me entraba el pánico por no poder cumplir en la pega y con ello reprobar la práctica.</p>

<p>Con el tiempo logré comprender que no era algo del otro mundo, mientras iba haciendo las cosas que me pedían, empecé a adaptarme a como es node, aprendí sobre qué <b>node es especial para comunicación en tiempo real entre el cliente y servidor</b>, y que es más liviano para trabajar en este último (<i>gran ventaja!</i> ), a trabajar en tiempo real con funciones asíncronas y el uso de async/await, la cual consiste en que una función debe esperar a que termine para poder procesar el siguiente, pude aprender a trabajar con arreglos/objetos de mejor manera al complementar con el uso de <a href="https://lodash.com/docs/4.17.15" traget="_blank" rel="noopener"><b>lodash</b></a> (<i>con esto se expandió mi cabeza</i>) es una librería de JavaScript que se puede utilizar con node, te simplificará la vida, siempre se la recomiendo a todos. En cuanto a <b>Express</b> logre comprender cómo armar una infraestructura sencilla para poder manejar las peticiones y de esta forma poder comunicarse con el front de una forma más sencilla.</p>

<p>Iniciar un proyecto con módulos de Node y Express no es complicado, pero lo primero que hay que tomar en cuenta es el uso de npm, este es un gestor de paquetes que permite crear, compartir y reutilizar aplicaciones y módulos de node. Para instalar npm solo deben seguir las instrucciones de su documentación (<a href="https://www.npmjs.com/get-npm" target="_blank" rel="noopener">Get-npm</a>). Ya que luego de instalar express, es tan sólo con tener esta estructura en un nuevo archivo en su carpeta raíz: </p>

<pre>
<code>
const express = require('express');
const app = express();
  
app.get('/', function (req, res) {
res.end("Hola mundo");
});
  
app.listen(3000, function () {
    console.log('Escuchando en el puerto 3000!');
 });

</code>
</pre> 
<br>

<p>Ya pueden empezar a trabajar con rutas.</p>

<p>Una de las principales herramientas que recomiendo es el uso de <a href="https://nodemon.io/" target="_blank">Nodemon</a>, está herramienta monitorea cualquier cambio que se produzca al guardar cambios hechos en el archivo que estás trabajando y recarga de forma automática, para no estar cancelando y ejecutando el archivo index cada vez que queramos probar algún cambio. Esto es súper útil, ahorra mucho tiempo y se puede saber el momento exacto del posible error que se puede cometer.</p>

<p>Otra librerías que recomendaría al programar en Node es el uso de lodash como mencione anteriormente ya que, simplifica mucho el uso de arrays y el manejo de objetos. En su documentación (Lodash) hay una amplia lista de métodos para usar, como por ejemplo:
</p>

<pre>
<code>
_.indexOf([1, 2, 1, 2], 2);
// => 1

_.join(['a', 'b', 'c'], '~');
// => 'a~b~c'


_.split('a-b-c', '-', 2);
// => ['a', 'b']

_.upperCase('--foo-bar');
// => 'FOO BAR'
</code>
</pre>
<br>

<p>Para el manejo de fechas es esencial saber que ocupar, ya que a veces puede ser un dolor de cabeza como me ha pasado a mí al momento de trabajar con fechas, para ello recomiendo el uso de moment que personalmente me ha facilitado mucho al trabajar con el odioso objeto Date. Algunos ejemplos básicos:</p>

<pre>
<code>
// se crea un objeto moment
const now = moment();

// se crea una fecha año, mes, dia
const nowDate = moment([2018, 6, 15]);
</code>
</pre>
<br>

<p>Al crear la constante now uno ya puede trabajar por ejemplo sacando el dia (now.day()) o el mes (now.month()).</p>

<p>Esto les simplificará bastante la vida al momento de trabajar con fechas</p>

<h2>Test</h2>

<p>Los test son una forma de poder tener una aplicación de mejor calidad y de desarrollo. Hay distintos tipos de test, por ejemplo, los <b>Tests E2E</b> que simulan el comportamiento de un usuario real y que prueba todo lo que su usuario debiera ser, están los <b>test de integración</b> donde se integran dos o más partes del código y están los <b>test unitarios</b> que testean solo una parte del código.</p>

<p>Una de mis tareas antes de poder identificarme como programador back fue realizar test a la aplicación que estamos desarrollando, utilizando la herramienta <b>Cypress</b>, que prácticamente es una aplicación todo en uno para realizar test. Esta herramienta se ejecuta mediante un navegador sin interfaz gráfica que viene por defecto al instalar Cypress. Al ver la sintaxis de como preparan los Tests, pensé que no era muy complicado, y efectivamente no lo era. El problema fue que pueden ser muy extensos al programarlos porque en un proyecto como en el que estoy puede llegar a tomar mucho tiempo prepararlos, así como también ejecutarlos.</p>

<p>Finalmente, toda esta experiencia que he vivido con nuevas metodologías y nuevos lenguajes es un trabajo que toma tiempo y dedicación, llevo 1 año y 2 meses y aún sigo aprendiendo. Si hay nuevas tecnologías que se deben aprender para realizar un trabajo de la universidad, o para empezar a trabajar, está bien sentirse abrumado o como también habrán pensamientos que te digan que no podrás, pero <b>solo se necesita esfuerzo y dedicación que con esto se puede llegar lejos</b>.</p>

<div class="row container-written">
<div class="col-md-2">
</div>
<div class="col-md-3">
    <img style="border-radius:50%;" src="{{page.image-author}}" width="110%" height="auto" alt="{{page.alt-image-author}}">
</div>
<div class="col-md-7 written">
    <p>Escrito por:</p>
    <p><b style="font-size:20px">{{page.author}}</b>
    <br>{{page.job}}</p>
</div>
</div>

 <div>{% include calltoaction.html %}</div>
{% include footer.html %}

