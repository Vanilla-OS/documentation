---
Title: Administrador de Paquetes (apx) - Vanilla OS
Description: Descubra cómo usar apx, el administrador de paquetes de Vanilla OS.
PublicationDate: 2023-06-10
Authors: 
  - Contributors of Vanilla OS
---

`apx` es el administrador de paquetes de Vanilla OS que es fácil de usar para instalar paquetes de múltiples fuentes dentro de contenedores sin la necesidad de alterar el sistema de archivos raíz.

## Cómo funciona

`apx` introduce completamente un nuevo paradigma en la administración de paquetes. La idea es
usar su sistema solo como un almacen de sus archivos, dejándolo limpio de paquetes
y limitando el riesgo de quiebres por incompatibilidades, paquetes mal contruidos
o que causan conflicto.

Esto se logra instalando el software dentro de uno o más contenedores totalmente administrados por `apx` teniendo acceso restringido a los recursos de su sistema pero con la posibilidad de usar solo sus controladores, servidor gráfico, etc.

Su directorio home está mapeado dentro del contenedor lo que le permite a usted acceder
a sus archivos de configuración, preferencias y otros archivos vitales necesarios para
los paquetes instalados, y al mismo tiempo que los paquetes instalados puedan acceder
a sus archivos, por ejemplo, abrir un archivo en LibreOffice.

### Sistema Anfitrión

Si bien la instalación de software en el sistema anfitrión va en contra de ideología del proyecto, hay casos en donde es esencial. Por ejemplo, cuando usted necesita
instalar un módulo del kernel o controlador.

En casos como este, usted puede usar el comando `abroot exec apt install <package_name>` o `abroot shell apt install <package_name>` para instalar directamente en el sistema anfitrión sin usar contenedores, *pero tenga en cuenta
que esto no es recomendable*.

### Múltiples fuentes

Por defecto, `apx` proporciona un contenedor basado en la distribución Ubuntu 22.10
para proveer Vanilla OS 22.10, y aísla todos los comandos del administrador de
paquetes de la distribución (en este caso `apt` para Ubuntu).

Sin embargo, usted puede instalar paquetes de otras distribuciones. Por ejemplo, usando la opción `--aur`,
un nuevo contenedor basado en Arch Linux se creará. Aquí, `apx` se encargará de administrar los paquetes de AUR
(Pacman y Yay), integrándolos con el sistema anfitrión.
Usando la opción `--dnf` con `apx` se creará un nuevo contenedor basado en Fedora Linux. Aquí, `apx`
se encargará de administrar los paquetes de los repositorios DNF de Fedora, integrándolos con el sistema anfitrión.

Para los paquetes con interfaz gráfica, `apx` crea archivos `.desktop` automaticamente dentro de los contenedores y los añade al menú de aplicaciones. Estas aplicaciones también se mostarán al momento de utilizar la opción "Abrir con" en el menú de nautilus. Los paquetes con interfaz gráfica instalados dentro de los contenedores se mostrarán en la sección Subsistema en el [Panel de control de Vanilla](/docs/vanilla-control-center).

Para el control de calidad, nosotros hemos limitado esta función para implementaciones específicas. Actualmente, solo las opciones `--aur` y `--dnf` están soportadas,
pero estamos planeando implementar soporte para el administrador de paquetes Nix en un futuro.

### Nombramiento

El nombre `apx` proviene de **apt (Advanced Packaging Tool)**, el administrador de paquetes usado por Debian y sus derivadas. **X** consta de dos líneas (host y contenedor) superpuestas una a otra, donde el contenedor está en la parte superior,
lo que significa que es la parte principal del sistema anfitrión.

## Uso

- [Manual](/docs/apx/manpage)
