Preguntas Frecuentes
==========================


P: ¿Módulo de facturación?
^^^^^^^^^^^^^^^^^^

Creemos que cualquiera que busque una remuneración mediante la renta de servidores, debería de hacer uso de software de pago con soporte especializado que garantice la seguridad y la satisfacción del usuario final, así mismo como hacer uso de software que ha sido duramente probado en auditorías de seguridad para proteger la información personal de los usuarios.
De ésta forma, no creemos ser la mejor opción para el ofrecimiento de éste servicio.
Es probable que en un futuro se desarrollen módulos de facturación para la renta de servidores, sin embargo; en el estado actual del proyecto, ésto aún no está soportado nativamente.


P: ¿En dónde están mis logs?
^^^^^^^^^^^^^^^^^^^^^

PufferPanel almacena los logs en la siguiente ubicación ``/var/log/pufferpanel``.


P: ¿En dónde están los archivos de los servidores?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

PufferPanel almacena los datos de los servidores en la siguiente ubicación ``/var/lib/pufferpanel/servers``.


P: ¿Puedo migrar de la v1 hacia la v2?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Actualmente no hay madera de poder migrar hacia la v2 debido a los grandes cambios realizados continuamente en ésta versión, lo cual; dificultaría en un principio la reescritura del sistema de migración. Sin embargo, en el momento que la v2 sea más estable, se desarrollarán herramientas capaces de poder migrar de la v1 a la v2 de manera sencilla.


P: ¿Cómo deshabilito el registro público de usuarios?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Inicia sesión en Pufferpanel con una cuenta administrativa y dirígete a la sección de ``ajustes`` en el panel lateral izquierdo, ahí encontrarás una opción marcada como ``Permitir registro de usuarios``, deberás desactivar ésta opción y ´´Guardar´´ los cambios.
De ésta forma, el sistema de registro de usuarios quedará desactivado para el público.


P: ¿Cómo modifico el título del panel web?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Inicia sesión en Pufferpanel con una cuenta administrativa y dirígete a la sección de ``ajustes`` en el panel lateral izquierdo, ahí encontrarás un campo de texto llamado como ``Nombre de la compañía``, modificalo a tu gusto y da clic sobre el botón de ``Guardar`` para guardar los cambios.


P: ¿Cómo puedo alojar un bot, hay alguna plantilla para ello?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Pufferpanel trabaja de manera conjunta con el sistema operativo en el que se encuentre instalado, por lo tanto; soporta cualquer tipo de aplicación que sea compatible con el mismo sistema operativo.
No existen plantillas específicas para bots, cada proyecto funciona de manera distinta y no hay una manera sencilla de poder cubrir todos éstos.

Deberás crear una plantilla propia, puedes hacerlo referenciandote de las `plantillas de ejemplo <https://github.com/PufferPanel/templates/>`_.
