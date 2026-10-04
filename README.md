# Sistema de Biblioteca — Engenharia de Software I

Sistema de gerenciamento de biblioteca desenvolvido em **Java**, com foco em **orientação a objetos e padrões de projeto**.

## Objetivo

Aplicar conceitos de Engenharia de Software na construção de um sistema de biblioteca, utilizando padrões de projeto para organizar regras de negócio e responsabilidades.

## O que o projeto faz

A aplicação funciona via terminal e permite:

- Realizar empréstimos e devoluções.
- Criar reservas.
- Observar livros.
- Consultar livros e usuários.
- Consultar notificações.
- Controlar estados de usuários, exemplares e empréstimos.
- Aplicar regras diferentes de empréstimo para cada tipo de usuário.

Tipos de usuário presentes:

```text
Usuarios
├── AlunoGraduacao
├── AlunoPos
└── Professor
```

## Tecnologias

- **Java**
- Programação Orientada a Objetos
- `Timer` / `TimerTask`
- Padrões de projeto

## Arquitetura

A aplicação utiliza os seguintes padrões:

- **Singleton** — uma única instância da biblioteca.
- **Facade** — a `Biblioteca` centraliza operações do sistema.
- **Command** — cada ação do terminal é representada por um comando.
- **Strategy** — regras de empréstimo variam conforme o tipo de usuário.
- **State** — controla estados de usuários, exemplares e empréstimos.
- **Observer** — usuários podem observar livros e receber notificações.

Fluxo simplificado:

```text
Terminal
   │
   ▼
Invoker → Command → Biblioteca
                      │
              ┌───────┴───────┐
              ▼               ▼
           Usuários         Livros
              │               │
              └───────┬───────┘
                      ▼
                  Empréstimos
```

## Modelagem

As principais entidades do domínio são:

```text
Biblioteca
├── Usuários
├── Livros
├── Exemplares
├── Empréstimos
└── Reservas
```

Usuários possuem empréstimos e reservas; livros possuem exemplares; os estados controlam a disponibilidade e as condições de uso.

## Como clonar

```bash
git clone https://github.com/NickFernands/Projeto-EngSoft-I.git
cd Projeto-EngSoft-I
```

## Como executar

Pré-requisito: **JDK**.

Compile os arquivos:

```bash
javac *.java
```

Execute:

```bash
java Main
```

A aplicação será executada no terminal e aceitará comandos como:

```text
emp <usuario> <livro>
dev <usuario> <livro>
res <usuario> <livro>
obs <usuario> <livro>
liv <livro>
usu <usuario>
ntf <usuario>
sai
```

## Autor

**Nicholas Fernandes**
