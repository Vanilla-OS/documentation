---
Title: Packaging - Vanilla OS
Description: Descubra como instalar programas e bibliotecas para o Vanilla OS.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

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

### Nomeando

Não há restrições quanto ao nome de um pacote, mas é recomendável usar o mesmo nome que o projeto original. Isto é, se o projeto original for
chamado `foo`, o pacote deve ser chamado `foo`, e não `bar`. Isto é importante porque permite que o usuário identifique facilmente o pacote.

### Versionamento

A versão do pacote deve ser a mesma que a versão original, com apenas pequenas mudanças se necessário. Por exemplo, se a versão original for `1.2.3`, a versão do pacote deve ser `1.2.3`, e não `2.0.0`. Se o pacote tiver algumas pequenas alterações, a versão deve ser `1.2.3-1`, `1.2.3-2`, etc. A versão nunca deve retroceder ou avançar a versão original.

### Armazenamento

Algumas aplicações requerem muito espaço de armazenamento, e isto pode ser um problema para Vanilla OS, que tem uma pequena partição raiz. Se a aplicação não puder ser instalada no contêiner Apx ou de outra forma, é recomendável editar seu comportamento para localizar seus dados no diretório pessoal do usuário ou na partição `/home`, que possui muito mais espaço de armazenamento.

Esta também é uma boa prática, pois permite ao usuário fazer facilmente o backup dos dados da aplicação, e também remover facilmente a aplicação sem perda de dados.
