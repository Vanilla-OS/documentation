---
title: Documentación de Vanilla OS
description: Descubra cómo utilizar Vanilla OS y todas sus herramientas y ajustes.
sidebar_position: 1
---

# Vanilla OS

*Pruebe la experiencia de GNOME Vanilla en Ubuntu con algunos condimentos.*

**Está página es la documentación oficial para los componentes de Vanilla OS en su edición en Español.**<br />
Lea el [**Manual**](https://handbook.vanillaos.org) para aprender guías y tutoriales escritos por la comunidad.

## PREGUNTAS FRECUENTES

Respuestas a las preguntas más frecuentes (aunque el proyecto es muy joven).
- **¿Por qué una nueva distribución?**<br />
  Vanilla OS surgió de la necesidad de una distribución de Linux basada en Ubuntu que 
  proporcionara GNOME vanilla sin ningún cambio en la experiencia 
  de usuario. Más tarde, su alcance se amplió para experimentar con algunas herramientas y 
  tecnologías, como ABRoot y Apx (el 
  subsistema basado en Distrobox).
  
- **¿Utiliza OSTree?**<br />
  No. Vanilla OS consigue la inmutabilidad a través de [`ABRoot`](https://github.com/Vanilla-OS/ABRoot)[anteriormente lo conseguíamos gracias a la utilidad `almost`]. El uso de OSTree se considerará en el futuro.
  
  Escribimos esta utilidad para la inmutabilidad bajo demanda basada en el 
  atributo de inmutabilidad de los archivos. Este enfoque funciona en cualquier partición 
  del sistema de archivos/esquema de particiones.
  
  Actualmente hemos introducido otra nueva utilidad para conseguir la inmutabilidad bajo demanda
  llamada [`ABRoot`](https://github.com/Vanilla-OS/ABRoot) reemplazando a `almost` para proveer una completa inmutabilidad y atomicidad, al realizar las transacciones entre 2 particiones raíz (A⟺B). También se consiguen las transacciones bajo demanda gracias al shell transaccional.
  
- **Lanzamiento contínuo**<br />
  No. Vanilla OS es un lanzamiento puntual y sigue el ciclo de lanzamiento de Ubuntu.

## Documentación

- **[Instalación](https://handbook.vanillaos.org/2022/11/05/installation.html)**<br />
Instrucciones para la instalación del sistema mediante [Vanilla Installer](https://github.com/Vanilla-OS/vanilla-installer).

- **[Configuración Inicial](https://handbook.vanillaos.org/2022/11/18/first-setup.html)**<br />
Con la utilidad de [Configuración Inicial](https://github.com/Vanilla-OS/first-setup) que proporciona Vanilla OS, usted podrá ajustar su sistema a sus necesidades.

- **[Administrador de paquetes (`apx`)](/apx/)**<br />
Apx es un administrador de paquetes que permite instalar y gestionar paquetes en un
contenedor gestionado, sin afectar al sistema anfitrión. `apx` puede instalar paquetes de los repositorios oficiales de Ubuntu, pero no solo eso, tambien de Arch User Repository (AUR) y de los repositorios DNF de Fedora dentro de un contenedor. Está muy bien integrado con el sistema anfitrión. Para los paquetes con interfaz gráfica (GUI), un acceso directo se creará automáticamente y se agragará al menú de aplicaciones de GNOME.

- **[Operador del Sistema de Vanilla (`VSO por sus siglas en inglés`)](/vso)**<br />
El [Operador del Sistema de Vanilla](/vso) es una utilidad de Vanilla OS que le permite realizar tareas de mantenimiento como actualizar el software, programar tareas, etc.

- **[Panel de Control de Vanilla](https://github.com/Vanilla-OS/vanilla-control-center)**<br />
Es una utilidad que le permite configurar las [actualizaciones](https://handbook.vanillaos.org/2022/12/10/updates.html) e instalar [controladores adicionales](https://handbook.vanillaos.org/2022/12/10/install-additional-drivers.html) en su sistema.

- **[Inmutabilidad (`almost`)](/almost)**<br />
~~[Almost](https://github.com/Vanilla-OS/almost) es una utilidad para la inmutabilidad bajo demanda basada
en el atributo de inmutabilidad de los archivos.~~ (Almost fue reemplazado por `ABRoot`).
