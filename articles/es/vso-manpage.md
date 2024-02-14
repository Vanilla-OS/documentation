---
Títle: Manual vso - Vanilla OS
Description: Manual para vso.
PublicationDate: 2023-06-10
Authors: 
  - Contributors of Vanilla OS
---

## NOMBRE

```md
VSO es una utilidad que le permite realizar tareas de mantenimiento en su instalación de
Vanilla OS.
```

## SINOPSIS

```md
vso [opciones] [comandos] [argumentos]
```

## DESCRIPCIÓN

```md
Uso: 
    vso [opciones] [comandos] [argumentos]

Opciones:
    -h, --help            Muestra este mensaje

Comandos:
    config                  Configurar VSO
    create-task             Crear una nueva tarea
    delete-task             Eliminar una tarea
    developer-program       Unirse al programa de desarrolladores
    help                    Mostrar este mensaje
    list-tasks              Listar todas las tareas
    rotate-tasks            Rotar tareas
    trigger-update          Ejecutar una actualización del sistema
    version                 Mostrar la versión
```

## CONFIG

```md
Descripción: 
    Configurar VSO

Uso:
    vso config [opciones] [comando]

Opciones:
    --help/-h           mostrar este mensaje
    --assume-yes/-y     asumir que Sí a todas las preguntas

Comandos:
    show                mostrar la configuración actual
    get <key>           obtener un valor de configuración
    set <key> <value>   establecer un valor de configuración

Ejemplos:
    vso config get updates::schedule
    vso config set updates::schedule weekly
```

## CREATE TASK

```md
Descripción: 
    Crear una nueva tarea

Uso:
    vso create-task [opciones] [argumentos]

Opciones:
    --help/-h               mostrar este mensaje

Argumentos:
    --name/-n               nombre de la tarea
    --description/-d        descripción de la tarea
    --need-confirm          pedir confirmación antes de ejecutar la tarea
    --command/-c            comando a ejecutar
    --after-task            ejecutar la tarea después de otra
    --after-task-success    ejecutar la tarea después de otra solo si tuvo éxito
    --after-task-failure    ejecutar la tarea después de otra solo si falló
    --every/-e              ejecutar la tarea cada X tiempo (minutos, horas, días)
    --at/-a                 ejecutar la tarea en un tiempo específico (hh:mm)
    --on-boot               ejecutar la en el arranque
    --on-shutdown           ejecutar la tarea al apagar
    --on-login              ejecutar la tarea al iniciar sesión
    --on-network            ejecutar la tarea al conectarse a la red
    --on-disconnect         ejecutar la tarea al desconectarse de la red
    --on-battery            ejecutar la tarea cuando usa batería
    --on-low-battery        ejecutar la tarea cuando hay batería baja (20%)
    --on-charge             ejecutar la tarea al cargar la batería
    --on-full-battery       ejecutar la tarea al cargar completamente la batería
    --on-condition-command  ejecutar la tarea en una condición específica
    --on-process            ejecutar la tarea cuando se inicia un proceso

Ejemplos:
    vso create-task -n "Batería completamente cargada" -d "notificar al completar la carga" -c "notify-send 'Batería completamente cargada'" --on-full-battery
    vso create-task -n "Ejecutar terminal" -d "Ejecutar una terminal si se abre la aplicación de Configuración" -c "kgx" --on-process gnome-control-center
```

## DELETE TASK

```md
Descripción: 
    Eliminar una tarea

Uso:
    vso delete-task [tarea] [opciones]

Opciones:
    --help/-h       mostrar este mensaje

Ejemplos:
    vso delete-task mi-tarea
    vso delete-task "mi tarea"
```

## DEVELOPER PROGRAM

```md
Descrición: 
    Unirse al programa de desarrolladores

Uso:
    vso developer-program [opciones]

Opciones:
    --help/-h       mostrar este mensaje

Ejemplo:
    vso developer-program
```

## LIST TASKS

```md
Descripción: 
    Listar todas las tareas

Uso:
    vso list-tasks [opciones]

Opciones:
    --help/-h       mostrar este mensaje

Ejemplo:
    vso list-tasks
```

## ROTATE TASKS

```md
Descripción: 
    Rotar tareas

Uso:
    vso rotate-tasks [opciones]

Opciones:
    --help/-h       mostrar este mensaje

Ejemplo:
    vso rotate-tasks
```

## TRIGGER UPDATE

```md
Descripción: 
    Ejecutar una actualización del sistema

Uso:
    vso trigger-update [opciones]

Opciones:
    --help/-h       mostrar este mensaje
    --now           ejecutar una actualización inmediatamente

Ejemplo:
    vso trigger-update --now
```

## VEA TAMBIÉN

- [`apx`](/docs/apx)
- [`abroot`](/docs/vso)

## AUTOR

```md
@JMarcosHP
```

## REPORTE DE ERRORES

Reportar los errores al [rastreador de problemas](https://github.com/Vanilla-OS/ABRoot/issues).
