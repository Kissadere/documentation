Instalando Pufferpanel en Docker
===================================

Pufferpanel ofrece varias imágenes que incluyen las dependencias necesarias para la creación de servidores de juegos.
Recomendamos hacer uso de la *última* versión de la imágen, pues contiene todo lo necesrio para crear servidores de manera rápida.

Creando un contenedor
----------------------

Para crear un contenedor nuevo, inicialo y posteriormente crea un usuario por defecto:

.. code-block::

    mkdir -p /var/lib/pufferpanel
    docker volume create pufferpanel-config
    docker create --name pufferpanel -p 8080:8080 -p 5657:5657 -v pufferpanel-config:/etc/pufferpanel -v /var/lib/pufferpanel:/var/lib/pufferpanel --restart=on-failure pufferpanel/pufferpanel:latest
    docker start pufferpanel
    docker exec -it pufferpanel /pufferpanel/pufferpanel user add
    
¡Listo!. Puedes acceder al panel desde  http://localhost:8080



Comprendiendo la configuración
------------------------

Al utilizar Docker, se han movido las opciones de configuración para hacerlos variables de entorno. Ésto significa que no tendrás que sobreescribir el archivo config.json para aplicar cambios. 
Utiliza el siguiente comando para ver todas las variables de entorno del contenedor.

.. code-block::

    docker inspect pufferpanel --format='{{range .Config.Env}}{{println .}}{{end}}'


Las variables hacen uso del formato JSON de la configuración, utilizando _ para la administración de los apéndices (hijos) en lugar de {}.


Etiquetas
----

pufferpanel/pufferpanel:latest
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Incluye todas las dependencias para servidores de juegos que se incluyen en las plantillas por defecto.
Es una combinación de las imágenes siguientes enlistadas.
Ésta imágen es la recomendda para poder crear servidores de juego de manera fácil y rápida.


pufferpanel/pufferpanel:java
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Incluye Java 8 y 16. Permitiendo la instalación de servidores de Minecraft para versiones posteriores a 1.17 y versiones más recientes para Java Edition.
Java 8 es accionado utilizando java8 como tu comando de inicialización de Java, con javac8 para el compilador.
Java 16 es accionado utilizando java16 como tu comando de inicialización de Java, con javac16 para el compilador.
Java 16 es la configuración por defecto de Java a ser utilizada.


pufferpanel/pufferpanel:srcds
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Incluye todas las dependencias de SRCDS para servidores de Valve como CS:GO, TF2, etcétera.


pufferpanel/pufferpanel:nodejs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Incluye todas las dependencias de NodeJS.


pufferpanel/pufferpanel:base
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Únicamente incluye el panel, en caso de querer crear una imágen personalizada.
