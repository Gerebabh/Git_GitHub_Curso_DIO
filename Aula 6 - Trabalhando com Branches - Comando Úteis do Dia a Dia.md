# :books: Aula 6 - Trabalhando com Branches - Comando Úteis do Dia a Dia

Caso precise consultar os comandos básicos do Git, clique [aqui](https://github.com/Gerebabh/Git_GitHub_Curso_DIO).

Definições do que é Branch Aula 1

### :computer: Temas da Aula

**Comandos úteis para o dia a dia.**

* `git fetch` - O comando `git fetch` é usado para baixar objetos e referências de outro repositório. Quando você executa `git fetch origin main`, você está buscando as informações da branch `main` do repositório remoto chamado `origin`. Isso permite que você compare as diferenças entre o repositório local e o remoto.

```bash
git fetch origin main
```

- `git` - Comando Git.
- `fetch` - Coleta informações do local determinado.
- `origin` - Repositório remoto chamado Origin.
- `main` - Branch chamada main.

***

* `git diff` - O comando `git diff` é usado para mostrar as diferenças entre commits, branches, arquivos e muito mais. Quando você executa `git diff main origin/main`, você está comparando a branch `main` local com a branch `main` do repositório remoto chamado `origin`. Isso mostrará as diferenças entre as duas branches.

```bash
git diff main origin/main
```

- `git` - Comando Git.
- `diff` - Comando para realizar comparação.
- `main` - Branch local que será comparada.
- `origin/main` - Determina a branch que será comparada, neste caso a branch `main` do repositório remoto chamado `origin`.

___

* `git merge` - O comando `git merge` é usado para mesclar alterações de uma branch em outra. Quando você executa `git merge origin/main`, você está mesclando as alterações da branch `main` do repositório remoto chamado `origin` na branch atual do seu repositório local.

```bash
git merge origin/main
```

- `git` - Comando Git.
- `merge` - Comando para mesclar branches.
- `origin/main` - Branch do repositório remoto chamado `origin` cujas alterações serão mescladas na branch atual.

___

**Como clonar uma Branch específica de um um repositório que contenha mais de uma.**

Como exemplo, o repositório remoto `origin` possui duas branches, sendo `main` e `teste`. Será clonada apenas a branch `teste`.

```bash
git clone [URL ou SSH] --branch teste --single-branch
```

O comando `git clone` é usado para criar uma cópia de um repositório remoto em seu computador local. Quando você executa `git clone [URL ou SSH] --branch teste --single-branch`, você está clonando apenas a branch `teste` do repositório remoto especificado pela URL ou SSH.

- `git` - Comando Git.
- `clone` - Comando para clonar as informações de um repositório especificado.
- `Endereço repositório remoto URL ou SSH` - Informe a URL ou SSH do repositório remoto.
- `--branch teste` - Informa que será clonada a branch com o nome `teste`. Caso não informe o nome da branch, todas serão clonadas.
- `--single-branch` - Determina que apenas a branch definida será clonada. Caso não seja utilizado este parâmetro, todas as branches serão clonadas.

