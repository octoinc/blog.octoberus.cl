---
layout: post
title:  "¿Cómo el protocolo Gossip y mensajes Ping-Pong ayudan a conocer los estados de los sensores de seguridad y cumplir con el estándar NERC-CIP?"
day:  03 agosto, 2021
categories: Seguridad
author: 'Equipo Octopull'
description: Como ya es sabido, el 9 de Octubre de 2020, el Coordinador Eléctrico Nacional (CEN) hizo el lanzamiento oficial del estándar de Ciberseguridad NERC-CIP el cual cuenta con 13 apartados de buenas práctica...
image: "/images/protocolo-gossip-image.png"

author: Rodrigo Morgado
job: CTO
image-author: https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/Team/Rodrigo.jpg
alt-image-author: Foto Rodrigo Morgado
---

<div class="row post-text">
    <div class="col-md-2"></div>
    <div class="col-md-7">
    <br>

<p>Como ya es sabido, el 9 de Octubre de 2020, el Coordinador Eléctrico Nacional (CEN) hizo el lanzamiento oficial del estándar de Ciberseguridad NERC-CIP el cual cuenta con 13 apartados de buenas práctica, los cuales serán exigibles a partir del cuarto mes, como es el caso particular del CIP-008, requerimiento R4, en relación a la notificación y reporte de incidentes de ciberseguridad, hasta el mes número 24 donde en este caso sería completar el proceso de revisión por una entidad, profesional u organismo competente del desarrollo e implementación del plan de seguridad física, requerimiento R6 del CIP-014.
</p>

<p>
La FERC (Federal Energy Regulatory Commission) el año pasado publicó un <a href="https://www.ferc.gov/sites/default/files/2020-04/security-plan-example.pdf" target="_blank">template actualizado</a> que sirve como base para que las empresas, reguladas en Estados Unidos, puedan desarrollar e implementar un plan de seguridad física. En este documento se describe el “Floor Plan” (funcionalidad ya implementada en Octo Security) y la revisión periódica de los sistemas de seguridad física implementados en la instalación a proteger.
</p>

<p>
Como Octo Security utiliza IIoT para comunicar los sensores entre sí, posee un protocolo llamado Gossip que se programa a nivel de microprocesadores para conocer el estado actual de cada nodo. Gossip (rumor en inglés) es un protocolo de comunicación “peer-to-peer” que permite distribuir mensajes en una red de nodos IIoT. Si bien, es un protocolo conocido en Cloud Computing, Octo Inc incorporó una versión simplificada y más liviana a nivel de nodo que cumpla con el objetivo.
</p>

<p>
Para ilustrar el funcionamiento, supongamos que tenemos una red de nodos con distintos sensores conectados en una instalación física: (a) Un sensor magnético para seguridad, (b) Dos sensores de clima y (c) Un Sensor de Ruido.
</p>

<p>
El sensor magnético funciona en base a eventos, eso significa que si alguien abre una puerta o ventana, el sensor cambia su estado de 0 a 1, informando al sistema el cambio de estado. Lo mismo sucede cuando se cierra la puerta o ventana, el nodo informa el cambio de estado de abierto a cerrado, de 1 a 0. El funcionamiento de los sensores de clima y ruido es distinto ya que funcionan siguiendo la configuración que hizo el administrador en Octo Security. El reporte de datos es en base a tiempos o eventos. Desde la administración, el usuario con el permiso adecuado puede definir un tiempo de 5 minutos para enviar datos de ruido, pero si existe un evento (intrusión), el sensor comienza a reportar cada 1 segundo el nivel de decibel que registra.
</p>

<p>
Si el sensor de ruido llegase a fallar, su detección es fácil, porque el nodo principal y la nube están esperando un dato en el intervalo de tiempo definido previamente por el usuario y de no recibirse envían un mensaje “ping” esperando la respuesta “pong” para saber si es un problema de latencia o encolamiento de datos.
</p>

<p>
Para el caso del sensor magnético, la lógica es similar, la diferencia reside en que periódicamente el sistema envía mensajes “ping” para esperar la respuesta “pong” y así saber bien el estado actual del sensor. Este sensor solo reporta datos frente a eventos y por lo tanto, de tener un sensor magnético con falla, podría mal interpretarse de que no han existido eventos asociados.
</p>

<p>
Esta lógica de funcionamiento del sistema, permite periódicamente generar reportes de la “salud” de los nodos y cumplir con el plan de seguridad física en cuanto a la revisión periódica del sistema de seguridad implementado.
</p>

<p>
Cuando un nodo no posee acceso a la nube tiene que enviarle los datos a otro peer y ese mensaje se guarda en otro peer y así es como se activa el Protocolo Gossip. Este protocolo entra en juego cuando se tiene que armar una red de mensajes, como mandarle un mensaje a una y otra persona, hasta lograr salir a internet. Pero cada vez que el mensaje pasa de uno a otro se genera persistencia de manera local, guardando el dato con toda su información (fecha/hr/min/seg/mlseg, valor del dato sensor y ID nodo emisor) localmente.
</p>

<p>
Para resguardar aún más la información añadimos un protocolo TTL (time to leave) sobre el protocolo Gossip. Este protocolo TTL distribuye el dato de manera limitada, siendo este guardado, luego de un número definido de distribución del dato dentro del sistema de nodos, evitando que mensajes queden en el aire de manera infinita entre nodos.
</p>

<p>
De esta manera buscamos que nuestra solución sea un aporte y ayuda en términos de seguridad de la infraestructura crítica, ateniéndonos al cumplimiento del estándar NERC-CIP.
</p>

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
