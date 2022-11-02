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
  del sistema de archivos/esquema de particiones. OSTree puede seguir siendo considerado en el futuro.
- **Lanzamiento continuo**\
  No. Vanilla OS es un lanzamiento puntual y sigue el ciclo de lanzamiento de Ubuntu.

## Secciones
- **[Inmutabilidad (`almost`)](/docs/almost)**\
Almost es una utilidad para la inmutabilidad bajo demanda basada
en el atributo de inmutabilidad de los archivos.

- **[Administrador de paquetes (`apx`)](/docs/apx)**\
Apx es un administrador de paquetes que permite instalar y gestionar paquetes en un
contenedor gestionado, sin afectar al sistema anfitrión. Ocasionalmente, es
posible utilizar `apx` para instalar paquetes en el sistema anfitrión también.
