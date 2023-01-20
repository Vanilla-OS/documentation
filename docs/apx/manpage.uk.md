---
title: APX - Manpage - Vanilla OS
Опис: Manpage для менеджера пакунків apx.
---

# Manpage: `apx`

## Найменування

```text
apx - простий у використанні менеджер пакунків Vanilla OS з підтримкою встановлення пакунків з декількох джерел
всередині контейнерів без зміни кореневої файлової системи.
```

## Короткий опис

```text
apx [параметри] [команда] [аргументи]
```

## Опис

```markdown
apx - це обгортка для декількох менеджерів пакунків для встановлення пакунків та запуску команд всередині керованого контейнера.

Використання:
    apx [параметри] [команда] [аргументи]

Параметри:
    -h, --help      Показати це повідомлення і вийти
    -v, --version   Показати версію і вийти
    --aur           Встановити пакунки з репозиторію AUR
    --dnf           Встановити пакунки з репозиторію Fedora

Команди:
    autoremove      Видалити всі невикористовувані пакунки
    clean           Очистити кеш менеджера пакунків apx
    enter           Увійти у оболонку контейнера
    export          Експортувати/відновити запис програми на робочому столі з контейнера
    help            Показати це повідомлення і вийти
    init            Ініціалізувати керований контейнер
    install         Встановити пакунки до контейнера
    list            Перерахувати встановлені пакунки
    log             Показати журнали
    purge           Видалити пакунки з контейнера (з видаленням конфігурації)
    run             Запустити команду всередині контейнера
    remove          Вилучити пакунки з контейнера
    search          Пошук пакунків
    show            Показати детальну інформацію про пакунок
    unexport        Видалити запис програми на робочому столі
    update          Оновити список доступних пакунків
    upgrade         Оновити систему шляхом встановлення/оновлення доступних пакунків
```

## `autoremove`

```markdown
Опис: 
    Видалити всі невикористовувані пакунки.
Використання:
    apx autoremove [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx autoremove
```

## `clean`

```markdown
Опис: 
    Очистити кеш менеджера пакунків apx.

Використання:
    apx clean [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx clean
```

## `enter`

```markdown
Опис: 
    Увійти у оболонку контейнера.

Використання:
    apx enter [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти
```

## `export`

```markdown
Опис: 
    Export/Recreate a program's desktop entry from a managed container.

Використання:
    apx export <program> [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx export htop
```

## `init`

```markdown
Опис: 
    Initialize the managed container.

Використання:
    apx init [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти
```

## `install`

```markdown
Опис: 
    Install packages inside a managed container.

Використання:
    apx install [options] <packages>

Параметри:
    -h, --help            Показати це повідомлення і вийти
    -y, --assume-yes      Proceed without manual confirmation.
    -f, --fix-broken      Fix broken deps before installing
    --no-export           Do not export a desktop entry after the installation. 
    --sideload [path]     Install a package from a local file.

Приклади:
    apx install htop git
    apx install --sideload /path/to/file.deb
```

## `list`

```markdown
Опис: 
    List installed packages.

Використання:
    apx list [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти
```

## `purge`

```markdown
Опис: 
    Purge packages inside a managed container.

Використання:
    apx purge <packages> [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx purge htop
```

## `remove`

```markdown
Опис:
    Remove packages inside a managed container.

Використання:
    apx remove <packages> [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx remove htop
```

## `run`

```markdown
Опис: 
    Run a program inside a managed container.

Використання:
    apx run <program> [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx run htop
```

## `search`

```markdown
Опис: 
    Search for packages in a managed container.

Використання:
    apx search <packages> [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx search htop
```

## `show`

```markdown
Опис: 
    Show details about a package.

Використання:
    apx show <package> [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx show htop
```

## `unexport`

```markdown
Опис:
    Unexport/Remove a program's desktop entry from a managed container.

Використання:
    apx unexport <program> [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx unexport htop
```

## `update`

```markdown
Опис: 
    Update the list of available packages.

Використання:
    apx update [options]

Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx update
```

## `upgrade`

```markdown
Опис: 
    Upgrade the system by installing/upgrading available packages.

Використання:
    apx upgrade [options]
  
Параметри:
    -h, --help            Показати це повідомлення і вийти

Приклади:
    apx upgrade
```

## `version`

```markdown
Опис:
    Display the version number of apx.

Використання:
    apx --version
    apx -v
```

## Дивіться також

- [`abroot`](/docs/ABRoot/index.uk)
- [`vso`](/docs/vso/index.uk)

## Автори

```text
Спільнота Vanilla OS
Переклад: Сапуцький Петро (@voxelin)
```

## Повідомлення про помилки

Повідомляйте про баги на [трекері помилок](https://github.com/Vanilla-OS/apx/issues).
