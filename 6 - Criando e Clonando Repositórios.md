# :books: Criando e Clonando Repositórios 

Informações básicas para a criação de um repositório local e a clonagem de um repositório remoto.

**Navegando entre diretórios através do terminal Git**

Para criar um diretório destinado a ser o repositório local, você pode utilizar o explorador de arquivos do seu computador ou o terminal do Git.

- Para criar uma pasta pelo terminal, navegue até o caminho desejado (por exemplo, `c:\user\teste`) e clique com o botão direito do mouse, selecionando "Abrir Git Bash aqui". No terminal, utilize os seguintes comandos:

  ```bash
  c:\user\teste
  mkdir meu_repo_local  # mkdir [nome do diretório] - Criará um novo diretório chamado "meu_repo_local"
  ```

- Para acessar pastas e subpastas, utilize o comando `cd [nome do diretório]` e para voltar um nível, use `cd ..`:

  ```bash
  c:\user\teste # Diretório inicial
  cd meu_repo_local # Acessando a subpasta. Dica: Digite a primeira letra e pressione TAB para autocompletar.
  C:\user\teste\meu_repo_local  # Diretório de destino.
  ```

- Para ver o conteúdo de um diretório, execute o seguinte comando:

  ```bash
  ls
  ```

**Criação de Repositório Local**

Existem algumas formas de criar um repositório local:

- Primeira: Através do terminal, selecione o diretório onde você deseja iniciar o repositório local e execute o comando:

  ```bash
  git init
  ```

- Segunda: Clonando um repositório remoto.

Através do comando `git clone` seguido da URL ou SSH, você criará um clone de um repositório remoto existente, criando um novo repositório local em seu computador. Ao realizar o clone, um novo diretório com o nome do repositório remoto e seus arquivos será criado.

```bash
git clone [url ou ssh do repositório]
```

Caso você queira clonar um repositório com um nome diferente, basta incluir um nome após o endereço do repositório no comando Git.

```bash
git clone [url ou ssh do repositório] [nome novo diretório]
```

Para essas opções de clone, pode ser necessário informar as credenciais de acesso ao Git para iniciar o processo.

* Para confirmar se um diretório já está configurado como repositório local, basta executar o comando:

```bash
git status
```

**Associando um repositório local um remoto**

Para testar esta forma, selecione um novo diretório para ser o repositório local e no terminal Git faça a inicialização de um novo repositório através do  `git init`. Desta você pode associar este repositório local a um remoto sem utilizar o método clone. 

```bash
git remote add origin "URL ou SSH"
```

Repare que diferente do `git clone` você associou um repositório remoto ao local, porém não buscou nenhum arquivo remoto. 

**Consultando repositórios remotos associados ao repositório local**

Após realizar um clone, você pode realizar o comando `git remote` para verificar o repositório remoto que está associado ao local.

```bash
git remote -v
```

Caso conectado ele apresentará o endereço do repositório remoto que de forma convencionada é chamado `origin`. Caso realize este comando em um diretório que não está associado a um repositório remoto não trará nenhum resultado na consulta.

Para conhecer mais comandos básicos do Git, clique [aqui](./Aula%200%20-%20Estrutura%20Git%20-%20Comandos%20Básicos.md).

