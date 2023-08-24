---
Title: Inmutabilidad (almost) - Vanilla OS
Description: Descubre cómo utilizar Almost, la utilidad de inmutabilidad bajo demanda.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

# Inmutabilidad (`almost`)

`almost` es una utilidad que proporciona inmutabilidad bajo demanda alternando la
inmutabilidad de archivos y directorios en la raíz del sistema. También proporciona
una forma de crear capas sobre los directorios inmutables, lo que le permite probar los
cambios antes de confirmarlos.

Note: `almost` has been replaced with `abroot`.

## ¿Cómo funciona?

La inmutabilidad en `almost` se obtiene estableciendo el indicador `i` en todos los archivos y
directorios en la raíz del sistema, excepto los que se utilizan para almacenar archivos del
directorio de inicio del usuario (`/home, /etc, /var`).

Lo mismo puede lograrse utilizando el comando `chattr`, pero `almost` proporciona consistencia al
restaurar el estado por defecto del sistema después de un reinicio, y con características adicionales
para gestionar mejor la inmutabilidad, por ejemplo, iniciar un comando mientras se desactiva temporalmente
la inmutabilidad.

### Inmutabilidad bajo demanda

Esto se denomina inmutabilidad "bajo demanda", ya que puede activarse o desactivarse en cualquier momento. La
inmutabilidad está pensada como una medida de seguridad para evitar cambios accidentales en el sistema, por lo que
debería mantenerse activada la mayor parte del tiempo.

Debido a su naturaleza, `almost` está listo para usar y funciona en todos los sistemas
de archivos y configuraciones.

### El nombre

El nombre `almost` viene del hecho de que no es una solución de inmutabilidad completa, sino
más bien una herramienta para ayudarle a conseguirla, sin dejar de poder de hacer
cambios cuando sea necesario.

## Qué no es

`almost` no tiene soporte para las instantáneas. Cada cambio realizado en el sistema es permanente y
no puede ser revertido sin restaurar desde una copia de seguridad o degradar el sistema. Para evitar esto, siempre
debe probar sus cambios usando capas antes de confirmarlos. La única razón para desactivar la inmutabilidad sería para editar
un archivo de configuración que no está en los directorios comunes, o para instalar controladores. Desactivar la inmutabilidad
para instalar una aplicación o biblioteca no es recomendable. Utiliza [`apx`](/docs/apx), [`Flatpak`](/docs/flatpak),
[`Snap`](/docs/snap) o [`AppImage`](/docs/appimage) en su lugar.

## Uso

- [Manual](almost-manpage)
