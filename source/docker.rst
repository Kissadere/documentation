Utilizar Docker con Pufferpanel
=============================

Primero, deberás instalar Docker en el nodo donde se encuentre Pufferpanel. Refierte a la guía de instalación de Docker, ubicada en https://docs.docker.com/get-docker/. Para el caso específico de Ubuntu, no hagas la instalación mediante `snap`, puesto que no tendrá privilegios de escritura sobre `/var/lib/pufferpanel`.

Por consiguiente, crea un grupo para docker (si es que no existe alguno) y adiciona a pufferpanel como un usuario de éste grupo.

.. code::

   sudo groupadd --force --system docker
   sudo usermod -a -G docker pufferpanel

Reinicia Pufferpanel
.. code::

   systemctl restart pufferpanel
