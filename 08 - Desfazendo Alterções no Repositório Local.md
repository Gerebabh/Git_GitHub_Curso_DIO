# :books: Desfazendo Alterações no Repositório Local

Caso precise consultar os comandos básicos do Git, clique  [aqui](./05%20-%20Estrutura%20Git%20-%20Comandos%20Básicos.md).

### :computer: Temas da Aula

- **Remoção de um repositório GIT**

Quando um repositório é criado em uma pasta específica, um arquivo chamado `.git` é criado na raiz do projeto. Existem duas formas de remover o repositório:

1. **Remoção manual**:

   Para remover o repositório manualmente, você pode deletar a pasta oculta `.git` dentro do diretório em questão. Porém, é importante observar que essa pasta é oculta, e não será exibida caso seu sistema não esteja configurado para exibir itens ocultos.

2. **Remoção via terminal do GIT**:

   Para remover o repositório via terminal, execute o seguinte comando dentro do diretório onde o repositório foi iniciado:

   ```bash
   rm -rf .git
   ```

   Esse comando remove recursivamente o diretório `.git` e todos os seus subdiretórios, desfazendo o controle de versão do Git no projeto.

**Nota**: Certifique-se de fazer backup de quaisquer alterações importantes antes de remover o repositório.

Lembre-se de utilizar essas opções com cuidado para evitar perda de dados não intencional.

- **Restaurar um arquivo alterado indevidamente no repositório local**

  Se você acidentalmente apagar ou modificar o conteúdo de um arquivo, você pode usar o comando `git restore` para restaurar o arquivo para a última versão que foi salva no repositório.

  Para restaurar um arquivo, use o seguinte comando:

  ```bash
  git restore <file>
  ```

  Por exemplo, o comando a seguir restaurará o arquivo `README.md` para a última versão que foi salva no repositório:

  ```bash
  git restore README.md
  ```

  Você também pode usar o comando `git restore` para restaurar um arquivo para uma versão específica. Para fazer isso, use o seguinte comando:

  ```bash
  git restore --staged <file>
  ```

  Por exemplo, o comando a seguir restaurará o arquivo `README.md` para a versão que está atualmente no índice:

  ```bash
  git restore --staged README.md
  ```

  Você também pode usar o comando `git restore` para restaurar um arquivo para uma versão específica no histórico. Para fazer isso, use o seguinte comando:

  ```bash
  git restore --source <commit> <file>
  ```

  Por exemplo, o comando a seguir restaurará o arquivo `README.md` para a versão anterior ao último commit:

  ```bash
  git restore --source HEAD^ README.md
  ```

  O comando `git restore` é uma ferramenta poderosa que pode ser usada para restaurar arquivos que foram acidentalmente alterados ou removidos.

- **Alterando a descrição de um commit**

Se você já fez um commit e quer alterar a descrição dele, pode usar os seguintes comandos:

- Para alterar a descrição diretamente no terminal, use este comando:

```bash
git commit --amend -m "nova descrição"
```

- Para alterar a descrição usando o editor do Git Bash, use este comando:

```bash
git commit --amend
```

Para editar a descrição no editor do Git Bash, pressione `i`. Quando terminar de editar, pressione `ESC`, depois digite `:wq` e pressione `Enter`.

- **Restaurar versões anteriores de commits**

O comando `git reset` possui três opções: `--soft`, `--mixed` e `--hard`. Cada uma dessas opções afeta o repositório de maneiras diferentes.

- `--soft`: Essa opção move o ponteiro do branch atual (HEAD) para o commit especificado, mas mantém as alterações no índice (staged). Isso significa que as alterações ainda estão prontas para serem confirmadas (committed) na próxima vez que você executar o comando `git commit`.
- `--mixed`: Essa é a opção padrão do comando `git reset`. Ela move o ponteiro do branch atual (HEAD) para o commit especificado e também atualiza o índice para corresponder ao conteúdo do commit especificado. No entanto, as alterações no diretório de trabalho (working directory) são mantidas. Isso significa que as alterações ainda estão presentes nos arquivos, mas não estão mais prontas para serem confirmadas (unstaged).
- `--hard`: Essa opção move o ponteiro do branch atual (HEAD) para o commit especificado, atualiza o índice para corresponder ao conteúdo do commit especificado e também atualiza o diretório de trabalho para corresponder ao conteúdo do commit especificado. Isso significa que todas as alterações no índice e no diretório de trabalho são descartadas e o repositório é restaurado para o estado do commit especificado.

**Nota**: É importante ter cuidado ao usar a opção `--hard`, pois ela pode resultar em perda de dados não intencional. Certifique-se de fazer backup de quaisquer alterações importantes antes de usar essa opção.

Além disso, você também pode usar os comandos `git restore` e `git reset` para restaurar versões anteriores de arquivos individuais. Aqui está um exemplo de como você pode fazer isso:

Suponha que você tenha criado dois arquivos, `dir_teste/aula-01.md` e `dir_teste/aula-02.md`, e os adicionou ao índice (staged) usando o comando `git add`. Agora, você deseja retirar um dos arquivos do índice (unstage) e restaurar o outro para a versão anterior.

Para retirar o arquivo `dir_teste/aula-01.md` do índice (unstage), você pode usar o comando `git restore --staged dir_teste/aula-01.md`. Isso removerá o arquivo do índice, mas manterá as alterações no diretório de trabalho (working directory).

Para restaurar o arquivo `dir_teste/aula-02.md` para a versão anterior, você pode usar o comando `git restore dir_teste/aula-02.md`. Isso atualizará o arquivo no diretório de trabalho para corresponder ao conteúdo do commit atual (HEAD).

Alternativamente, você também pode usar o comando `git reset` para retirar um arquivo do índice (unstage). Para fazer isso, você pode usar o comando `git reset dir_teste/aula-01.md`. Isso removerá o arquivo do índice, mas manterá as alterações no diretório de trabalho.