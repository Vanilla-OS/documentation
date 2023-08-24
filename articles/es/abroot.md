---
Title: ABRoot - Introducción
Description: Descubra cómo usar ABRoot.
Authors: Contributors of Vanilla OS
---

> Esta documentación se refiere a ABRoot v1, no a v2. La documentación de v2 todavía se está escribiendo.

# Immutabilidad (`abroot`)

`abroot` es una utilidad que proporciona una completa inmutabilidad y atomicidad, esto se logra haciendo transacciones entre 2 particiones raíz (A⟺B), también se consiguen las transacciones bajo demanda gracias al shell transaccional. 
## Cómo funciona

El sistema de archivos de GNU/Linux es una estructura con una gerarquía de archivos donde está la raíz y otros directorios.
La raíz es el directorio primario de la gerarquía que contiene las demás particiones.
En un sistema de archivos inmutable, la partición raíz es de solo lectura, impidiendo la instalación de paquetes esenciales, como los controladores en el sistema anfitrión. 

`abroot` permite instalar módulos del kernel, controladores y otros paquetes esenciales sin comprometer la inmutabilidad del sistema de archivos.

Cuando se ejecuta un comando en `abroot`, una transacción se inicia en el shell transaccional en la segunda partición raíz. Si la transacción tiene éxito, los cambios se aplican usando una superposición y se sincroniza con la partición raíz actual al reiniciar. Si la transacción falla, no se aplica ningún cambio (debido a una propiedad llamada atomicidad). `abroot` también permite las transacciones bajo demanda usando el comando `abroot shell`.

Las instalaciones de Vanilla OS crean las particiones raíz y boot para ambos estados (A y B) (20GB por cada partición raíz) como un requisito para `abroot`.

## Estados

`abroot` tiene dos estados - presente y futuro. Cuando usted está en su instalación de Vanilla OS por primera vez, el estado presente es A. Cuando usted reinicia el sistema, el estado automáticamente se cambia a B. Cuando usted instala un paquete usando `abroot`, se instala en la futura partición raíz y se sincroniza con la partición raíz actual al reiniciar.

## Actualizaciones

`abroot` hace uso de `vso` para realizar actualizaciones inteligentes de forma automática en segundo plano instalándolas en la futura partición raíz, esto ahorrará tiempo y no se requerirá aplicar actualizaciones después de reiniciar.

## Nombramiento

El nombre de `ABRoot` se refiere a las dos particiones raíz A y B (A⟺B), para realizar las transacciones. 

## Uso

- [Manpage](/docs/ABRoot/manpage)
