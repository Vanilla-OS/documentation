---
Título: Manual apx - Vanilla OS
Descripción: Manual para apx.
---

# Manual `apx`

## NOMBRE

```text
`apx` es el administrador de paquetes de Vanilla OS que es fácil de usar para instalar paquetes de múltiples fuentes dentro de contenedores sin la necesidad de alterar el sistema de archivos raíz.
```

## SINOPSIS

```text
apx [opciones] [comando] [argumentos]
```

## DESCRIPCIÓN

```markdown
apx is a wrapper around multiple package managers to install packages and run commands inside a managed container.
apx es un envoltorio alrededor de múltiples administradores de paquetes para realizar la instalación de paquetes y ejecutar comandos dentro de un contenedor.

Uso:
    apx [opciones] [comando] [argumentos]

Opciones:
    -h, --help      Muestra este mensaje
    -v, --version   Muestra la versión
    --aur           Instala paquetes desde el repositorio AUR
    --dnf           Instala paquetes desde los repositorios de Fedora Linux

Commands:
    autoremove      Elimina todos los paquetes no utilizados
    clean           Limpia la caché de apx
    enter           Entra al shell del contenedor
    export          Exporta/Recrea el acceso directo de un programa del contenedor
    help            Muestra este mensaje
    init            Inicializa un contenedor
    install         Instala paquetes dentro del contenedor
    list            Lista todos los paquetes instalados
    log             Muestra los registros
    purge           Purga los paquetes del contenedor
    run             Ejecuta un comando dentro del contenedor
    remove          Elimina paquetes del contenedor
    search          Buscar paquetes
    show            Muestra los detalles de un paquete
    unexport        Elimina el acceso directo de un programa
    update          Actualiza los repositorios de paquetes disponibles
    upgrade         Actualiza todo el sistema instalando/actualizado los paquetes disponibles
```

## AUTOREMOVE (autoremover)

```markdown
Descripción: 
    Elimina todos los paquetes no utilizados.
Uso:
    apx autoremove [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Uso:
    apx autoremove
```

## CLEAN (limpiar)

```markdown
Descrición: 
    Limpia la caché de apx.

Uso:
    apx clean [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx clean
```

## ENTER (entrar)

```markdown
Descripción: 
    Entra al shell del contenedor.

Uso:
    apx enter [opciones]

Opciones:
    -h, --help            Muestra este mensaje
```

## EXPORT (exportar)

```markdown
Descripción: 
    Exporta/Recrea el acceso directo de un programa del contenedor.

Uso:
    apx export <programa> [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx export htop
```

## INIT (inicializar)

```markdown
Descripción: 
    Inicializa un contenedor.

Uso:
    apx init [opciones]

Opciones:
    -h, --help            Muestra este mensaje
```

## INSTALL (instalar)

```markdown
Descripción: 
    Instala paquetes dentro del contenedor.

Uso:
    apx install [opciones] <paquetes>

Opciones:
    -h, --help            Muestra este mensaje
    -y, --assume-yes      Proceder sin confirmación manual.
    -f, --fix-broken      Reparar dependencias rotas antes de instalar.
    --no-export           No exportar acceso directo después de instalar.
    --sideload [ruta]     Instalar un paquete desde un archivo local.

Ejemplos:
    apx install htop git
    apx install --sideload /path/to/file.deb
```

## LIST (listar)

```markdown
Descripción: 
    Lista todos los paquetes instalados.

Uso:
    apx list [opciones]

Opciones:
    -h, --help            Muestra este mensaje
```

## LOG (registro/bitácora)

```markdown
Descripción: 
    Muestra los registros.

Uso:
    apx log [opciones]

Opciones:
    -h, --help            Muestra este mensaje
```

## PURGE (purgar)

```markdown
Descripción: 
    Purga los paquetes del contenedor.

Uso:
    apx purge <paquetes> [opciones]

Opciones:
    -h, --help            Show this help message and exit

Ejemplos:
    apx purge htop
```

## RUN (correr/ejecutar)

```markdown
Descripción: 
    Ejecuta un comando dentro del contenedor.

Uso:
    apx run <programa> [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx run htop
```

## REMOVE (remover)

```markdown
Descripción:
    Elimina paquetes del contenedor.

Uso:
    apx remove <paquetes> [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx remove htop
```

## SEARCH (buscar)

```markdown
Descripción: 
    Buscar paquetes.

Uso
    apx search <paquetes> [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx search htop
```

## SHOW (mostrar)

```markdown
Descripción: 
    Muestra los detalles de un paquete.

Uso:
    apx show <paquete> [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx show htop
```

## UNEXPORT (des-exportar)

```markdown
Descripción:
    Elimina el acceso directo de un programa.

Uso:
    apx unexport <programa> [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx unexport htop
```

## UPDATE (actualizar)

```markdown
Descripción: 
    Actualiza los repositorios de paquetes disponibles.

Uso:
    apx update [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx update
```

## UPGRADE (mejorar)

```markdown
Descripción: 
    Actualiza todo el sistema instalando/actualizado los paquetes disponibles.

Uso:
    apx upgrade [opciones]

Opciones:
    -h, --help            Muestra este mensaje

Ejemplo:
    apx upgrade
```

## VERSION

```markdown
Descripción:
    Muestra la versión.

Uso:
    apx --version
    apx -v
```

## VEA TAMBIÉN

- [`abroot`](/docs/ABRoot)
- [`vso`](/docs/vso)

## AUTOR

```text
@JMarcosHP
```

## REPORTE DE ERRORES

Reportar los errores al [rastreador de problemas](https://github.com/Vanilla-OS/ABRoot/issues).
