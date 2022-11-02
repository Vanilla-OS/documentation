---
título: Documentación de Vanilla OS
descripción: Descubre cómo utilizar Vanilla OS y todas sus herramientas y ajustes.
---

# Vanilla OS
Prueba la experiencia de GNOME Vanilla en Ubuntu con algo de picante.

## FAQ
Respuestas a las preguntas más frecuentes (aunque el proyecto es muy joven).
- **¿Por qué una nueva distribución?**\
  Vanilla OS surgió de la necesidad de una distribución de Linux basada en Ubuntu que 
  proporcionara GNOME vanilla sin ningún cambio en la experiencia 
  de usuario. Más tarde, su alcance se amplió para experimentar con algunas herramientas y 
  tecnologías, como Almost (inmutabilidad bajo demanda) y Apx (el 
  subsistema basado en Distrobox).
- **¿Utiliza OSTree?**\
  No. Vanilla OS consigue la inmutabilidad a través de [`almost`](https://github.com/Vanilla-OS/almost). 
  Escribimos esta utilidad para la inmutabilidad bajo demanda basada en el 
  atributo de inmutabilidad de los archivos. Este enfoque funciona en cualquier partición 
  sistema de archivos/esquema de particiones. OSTree puede seguir siendo considerado en el futuro.
- **Rolling Release?**\
  No. Vanilla OS is a point release and follows the Ubuntu release cycle.

## Sections
- **[Immutability (`almost`)](/docs/almost)**\
Almost is a utility for on-demand immutability based
on the immutability attribute of files.

- **[Package Manager (`apx`)](/docs/apx)**\
Apx is a package manager that allows you to install and manage packages in a
managed container, without affecting the host system. Occasionally, it is
possible to use `apx` to install packages on the host system as well.
