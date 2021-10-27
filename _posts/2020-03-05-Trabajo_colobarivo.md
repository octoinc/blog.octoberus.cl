---
layout: post
title:  "Trabajo colaborativo entre sensores y vehículos no tripulados"
day:   05 Mayo, 2020
categories: [Digitalización,Inspecciones]
description: A fines del año 2016 comenzamos con la idea de integrar la información de vehículos no tripulados como drones y rovers con aplicaciones de chat. La razón de por qué emprendimos esta misión de trabajo, fue para dejar disponible y lo más rápido posible, imágenes capturadas por drones...
image: "https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/loomo.jpeg"

author: Rodrigo Morgado
job: CTO
image-author: https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/Team/Rodrigo.jpg
alt-image-author: Foto Rodrigo Morgado
---

<!-- <meta property="og:image" content="http://www.miweb.com/imagen.jpg"/>
<link rel="image_src" href="http://www.miweb.com/imagen.jpg" /> -->

<!-- <div class="borde2">
<br> -->

<div class="row post-text">
    <div class="col-md-2"></div>
    <div class="col-md-7">
    <br>

<p>A fines del año 2016 comenzamos con la idea de <b>integrar la información de vehículos no tripulados como drones y rovers con aplicaciones de chat</b>. La razón de por qué emprendimos esta misión de trabajo, fue para dejar disponible y lo más rápido posible, imágenes capturadas por drones en un grupo de chat que compartían especialistas de ingeniería de una importante multinacional. Muchos de los activos que cumplen funciones en plantas productivas en Chile provienen del extranjero y a veces, es necesario, compartir ideas entre colegas nacionales con los respectivos vendors.</p>

<p>Esta aplicación nos llevó a desarrollar más funcionalidades en el trabajo colaborativo entre sensores y vehículos no tripulados. Una de las aplicaciones inmediatas abordar que un cliente visualizó para resolver un actual dolor en su compañía, eran los <b>robos en las instalaciones</b> que comprenden grandes extensiones de terreno <i>(sobre 500 hectáreas)</i>. Encontramos varios problemas para utilizar tecnologías tradicionales, entre los que se encuentran:</p>

<ol>
<li> <b>Alto costo de inversión en infraestructura.</b> Colocar cámaras y sus respectivas canaletas para el cableado hace que el CAPEX sea excesivo.</li>
<li> <b>Áreas sin acceso a Internet.</b> Si se opta por instalación de sensores complementarios, éstos deben construir su propia red o hacer converger el flujo de datos a un nodo con acceso.</li>
<li> <b>Baja resiliencia en el sistema.</b> Por lo general una red de local de seguridad, que usa cables de datos, no está construida para tolerar fallas de comunicación.</li>
<li> <b>Daños en el equipamiento por corrosión.</b> No era posible instalar cualquier hardware, el lugar físico donde se realizaría la instalación estaba expuesto a corrosión por aire salino y altas temperaturas.</li>
</ol>
<br>

<img style="float:left; margin:10px 20px 10px 0;" src="https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/panel-solar.jpeg" width="40%" height="auto" alt="panel solar en el desierto">
<p>La empresa decidió innovar y acceder a implementar una propuesta que incluía el uso de nodos con comunicación wireless y alimentación a través de baterías más paneles solares. Al construir nodos de bajo costo, nos permitió generar redundancia en el sistema y con ellos, aumentar su resiliencia. El problema que  encontramos fue que nuestro diseño no era óptimo. Dentro de un espacio de 1.000 hectáreas, no es necesario instalar sensores en el 100% del área, solo es esencial instalar en aquellas zonas que la empresa ya había identificado como críticas (historial de los robos). Al crear una <a href="https://soporte.syscom.mx/es/articles/1923724-que-es-una-red-wifi-mesh" target="_blank" rel="noopener">red mesh</a> en un 90% distribuida, se calcula el porcentaje de manera similar a la que un mensaje ping del <a href="https://medium.com/@adr.rod87/qu%C3%A9-son-los-protocolos-gossip-6b92fe449ec0" target="_blank" rel="noopener">protocolo Gossip</a> golpea un peer o no. Si tenemos 10 nodos, y el nodo A envía un mensaje, éste es transmitido por el 90% de los nodos restantes. Yep!, genera problemas en el ancho de banda, pero nada que no se pueda optimizar. Existe un parámetro que llamado TTL, "Time To Live" (que ayuda a controlar el nivel de propagación de los mensajes) se deben agregar nodos intermedios para poder conectar estas áreas, ya que los datos no pueden salir a la nube por sí solos. Esto nos motivó a investigar lo que estaban haciendo varios académicos que usan vehículos no tripulados cómo drones para mejorar la red.</p>

<h3><b>Redes Colaborativas Entre Sensores y Vehículos No Tripulados</b></h3>

<p>Para quienes no hayan aún revisado la investigación realizada por <a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6308614/" target="_blank" rel="noopener">Popescu, Dragana, Stoican, Ichim y Stamatescu, 2018</a>. El paper busca ilustrar la forma óptima de configuración para que una red de nodos pueda extenderse en área y que su resiliencia aumente gracias a la interacción con vehículos no tripulados.</p>

<p>La integración de redes compuestas por sensores y vehículos no tripulados pueden generar los siguientes beneficios según los autores.</p>

<ol>
<li><b>Recolección y examinación en terreno de datos.</b> Los vehículos no tripulados pueden recolectar la información de los sensores y subirnos inmediatamente a la red como pueden ser transportados a la base para ser procesados.</li>
<li><b>Eficiencia en el trabajo de clusters.</b> Como explicaba anteriormente, existen lugares que requieren sensores y otros que no. Los vehículos no tripulados permiten crear clusters de sensores que optimizan los recursos en el área a cubrir. No es necesario utilizar nodos "helpers" solo para reenviar la data.</li>
<li><b>Los vehículos no tripulados como drones, permiten hacer levantamiento 3D del terreno.</b> Estos mapas digitales sirven mucho para generar un plan de instalación de los sensores que optimice la puesta en terreno.</li>
</ol><br>

<p>Si bien, no es trivial realizar una configuración a nivel de hardware y software para lograr el objetivo, los autores dan énfasis en sortear una serie de problemas secuenciales primero:</p>

<ul>
<li>Si la posición de los sensores es desconocida, es necesario primero generar vuelos de levantamiento de datos para identificar los sensores y su posición geográfica con el objetivo de llevar un registro e inventario de los nodos repartidos en el terreno. Esto se puede hacer desde una mirada fotogramétrica donde se hace un levantamiento del terreno y se puede estimar con mayor precisión la ubicación de los nodos.</li>
<li>Se requiere reunir todas las restricciones en relación a obstáculos durante el vuelo y problemas de comunicación que permitan crear una lista de las posibles trayectorias de los drones.</li>
<li>Finalmente, usando el modo auto-pilot se puede obtener feedback de la misión para analizar posteriormente las rutas realizadas.</li>
</ul><br>

<img style="float:right; margin:8px 0px 0px 25px;" src="https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/drone-bumblebot.jpeg" width="40%" height="auto" alt="Drone en planta industrial">
<p>En el equipo <a href="https://www.octo.is/" taget="_blank" rel="noopener">Octo Inc.</a>, durante nuestro trabajo en la integración de Bumble Bot (aplicación que se preocupa del compliance a la hora de operar drones) nos percatamos que tener puntos en tierra (como los nodos) correctamente geolocalizados y conociendo con exactitud su precisión, nos permitía corregir las rutas de los drones. Con esto, durante levantamientos aerofotogramétricos, nos permitía obtener mejores resultados.</p><br>


<h3><b>¿Cómo seguimos nuestra misión de integración?</b></h3>

<p>Una vez terminado el proyecto piloto donde colocamos cerca de 50 nodos de seguridad en el Desierto de Atacama utilizando principalmente el protocolo LoRa (para larga distancia y de bajo consumo), comenzamos con la integración en la <a href="https://www.octopull.cl/" taget="_blank" rel="noopener">plataforma Octopull</a> donde se comunicaban señales desde estos sensores a drones DJI (Matrice 600, Mavic Pro y Enterprise. Es el mismo SDK por lo que el dolor de cabeza es uno solo). <b>Con esta integración, buscamos generar una misión de vuelo a un drone y una misión de inspección al rover cuando se active una alerta</b> (ej. movimiento en cerco infrarrojo perimetral). El desafío en estas pruebas fue ejecutar la misión desde el "home" hasta la ubicación del sensor de la manera más óptima posible. No solo el GPS del vehículo no tripulado es necesario, se requiere complementar con otros sensores (como de proximidad) para poder guiar al objeto a que ejecute la ruta sin percances.</p>

<img style="float:right; margin:8px 0px 0px 25px;" src="https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/loomo-octo.jpeg" width="45%" height="auto" alt="Pruebas con loomo">
<p>En una de las pruebas que llevamos a cabo, utilizamos un rover Segway Loomo, si bien, no viene con un GPS de fábrica, posee sensores que permiten una ejecución de ruta bastante decente, pero nos encontramos con problemas de precisión cuando queríamos llegar desde el punto A al B con un error menor de 10 cms. Si la distancia entre A a B era menor de 100 metros, el resultado se encontraba en ese rango de error, pero si aumentábamos la distancia, el error se duplicaba cada 20 metros que agregábamos a la ruta. Algo insostenible para llevar el piloto a producción.</p>

<p>Para poder cumplir con la misión de llegar al Punto B desde A con la mayor precisión posible en distancias sobre 1Km, tuvimos que incorporar hardware y software adicional al Loomo. Esto lo hicimos principalmente para corregir la posición en el tiempo t=t1. Nos dimos cuenta que por consola, el Segway Loomo nos declaraba una posición p=p1 en t=t1, la cual distaba del dato real que capturaba un sensor (GPS y proximidad). Al hacer esta comparación entre la posición reportada por el rover y aquella, reportada por los sensores, nos permitía actualizar las instrucciones del vehículo no tripulado, corrigiendo la ruta y reduciendo el error acumulado en todas las posiciones donde capturábamos datos. Esto nos permitió ejecutar misiones de inspección y vigilancia de mejor manera.</p>

<p>Hoy en día, estamos aprendiendo del trabajo realizado por Popescu, Dragana, Stoican, Ichim y Stamatescu, 2018 no solo para poder obtener los datos desde los sensores sino utilizar estos mismos nodos para corregir las posiciones de los vehículos no tripulados. Cuando la posición del nodo A es conocida nos sirve como punto en tierra para que los vehículos no tripulados envíen señales y corrijan su posición. Algo muy parecido a lo que hacen los satélites y bueno, todo lo que hoy en día vuela.</p>

<p>Si no conocen el Loomo, acá un video que explica sus funcionalidades.</P>


<iframe width="100%" height="340" src="https://www.youtube.com/embed/t5H4JENYps4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

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


