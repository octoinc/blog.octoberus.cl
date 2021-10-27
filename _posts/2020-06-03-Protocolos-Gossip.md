---
layout: post
title:  "Protocolos Gossip"
day:   03 junio, 2020
categories: 
description: Gossip es un protocolo de comunicación de datos utilizado en sistemas distribuidos, funciona de manera parecida a la expansión del contagio de una enfermedad o de un rumor, de persona a persona, ya que básicamente trabaja esparciendo un mensaje de nodo en nodo...
image: "https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/gossip.png"

author: Hector Orellana
job: Software Developer
image-author: https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/Team/Hector.jpg
alt-image-author: Foto Hector Orellana
---

<div class="row post-text">
<div class="col-md-2"></div>
<div class="col-md-7">
<br>

<p>Gossip es un <b>protocolo de comunicación</b> de datos utilizado en <b>sistemas distribuidos</b>, funciona de manera parecida a la expansión del contagio de una enfermedad o de un rumor, de persona a persona, ya que básicamente trabaja esparciendo un mensaje de nodo en nodo.</p>

<p>Algunas de las fortalezas de los protocolos gossip son:<p>

<ul>
	<li><b>Escalables</b> en relación al trabajo que toma esparcir un mensaje por toda la red, aún cuando la cantidad de nodos instalados crezca.</li>
	<li>Ningún nodo debería tener una función especial en la red, por lo que es <b>fácil reemplazarlos</b> si fuese necesario. De igual manera si se agrega o quita un nodo a la red esta no debería sufrir problemas.</li>
</ul><br>

<p>Las redes que utilizan protocolos gossip son resistentes a los fallos de sus nodos y estos mismos pueden autónomamente dirigir sus mensajes a sus pares vivos, obviando los nodos que no estén respondiendo a los mensajes que les llegan. Por otro lado los protocolos gossip no necesariamente se encargan de manejar mensajes que llegan corruptos o incompletos, lo que se conoce como el <a href="https://people.eecs.berkeley.edu/~luca/cs174/byzantine.pdf" target="_blank" rel="noopener">problema de los generales bizantinos</a>.</p>


<h2 style="font-weight: 600">Cómo funciona</h2>
<p>La red gossip está compuesta por <b>“N nodos”</b>, los cuales periódicamente se comunican entre sí. Cada nodo no necesariamente conoce al resto de los nodos de la red, por lo general solo saben de los más próximos. Estos deben ser capaces de encontrar sus pares.</p>

<p>Cada cierto tiempo un nodo elige al azar <b>“M nodos”</b> con el fin de enviar su mensaje(dato recogido), este proceso se repite en cada nodo llegando a la mayor cantidad de nodos disponibles en la red, hasta que idealmente todos los nodos tengan la información. Debido a la manera que difunden la información se dice que los protocolos gossip funcionan de manera parecida a la de una epidemia, considerando que cada mensaje es como la <i>enfermedad</i> y los nodos que reciben el mensaje los <i>contagiados</i>.</p>

<p>Además, los mensajes son enviados por cada nodo mientras se cumpla cierto <b>criterio</b>, por ejemplo un nodo puede enviar cierto mensaje durante 30 minutos o también puede existir un límite de veces que un nodo enviará un mensaje. Cuando se cumple este criterio el nodo deja de repetir el mensaje (se considera sano de la enfermedad).</p>

<p>Para asegurar un correcto funcionamiento de la red, es decir que los mensajes se esparzan correctamente por esta, se debe cumplir los siguiente:</p>

<ul>
	<li>Se debe <b>seleccionar aleatoriamente a qué nodos se enviará cada mensaje</b> (nodos pares), esto con el objetivo de evitar que el mismo nodo sea siempre el que reciba el flujo de los datos. La idea es que la carga se balancee por todos los pares disponibles.</li>
	<li>Los <b>nodos no necesitan conocer todo el estado de la red</b>, solo basta con sus pares de nodos más cercanos.</li>
	<li>Cada mensaje tiene un <b>tamaño límite</b> conocido por los nodos.</li>
</ul><br>

<p>El tiempo que toma que un mensaje llegue al 100% de los nodos depende de los siguientes parámetros:</p>

<ol>
	<li><b>Intervalo de tiempo</b> entre que se envía cada mensaje.</li>
	<li>El <b>total de nodos</b> en la red.</li>
	<li>El <b>porcentaje de mensajes que se pierden</b> en cada comunicación.</li>
	<li>Cuantos nodos presentan problemas.</li>
	<li>A <b>cuántos nodos se le enviará el mensaje</b> en cada intervalo.</li>
</ol><br>

<p>El siguiente gráfico muestra cómo el mensaje llega a más nodos a medida que pasa el tiempo, con 30 nodos en la red, se envía el mensaje a <b>3 pares cada 5 segundos</b>, asumiendo que no hay nodos con fallas y que no se están perdiendo mensajes.<p>

<p style="text-align:center;"><img src="https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/protocol-gossip.png" width="100%" height="auto" center alt="Simulador de convergencia del Protocolo Gossip"></p>
<p class="tittle">Fuente: <a href="https://www.serf.io/docs/internals/simulator.html" target="_blank" rel="noopener">https://www.serf.io/docs/internals/simulator.htm</a></p>

<p>También, se puede observar que toma algo de tiempo (30 segundos) en este caso para que un mensaje llegue a toda la red. Por este motivo se dice que las redes que utilizan protocolos gossip son eventualmente <b>consistentes</b>.</p>


<h2 style="font-weight: 600">Quién utiliza protocolos Gossip.</h2>

<h3>Hashicorp Consul</h3>
<p><a href="https://www.consul.io/docs/internals/gossip.html" target="_blank" rel="noopener">Consul</a> es un servicio para devOps que permite automatizar y comunicar programas que corren en diversos proveedores de la nube como <a href="https://aws.amazon.com/es/" target="_blank" rel="noopener">aws</a> o <a href="https://cloud.google.com/?&utm_source=google&utm_medium=cpc&utm_campaign=latam-CL-all-es-dr-bkws-all-all-trial-e-dr-1008075-LUAC0010193&utm_content=text-ad-none-none-DEV_c-CRE_382183366236-ADGP_BKWS+%7C+Multi+~+Google+Cloud-KWID_43700047166266686-kwd-301173107424-userloc_1003325&utm_term=KW_google%20cloud-ST_Google+Cloud&gclid=EAIaIQobChMIooTutKTm6QIVVQiRCh0cewwZEAAYASAAEgKBFfD_BwE&gclsrc=aw.ds" target="_blank" rel="noopener">google cloud</a>. Consul utiliza gossip para administrar y enviar mensaje entre cada uno de sus clusters de clientes.</p>

<h3>Apache Cassandra</h3>
<p><a href="https://docs.datastax.com/en/archived/cassandra/3.0/cassandra/architecture/archGossipAbout.html" target="_blank" rel="noopener">Cassandra</a> es una base de datos <b>NoSQL</b>, distribuida que promete ser escalable, mantener alta disponibilidad y ser tolerante a los fallos. En cassandra los nodos se comunican entre sí utilizando un protocolo gossip. Luego de enviar un mensaje se espera a que el nodo receptor envíe una respuesta que indique recibió el mensaje correctamente, si esto no ocurre se considera al nodo como caído y el resto de sus pares periódicamente revisarán su estado para verificar si es que revivió. Mientras tanto no se le enviarán mensajes, de esta manera Cassandra detecta errores en los nodos de su red y automáticamente reacciona para rutear los mensajes sólo a sus nodos disponibles.</p>

<h3>DynamoDB</h3>
<p><a href="https://aws.amazon.com/es/dynamodb/" target="_blank" rel="noopener">AWS DynamoDB</a> es una de datos <b>NoSQL</b>, serverless que permite cargas de 10 billones de consultas diarias. Al igual que <i>Apache Cassandra</i>, DynamoDB utiliza una red gossip para detectar nodos que no están disponibles para así balancear la carga entre el resto de pares y además asegurarse que toda la base de datos será eventualmente consistente, cuando los mensajes lleguen a toda la red.</p>

<h2 style="font-weight: 600">Gossip en Octopull</h2>
<p>La base de la plataforma Octopull es una red distribuida de sensores de diversos tipos, tales como clima, flujo de líquido o movimiento, entre otros. Estos sensores se comunican entre sí principalmente utilizando el protocolo de comunicación <b>LoRa</b>, el cual permite a dispositivos comunicarse a través de <b><a href="https://www.thethingsnetwork.org/article/lorawan-world-record-broken-twice-in-single-experiment-1" target="_blank" rel="noopener"> grandes distancias</a> y requiriendo poca energía</b>. Al final de la red se encuentra el gateway el cual se encarga de recibir los datos medidos por los sensores para luego subirlos a la nube.</p>

<p>Para asegurar la estabilidad, escalabilidad del sistema y disponibilidad de los datos Octopull utiliza una red gossip en la cual se encuentran <b>sensores, gateway y nodos intermedios</b>. De esta manera se asegura que los datos lleguen correctamente al gateway y se simplifica la instalación de nuevos nodos y sensores, los cuales deberían unirse a la red automáticamente.</p>

<p>Cada nodo en la red periódicamente busca a todos los pares que tienen disponibles, enviando un mensaje por <b>LoRa</b>, para luego poder elegir aleatoriamente algunos de estos para transmitirles un mensaje. <b>Cada mensaje tiene un identificador único</b> y lleva consigo un contador el cual indica la cantidad de veces que le quedan para ser repetido, de esta manera se evita llenar la red de mensajes antiguos. Utilizando el identificador único del mensaje <b>se evita almacenar información duplicada en la base de datos</b>.</p>

<p>El lograr que la red se comunique utilizando un protocolo gossip permite que la plataforma Octopull pueda escalar en el momento en que sea necesario agregar más nodos a la red y resiliente para adaptarse a problemas que puedan surgir.</p>

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

