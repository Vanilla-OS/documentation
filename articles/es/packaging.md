---
Title: Empaquetado - Vanilla OS
Description: Averigüe como empaquetar software y librerías para Vanilla OS.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

Empaquetar es el proceso de crear un paquete para un software o una librería, para
que pueda ser instalada en una distribución. Vanilla OS tiene un sistema de archivos raíz
poco convencional, por lo que algunas consideraciones y pautas deben ser seguidas.

## ¿Cuando empaquetar?

Vanilla OS es una distribución transaccional, lo que significa que recibe
actualizaciones vía transacciones. El proceso es manejado por [ABRoot](/docs/ABRoot),
lo que requiere un reinicio para que los cambios surtan efecto. Esto significa que el usuario
tendrá que reiniciar el sistema después de instalar un paquete, y esto no es ideal.
Además, la partición raíz es muy pequeña, pero esto es intencional para prevenir que el
usuario instale demasiados paquetes, lo cual expondría el sistema a vulnerabilidades de
seguridad y mayor complejidad durante las transacciones.

Por estas razones, es recomendable empaquetar solamente software esencial y librerías.
Para entender mejor qué es esencial, puede revisar la siguiente tabla:

| Software | Esencial | Razón |
| -------- | -------- | ----- |
| Chromium | No | Es un navegador web, el cual no es esencial para el sistema y puede ser instalado vía [Apx](/docs/apx), [Flatpak](https://handbook.vanillaos.org/2022/12/09/install-flatpaks.html), [Snap](https://snapcraft.io/) ó [AppImage](https://appimage.org/). |
| fuse | Sí | Este es un controlador de dispositivos, el cual es esencial para que AppImage funcione, y debe ser instalado por fuera del contenedor de Apx. |
| GIMP | No | Es un editor gráfico, el cual no es esencial para el sistema y puede ser instalado vía [Apx](/docs/apx), [Flatpak](https://handbook.vanillaos.org/2022/12/09/install-flatpaks.html), [Snap](https://snapcraft.io/) ó [AppImage](https://appimage.org/). |

## Pautas de Empaquetado

Esta sección está organizada en múltiples subsecciónes, cada una describiendo
un aspecto diferente de el proceso de empaquetamiento.

### Nombrado

No hay restricciones en el nombre del paquete, pero es recomendable que
use el mismo nombre que el proyecto original. Por ejemplo, si el proyecto se
llama `foo`, el paquete debe llamarse `foo`, y no `bar`. Esto es importante
porque permite al usuario fácilmente identificar el paquete.

### Versionamiento

La versión del paquete debe ser la misma que del proyecto original (también llamado _upstream_),
con cambios menores si es necesario. Por ejemplo, si la versión _upstream_ es `1.2.3`, la versión
del paquete debe ser `1,2,3`, y no `2.0.0`. Si el paquete tiene algunos cambios menores,
la versión debería ser `1.2.3-1`, `1.2.3-2`, etc. La versión nunca debe rebasar o
quedarse atrás de la versión _upstream_.

### Almacenamiento

Algunas aplicaciones requieren mucho almacenamiento, y esto puede ser un problema
para Vanilla OS, la cual tiene una partición raíz muy pequeña. Si la aplicación
no puede ser instalada en el contenedor Apx o de cualquier otra forma, es recomendable
editar su comportamiento para que almacene sus datos en el directorio _home_ del usuario
o en la partición `/home`, la cual tiene mucha más capacidad.

Es también buena práctica, ya que permite al usuario respaldar con facilidad
los datos de la aplicación, y también fácilmente remover la aplicación sin perder
los datos.
