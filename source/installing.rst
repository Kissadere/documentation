Instalación de Pufferpanel
======================


Requerimientos del sistema
-------------------

* Un VPS o Servidor Dedicado (Sistemas operativos de 32-Bits no están soportados)
* Acceso root o privilegios de administrator (root o sudo)
* Cualquiera de los siguientes sistemasa operativos:

+-----------------------+-------+----------------+
| OS/Versión            | AMD64 | ARM            |
+=======================+=======+================+
| Centos 7              | Sí    | No             |
+-----------------------+-------+----------------+
| Centos 8              | Sí    | No             |
+-----------------------+-------+----------------+
| Fedora 33             | Sí    | No             |
+-----------------------+-------+----------------+
| Ubuntu Bionic (18.04) | Sí    | No             |
+-----------------------+-------+----------------+
| Ubuntu Cosmic (18.10) | Sí    | No             |
+-----------------------+-------+----------------+
| Ubuntu Disco (19.04)  | Sí    | No             |
+-----------------------+-------+----------------+
| Ubuntu Eoan (19.10)   | Sí    | No             |
+-----------------------+-------+----------------+
| Ubuntu Focal (20.04)  | Sí    | Sólo ARM64     |
+-----------------------+-------+----------------+
| Ubuntu Groovy (20.10) | Sí    | Sólo ARM64     |
+-----------------------+-------+----------------+
| Debian Jessie (8)     | Sí    | No             |
+-----------------------+-------+----------------+
| Debian Stretch (9)    | Sí    | No             |
+-----------------------+-------+----------------+
| Debian Buster (10)    | Sí    | No             |
+-----------------------+-------+----------------+
| Debian Bullseye (11)  | Sí    | No             |
+-----------------------+-------+----------------+
| Raspbian Buster (10)  | No    | ARM64 o ARM32  |
+-----------------------+-------+----------------+


Instalación
----------

Con el fin de simplificar la instalación, en caso de contar con alguno de los sistemas operativos enlistados; simplemente deberás instalar nuestro paquete.

.. tabs::

   .. tab:: Ubuntu/Debian

      .. code-block:: bash

         curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.deb.sh | sudo bash
         sudo apt-get install pufferpanel
         sudo systemctl enable pufferpanel
         

   .. tab:: CentOS

      .. code-block:: bash

         curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.rpm.sh | sudo bash
         sudo yum install pufferpanel
         sudo systemctl enable pufferpanel
         
         
   .. tab:: Docker
   
      Para utilizar el sistema de Docker, dirígete hacia :doc:`ésta página <installing-docker>`.


Otro sistema operativo
----------------------
.. warn::
   No recomendamos la instalación en algún sistema operativo distinto a los establecidos, procede bajo tu propio riesgo.
   
Es posible instalar Pufferpanel en cualquier otro sistema operativo basado en Debian o Red Hat, incluso si no está en la lista de requerimientos.
Para poder hacer la instalación en algún sistema operativo no incluído, deberás agregar tu sistema operativo y tu versión :code:`os={os} dist={version}` en el comando curl, entre sudo y bash, por ejemplo:

.. code-block:: bash
         
   curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.deb.sh | sudo os=ubuntu dist=focal bash
           

Puertos
-----

Necesitarás hacer uso de los siguientes puertos para el correcto funcionamiento de Pufferpanel, recuerda permitir el tráfico entranda y saliente desde los siguientes puertos

* 8080: Acceso Web
* 5657: SFTP


Crear usuario administrativo
---------------

Para crear el primer usuario con privilegios de administrador en Pufferpanel, utiliza el siguiente comando.
No olvides marcar la opción "Y" cuando el sistema te lo indique para poder otorgar privilegios de administración.

.. code::

   $ sudo pufferpanel user add


Inicializar Pufferpanel
------------------

.. code::

   $ sudo systemctl enable --now pufferpanel

--------------------
Administración del servicio
--------------------

Pufferpanel hace uso de systemd para administrar el servicio del mismo, consulta la págian de man `man systemctl` o dirígete `a aquí <https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units>`_ para obtener más información al respecto.

¡Listo!
-----

Has terminado la instalación de Pufferpanel, ahora podrás acceder a tu panel desde IP:8080 en tu navegador

Additional resources:

* :doc:`Habilitar SSL <guides/ssl-setup-nginx>`
* :doc:`Cambiar motor de la base de datos <guides/database>`
