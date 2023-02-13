---
title: Packaging - Vanilla OS
description: Descubra como instalar programas e bibliotecas para o Vanilla OS.
---

# "Packaging"

"Packaging" é o processo de criação de um "pacote" para um software ou uma biblioteca, de modo que ele possa ser instalado em uma distribuição linux. "Vanilla OS" tem um sistema de arquivos com uma raiz não convencional, o que requer que algumas considerações e diretrizes sejam seguidas.

## Quando empacotar?

Vanilla OS é uma distribuição transacional, o que significa que ele recebe atualizações através de transações. O processo é tratado pela [ABRoot](/docs/ABRoot), o que requer uma reinicialização para aplicar as mudanças. Isto significa que o usuário ierá que reiniciar o sistema após a instalação de um pacote, o que não é o ideal. Também a partição raiz é muito pequena, isto é intencional para evitar que o usuário instale muitos pacotes, o que poderia expor o sistema à vulnerabilidades de segurança e complicações durante as transações.

Por estas razões, é recomendável empacotar apenas software e bibliotecas essenciais. Para entender melhor o que é essencial, você pode verificar a tabela a seguir:

| Programa | Essencial | Motivo                                                                                                                                                                                                                                                    |
| -------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Chromium | Não        | É um navegador de internet, que não é essencial para o sistema e pode ser instalado através do [Apx](/docs/apx), [Flatpak](https://handbook.vanillaos.org/2022/12/09/install-flatpaks.html), [Snap](https://snapcraft.io/) ou [AppImage](https://appimage.org/).     |
| fuse     | Sim       | Este é um driver de dispositivo, que é essencial para que os AppImage funcionem, e também deve ser instalado fora do contêiner "Apx".                                                                                                                              |
| GIMP     | Não        | É um editor de image, que não é essencial para o sistema e pode ser instalado através do [Apx](/docs/apx), [Flatpak](https://handbook.vanillaos.org/2022/12/09/install-flatpaks.html), [Snap](https://snapcraft.io/) ou [AppImage](https://appimage.org/). |

## Diretrizes de empacotamento

Esta seção está organizada em várias subseções, cada uma descrevendo um aspecto diferente do processo de empacotamento.

### Naming

There are no restrictions on the name of the package, but it is recommended to
use the same name as the upstream project. I.e. if the upstream project is
called `foo`, the package should be called `foo`, and not `bar`. This is
important because it allows the user to easily identify the package.

### Versioning

The version of the package should be the same as the upstream version, with
minor changes if needed. For example, if the upstream version is `1.2.3`, the
package version should be `1.2.3`, and not `2.0.0`. If the package has some
minor changes, the version should be `1.2.3-1`, `1.2.3-2`, etc. The version
must never go backwards or forwards the upstream version.

### Storage

Some applications require a lot of storage, and this can be a problem for
Vanilla OS, which has a small root partition. If the application cannot be
installed in the Apx container or any other way, it is recommended to edit
its behavior to locate its data in the user's home directory or in the `/home`
partition, which has a lot more storage.

This is also a good practice, since it allows the user to easily backup the
data of the application, and also to easily remove the application without
losing the data.
