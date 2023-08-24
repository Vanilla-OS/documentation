---
Title: Manual ABRoot
Description: Manual para ABRoot.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

# Manual `abroot`

## Nombre

```text
ABRoot es una utilidad que proporciona una completa inmutabilidad y atomicidad, esto se logra haciendo transacciones entre 2 particiones raíz (A⟺B), también se consiguen las transacciones bajo demanda gracias al shell transaccional.
```

## SINOPSIS

```text
abroot [opción] [comando]
```

## DESCRIPCIÓN

```markdown
Uso:
    abroot [opción] [comando]

Opciones:
    --help/-h       muestra este mensaje
    --verbose/-v        muestra más verbosidad
    --version/-V        muestra la versión

Comandos:
    _update-boot    actualiza la partición boot (sólo para usuarios avanzados)
    get             muestra el estado presente o futuro de la partición raíz
    shell           entra en un shell transaccional en la futura partición raíz y cambia a esa partición en el siguiente reinicio
    exec            ejecuta un comando en el shell transaccional en la futura partición raíz y cambia a esa partición en el siguiente reinicio
```

## EXEC

```markdown
Ejecuta un comando en el shell transaccional en la futura partición raíz y cambia a esa partición en el siguiente reinicio.

Uso:
    exec [comando]

Opciones:
    --help/-h           muestra este mensaje
    --assume-yes/-y     asumir que Sí a todas las preguntas

Ejemplos:
    abroot exec ls -l /
    abroot exec apt install git 
```

```text
Tip: Usted puede ejecutar varios comandos usando "" y pasarlos como una sola cadena.
```

### GET

```markdown
Muestra el estado presente o futuro de la partición raíz.

Uso:
    get [estado]

Opciones:
    --help/-h       muestra este mensaje

Estados:
    present     muetra el estado presente de la partición raíz
    future      muestra el estado futuro de la partición raíz

Ejemplos:
    abroot get present
    abroot get future
```

## SHELL

```markdown
Entra en un shell transaccional en la futura partición raíz y cambia a esa partición en el siguiente reinicio.

Uso:
    shell

Opciones:
    --help/-h           muestra este mensaje
    --assume-yes/-y     asumir que Sí a todas las preguntas

Ejemplos:
    abroot shell
```

## UPDATE BOOT

```markdown
Actualiza la partición boot para propósitos de mantenimiento (sólo para usuarios avanzados).

Uso:
    _update-boot

Opciones:
    --help/-h           muestra este mensaje
    --assume-yes/-y     asumir que Sí a todas las preguntas
```

## VEA TAMBIÉN

- [`apx`](/docs/apx)
- [`vso`](/docs/vso)

## AUTOR

```text
@JMarcosHP
```

## REPORTE DE ERRORES

Reportar los errores al [rastreador de problemas](https://github.com/Vanilla-OS/ABRoot/issues).
