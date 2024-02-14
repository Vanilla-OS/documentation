---
Title: Manual de almost - Vanilla OS
Description: Manual de la utilidad almost.
PublicationDate: 2023-06-10
Authors: 
  - Contributors of Vanilla OS
---

Note: `almost` has been replaced with `abroot`.

## NOMBRE

```md
almost - una herramienta de inmutabilidad bajo demanda y capas basada en el atributo de archivo (i)nmutable y tmpfs.
```

## SINOPSIS

```md
almost [OPCIÓNES] [COMANDO] [ARGUMENTOS]
```

## DESCRIPCIÓN

```md
almost es una utilidad que provee inmutabilidad bajo demanda alternando la inmutabilidad de los archivos y directorios en la raíz del sistema. También provee una forma de crear capas por encima de los directorios inmutables, permitiendo probar cambios antes de cometerlos.

Opciónes:
    --help/-h       muestra este mensaje
    --verbose/-v        salida detallada
    --version/-V        muestra la versión
    
Comandos:
    enter       configura el sistema de archivos como sólo-lectura o lectura-escritura hasta el próximo reinicio
    config      muestra la configuración actual
    check       revisa si el sistema de archivos está en modo sólo-lectura o lectura-escritura
    run     corre un comando en modo lectura-escritura y regresa al modo sólo-lectura después de que el comando termine
```

## ENTER (entrar)

```md
Configura el sistema de archivos como sólo-lectura o lectura-escritura hasta el próximo reinicio.

Configurar el sistema de archivos como lectura-escritura puede ser considerado un riesgo de seguridad. Sea cuidadoso cuando use este comando.

Uso:
    enter [opciónes] [comando]

Opciónes:
    --help/-h      muestra este mensaje
    --verbose/-v        salida detallada

Comandos:
    ro      configura el sistema de archivos como sólo-lectura
    rw      configura el sistema de archivos como lectura-escritura
    default     configura el sistema de archivos como está definido en el archivo de configuración

Ejemplos:
    almost enter ro
    almost enter rw
```

## CONFIG (configurar)

```md
Administra y muestra la configuración actual.

Uso:
    config [opciónes] [comando]

Opciónes:
    --help/-h       muestra este mensaje

Comandos:
    set [clave] [valor]     Configura un valor de la configuración

Ejemplos:
    almost config
    almost config set Almost::DefaultMode 1
```

## CHECK (checar/revisar)

```md
Revisa si el sistema de archivos está en modo sólo-lectura o lectura-escritura.

Uso:
    check [opciónes] [comando]

Opciónes:
    --help/-h        muestra este mensaje

Ejemplos:
    almost check
```

## RUN (correr/ejecutar)

```md
Corre un comando en modo lectura-escritura y regresa al modo sólo-lectura después de que el comando termine.

Uso:
    run [comando]

Opciónes:
    --help/-h        muestra este mensaje
    --verbose/-v    salida detallada

Ejemplos:
    almost run ls
```

## VEA TAMBIÉN

- [`apx`](apx)

## DIAGNÓSTICOS

```md
almost regresa 0 en éxito, 1 en error.
```

## AUTOR

```md
Contribuidores de Vanilla OS
Traducción al español por @MasterGeekMX
```

## REPORTANDO ERRORES

Reportar los errores al [rastreador de problemas](https://github.com/Vanilla-OS/almost/issues).
