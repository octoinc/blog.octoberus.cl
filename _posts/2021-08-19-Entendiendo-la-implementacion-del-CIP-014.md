---
layout: post
title:  "Entendiendo la implementación del estándar CIP-014"
day:  19 agosto, 2021
categories: Seguridad
description: El 16 Abril de 2013 ocurre el ataque a la subestación eléctrica Metcalf de propiedad de la empresa Pacific Gas and Electric Company (PG&E’s) En un principio se creía que el ataque a los 17 transformadores...
image: "/images/plan-de-seguridad.jpeg"

author: Rodrigo Morgado
job: CTO
image-author: https://octo-marketing.s3-us-west-2.amazonaws.com/Blog/Team/Rodrigo.jpg
alt-image-author: Foto Rodrigo Morgado
---


<div class="row post-text">
    <div class="col-md-2"></div>
    <div class="col-md-8">
    <br>

<p>
El 16 Abril de 2013 ocurre el ataque a la subestación eléctrica Metcalf de propiedad de la empresa Pacific Gas and Electric Company (PG&E’s). En un principio se creía que el ataque a los 17 transformadores había sido perpetrado por un grupo de personas ya que en el lugar se encontraron más de 100 casquillos de un tipo de rifle calibre 7.62×39 mm. Las investigaciones posteriores permitieron concluir que solo una persona pudo haber sido responsable de este ataque, al revisar las cámaras de seguridad y distinguir el efecto visual que produce un disparo.
</p>


<p>
Si bien, este evento no causó un corte de suministro eléctrico a gran escala, produjo daños por sobre los 15 millones de dólares.
</p>


<p>
Este evento ocurrido en Abril de 2013 fue la determinación inmediata para que la FERC(Federal Energy Regulatory Commission) en Estados Unidos acelerara la divulgación de un <b>estándar en seguridad física</b>. En Octubre de ese mismo año, la <a href="https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx" target="_blank" rel="noopener">NERC CIP</a> publica los primeros lineamientos de lo que sería el apartado <b>CIP-014</b>, el cual se formalizaría al año siguiente.
</p>

<br>
<h2>
El espíritu y la intención del NERC CIP-014
</h2>


<p>
Este apartado busca proteger, desalentar a potenciales amenazas a instalaciones de distribución, subestaciones y centros de control, que en caso de existir un ataque, termine afectando su operación o resulten gravemente dañadas y que por lo tanto, en consecuencia, se produzca una inestabilidad en el sistema, separación del sistema en islas o fallas en cascada del sistema interconectado.
</p>


<p>
El foco principal de este apartado está en la protección física de las instalaciones y en la gestión de los riesgos de ataques, clasificando las acciones en proactivas: <b>(a) desalentar amenazas y (b) minimizar vulnerabilidades; y reactivas: (a) mitigar consecuencias</b>.
</p>


<p>
La NERC CIP-014 posee 6 requerimientos, donde el requerimiento 3 (R3) es opcional y solo se aplica cuando el operador y dueño de la instalación crítica son distintos, y por lo tanto, es requerido armar un plan de coordinación entre el dueño y operador.
</p>

<br>
<h3>R1 - Evaluación inicial</h3>

<p>
El primer requerimiento busca desarrollar una <b>evaluación inicial de los riesgos</b> que permita identificar cuales estaciones, subestaciones y centros de control, en caso de ser vulnerados o dañados gravemente como resultado de un ataque físico, genera una estabilidad en el sistema con la capacidad de propagarse, una separación incontrolable (se generan islas) o una falla en cascada del sistema interconectado.
</p>


<p>
Lo que busca el R1 es generar una base sobre la cual se desarrollará e implementará el plan de seguridad física.
</p>


<p>
<b>¿Dónde debería colocar foco la empresa al implementar el requerimiento R1?</b>
</p>

<ul>
<li>Primero distinguir si afecta o no el estándar NERC-CIP al sistema en evaluación.</li>
<li>Crear unos criterios de evaluación estándar que permitan puntuar a todas las instalaciones por igual y por ende, permita comparar la matriz evaluada de insfraestructura crítica.</li>
<li>Evaluar solo lo que es requerido y necesario.</li>
<li>Documentar el criterio de priorización para asegurar físicamente las instalaciones en cuestión.</li>
</ul>

<br><br>

<h3>R2 - Revisión de un tercero del R1</h3>

<p>
Cada dueño de la infraestructura crítica debe solicitar a un tercero <i>no relacionado a la empresa</i> la <b>revisión de la evaluación realizada en R1</b> (revisar quienes pueden ser entidades autorizadas para ejecutar esta revisión en la misma publicación del CEN).
</p>

<p>
Este requerimiento busca <b>validar el criterio definido en R1 y la priorización de los activos de operación</b> como de los ciberactivos. En caso de ser necesario, se debe reevaluar y revisar si es neecesario, aplicando las modificaciones que la tercera parte indique.
</p>


<p>
<b>¿Dónde debería colocar foco la empresa al implementar el requerimiento R2?</b>
</p>

<ul>
<li>Seleccionar bien a la empresa que revisará la evaluación inicial (consultores en seguridad con experiencia en la industria, profesionales PSP, entre otros).</li>
<li>Distinguir y declarar posibles conflictos de interés que afecten la objetividad de la revisión de la evaluación inicial.</li>
<li>Asegurarse que el plan completo de seguridad es entendido bien.</li>
<li>Recordar que este es un proceso colaborativo entre la empresa responsable de llevar a cabo la evaluación como del revisor.</li>
</ul>

<br><br>
<h3>R4 - Evaluación de las amenazas y vulnerabilidades</h3>

<p>
Conducir una <b>evaluación de las potenciales amenazas y vulnerabilidades de un ataque físico</b> las instalaciones identificadas en R1 (estaciones, subestaciones y centros de control).
</p>

<p>
Este proceso es importante que se ejecute al detalle porque incide directamente en la inversión que la empresa debe realizar en un futuro para cumplir con su plan de seguridad física y por ende, proteger tanto los ciberactivos como activos de operación.
</p>


<p>
<b>¿Dónde debería colocar foco la empresa al implementar el requerimiento R4?</b>
</p>

<ul>
<li>Acá es bueno utilizar frameworks de evaluación de amenazas y vulnerabilidades ya existentes en el país como en el extranjero. En Estados Unidos, el homeland, que viene siendo el Ministerio del Interior en Chile, publicada cada cierto tiempo documentos y templates que permiten hacer una correcta evaluación de amenazas y vulnerabilidades. La FERC hace poco tiempo publicó un template que sirve como base para la evaluación de amanezas y vulnerabilidades como para la implementación del plan de seguridad física. Lo pueden encontrar acá: <a href="https://www.ferc.gov/sites/default/files/2020-04/security-plan-example.pdf" target="_blank" rel="noopener">Physical Security Plan</a></li>
<li>Este proceso debe ser revisado constantemente porque nuevas amenazas surgen y debe actualizarse.</li>
<li>Asegurarse que el plan completo de seguridad es entendido bien.</li>
<li>Aplicar metodologías cuantitativas que permitan hacer una priorización más objetiva.</li>
</ul>


<br><br>
<h3>R5 - Desarrollo e implementación del plan de seguridad física</h3>

<p>
<b>Desarrollar, implementar y documentar el plan de seguridad física </b>que cubra las estaciones y subestaciones de transmisión, como centros primarios de control.
</p>

<p>
Es mejor tener una visión holística de este proceso y más que pensar en un plan, es desarrollarlo como un programa de acción con responsables y fechas.
</p>

<p>
<b>¿Dónde debería colocar foco la empresa al implementar el requerimiento R5?</b>
</p>

<ul>
<li>Usar un método enfocado en la creación de un programa más que en un plan</li>
<li>Incluir todo lo que se espera en un programa de seguridad para infraestructura crítica. Comenzar con un template base.</li>
<li>Ser realista en los tiempos de implementación, en la inversión requerida, y en las metas del programa de seguridad.</li>
</ul>

<br><br>
<h3>R6 - Evaluación y revisión por parte de un tercero de R4 y R5</h3>

<p>
En este proceso se revisa la evaluación realizada en R4 y del plan de seguridad desarrollado en R5.
</p>

<p>
Este proceso busca mejorar la protección, aumentar la disuasión a posibles ataques, y fortalecer la eficiencia operacional del plan de seguridad.
</p>

<p>
Acá se busca <b>validar el plan de seguridad física desarrollado</b> y en caso de ser necesario, identificar y corregir los posibles errores que éste presente.
</p>

<p>
<b>¿Dónde debería colocar foco la empresa al implementar el requerimiento R6?</b>
</p>

<p>Buscar una tercera parte con la competencia y experiencia en la industria. Como <a href="https://www.linkedin.com/company/zooft-company/" target="_blank" rel="noopener">OCTO INC</a> ayudamos en una pequeña parte de la <b>creación del plan de seguridad física </b> en todo lo que tiene que ver con control de acceso. Nos hemos dedicado a crear una solución resiliente y segura para que la empresa administre los accesos a sus instalaciones físicas de mejor manera.</p>

<br>

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

 <!-- <div>{% include calltoaction.html %}</div> -->
{% include footer.html %}