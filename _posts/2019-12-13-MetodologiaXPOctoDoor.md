---
layout: post
title:  Metodología XP Aplicada a OctoDoor
day:   13 Diciembre, 2019
categories: [Software,Control de accesos,Seguridad]
description: Sí, nos entraron a robar a la casa 3 días después de mudarnos. Quedamos averiados y sin respuesta. Lo pasamos mal!. Somos una empresa de tecnología especialista en crear soluciones de Industrial. Tenemos una plataforma llamada Octopull que utiliza sistemas distribuidos ...
image: https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/octodoor.jpg
alt-image: imagen aplicación octodoor by Octo INC.

author: Rodrigo Morgado
job: CTO
image-author: https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/Team/Rodrigo.jpg
alt-image-author: Foto Rodrigo Morgado
---

<div class="post-text add-padd">

<iframe width="100%" height="500" src="https://www.youtube.com/embed/tAKcst__STk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br><br>

<p>Sí, nos entraron a robar a la casa 3 días después de mudarnos. Quedamos averiados y sin respuesta. Lo pasamos mal! </p>

Somos una empresa de tecnología especialista en crear soluciones de Industrial <a href="https://www.mckinsey.com/business-functions/mckinsey-digital/our-insights/radically-rethink-your-strategy-how-digital-b2b-ecosystems-can-help-traditional-manufacturers-create-and-protect-value" target="_blank" rel="noopener">Internet of Things</a>. Tenemos una plataforma llamada Octopull que utiliza sistemas distribuidos a nivel de microcontroladores para aumentar la confiabilidad del sistema y así proveer de datos a terceros a través de una <strong>API</strong> pública y privada para que terceros puedan construir soluciones.

<p>Como el problema que teníamos era justamente la seguridad, comenzamos a instalar nodos en la casa tanto de clima como infrarrojos. Somos 22 personas entrando y saliendo por lo que duplicar las llaves de acceso era un tema. Sobre todo porque una de las llaves cuesta cerca de 10 lucrecias!. </p>

<p>Nos demoramos un par de horas en configurar e instalar los primeros nodos en la casa y una semana exacta para construir la aplicación móvil Octo Door! </p>

<p>Acá les dejo la receta de cómo sacar una aplicación confiable en una semana.</p>

<ol>
<li> Solo cubre una funcionalidad al principio y la que más valor genere. Queremos abrir puertas por lo que incluso la recuperación de contraseña en el sistema no es prioridad ya que es solo para nosotros 22.</li>
<li>Después del primer días de coding con el equipo, creamos una lista de funcionalidades que podríamos incorporar. Las priorizamos y las dejamos en un backlog. Solo nos quedamos con una para el día siguiente.</li>
<li>Al día siguiente revisamos la funcionalidad y nos preguntamos, ¿qué podemos mejorar en el primer release para hacerlo más confiable y seguro?, cubrimos temas de seguridad y performance por lo que la nueva funcionalidad quedó postergada para el día siguiente.</li>
<li>Al día siguiente nos hicimos la misma pregunta, ¿qué podemos mejorar antes de pensar en incorporar un nuevo elemento?, nos dedicamos 90% al <strong>UX</strong> y un 10% del tiempo al <strong>UI</strong>. Por lo que la nueva funcionalidad quedó nuevamente postergada.</li>
<li>Sin saberlo, estábamos viviendo una de los aspectos más importantes del Extreme Programming, enfocarse en solo una cosa, pero hacerlo bien hasta que todos lo prueben unas 1000 veces y ahí recién pensar en agregar la lógica de edificios y departamentos que decidimos cubrir después. ¿Por qué era importante para nosotros?, simple. Nuestro terreno tiene 2 casas y teníamos que ayudar a solucionar el problema a los vecinos.</li>
</ol><br>

<p>El primer release lo sacamos en 1 semana, 1 semana más para <a href="https://play.google.com/store/apps/details?id=com.octoInc.octo_door" target="_blank" rel="noopener">Google Play</a> y después 1 semana más para <a href="https://apps.apple.com/us/app/octo-door/id1491066941" target="_blank" rel="noopener">Apple Store</a>. Hoy en día, OctoDoor es una realidad.</p>

<div class="row section-author">
<div class="col-md-2"></div>
<div class="col-md-3">
    <img class="author" src="{{page.image-author}}" width="70%" height="auto" alt="{{page.alt-image-author}}">
</div>
<div class="col-md-7 author-space">
    <p>Escrito por:</p>
    <p><b style="font-size:20px">{{page.author}}</b>
    <br>{{page.job}}</p>
</div>
</div>

<div>{% include calltoaction.html %}</div>
{% include footer.html %}



