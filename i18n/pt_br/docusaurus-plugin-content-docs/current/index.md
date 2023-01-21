---

title: Documentação do Vanilla OS

description: Descubra como usar o Vanilla OS e todas as suas ferramentas e configurações.

sidebar_position: 1

---

# Vanilla OS

Sinta a experiência GNOME Vanilla no Ubuntu com um pouco de tempero.

**Esta página é a documentação oficial dos componentes do Vanilla OS.**<br />

Confira o  [**Manual**](https://handbook.vanillaos.org) para guias e tutoriais escritos pelo usuário.

## FAQ

Respostas às perguntas mais frequentes sobre o Vanilla OS.

- **Por que uma nova Distribuição?**<br />

  O Vanilla OS surgiu da necessidade de uma distribuição Linux baseada no Ubuntu que

  forneceria o GNOME vanilla sem nenhuma alteração para a experiência do usuário. Mais tarde, seu escopo foi estendido para experimentar algumas ferramentas e tecnologias, como ABRoot e Apx (o subsistema baseado em Distrobox).

  

- **Ele usa OSTree?**<br />

  Não. O Vanilla OS alcança a imutabilidade por meio de [`ABRoot`](https://github.com/Vanilla-OS/ABRoot) [anteriormente alcançado através do utilitário `almost`]. O uso de OSTree pode ser considerado no futuro.

 

  Escrevemos o utilitário "almost" para imutabilidade sob demanda com base no

   atributo de imutabilidade dos arquivos. Essa abordagem funcionou em qualquer partição

   esquema/sistema de arquivos.

  

  Introduzimos um novo utilitário [ABRoot](https://github.com/Vanilla-OS/ABRoot) substituindo o `almost` utilitário para fornecer total imutabilidade e atomicidade, transacionando entre 2 partições raiz (A⟺B). Ele também permite transações sob demanda por meio de um shell transacional.

  

- **Lançamento contínuo/Rolling Release?**<br />

  Não. O Vanilla OS é de lançamento pontual e segue o ciclo de lançamento do Ubuntu.

## Guia do usuário

- **[Instalação](https://handbook.vanillaos.org/2022/11/05/installation.html)**

- **[Primeira configuração](https://handbook.vanillaos.org/2022/11/18/first-setup.html)**

- **[Atualizações](https://handbook.vanillaos.org/2022/12/10/updates.html)**

- **[Mais guias](https://handbook.vanillaos.org/)**

## Documentação dos componentes principais

- **[Apx](/apx/)**<br />

  é um gerenciador de pacotes baseado em contêiner que permite a instalação de pacotes de outras distribuições em um ambiente de sandbox.

- **[ABRoot](/abroot)**<br />

  é um utilitário que permite transações totalmente atômicas entre 2 partições raiz (A⟺B).

- **[VSO](/vso)**<br />

  é um utilitário que permite executar tarefas de manutenção na instalação do Vanilla OS.

- ~~**[Almost](/almost)**~~<br />

  ~~permite que você torne seu sistema imutável simplesmente alternando o atributo i dos arquivos.~~

## Contribuindo

- **[Packaging](/packaging)**<br />

  programas para o Vanilla OS requerem algumas considerações e diretrizes a serem seguidas.
