# :books: Aula 4 - Enviando e Baixando Alterações com o Repositório Remoto

Caso precise consultar os comandos básicos do Git, clique [aqui]([Git_GitHub_Curso_DIO/Aula 0 - Estrutura Git - Comandos Básicos.md at main · Gerebabh/Git_GitHub_Curso_DIO](https://github.com/Gerebabh/Git_GitHub_Curso_DIO/blob/main/Aula 0 - Estrutura Git - Comandos Básicos.md)).

Depois de organizar o repositório local e ter arquivos já commitados prontos para serem enviados (pushed) para o repositório remoto, os passos a seguir serão descritos abaixo.

### :computer: Temas da Aula

- **Configuração da Branch Main / Master**. Veja instruções da Aula 1
- **Conectar o repositório local ao repositório remoto, como exemplo o GitHub**.

Crie ou acesse o repositório remoto do GitHub e no botão de seleção “CODE” copie o endereço HTTPS ou, caso já tenha uma chave SSH configurada, selecione a opção SSH e copie o endereço.

Retorne ao terminal do Git e faça o seguinte comando para conectar os repositórios local e remoto:

```
git remote add origin (Cole aqui a URL ou SSH)
```

Para confirmar se foi conectado corretamente, digite:

```
git remote -v
```

O terminal retornará as informações de conexão dos repositórios.

- **Enviando arquivos do repositório local para o remoto**

Para enviar os arquivos já preparados do repositório local para o remoto, podemos utilizar o comando:

```
git push -u origin main
```

`git push` - Comando para envio

`-u` seguido pelo `main` - “Set up-stream” Configura no Git a Branch `main` do repositório local como branch up-stream. O que facilitará para realizar os próximos envios de arquivos sendo necessário informar apenas o comando `git push`.

- **Edição de arquivos**

A edição dos arquivos pode ser feita no repositório local ou remoto.

**Edição direta no arquivo** - No GitHub, selecione o arquivo `README.md` e clique no lápis para entrar no modo edição. Ao lado do botão `Edit`, é exibido o botão `Preview`, que permite ver as alterações realizadas no modo de exibição. Após concluir as alterações, clique em `Commit changes...` e será exibida uma nova janela.

Nesta janela, informe a mensagem referente ao commit e, se julgar necessário, pode ser incluída uma descrição adicional que é opcional. Finalize clicando em `Commit changes`.

**Edição pelo Editor do GitHub** - Como requisito para acessar o editor, você deve estar logado no GitHub e selecionado o repositório que deseja editar. Após isso, pressione `.` (PONTO) no teclado. O Editor é o VSCode versão online.

Selecione o arquivo que será editado para acessar a aba de edição.

Na aba de edição, você tem a opção de clicar no ícone de pré-visualização ou pressionar `ctrl+k v` para abrir esta aba ao lado da de edição.

Após realizar as alterações, clique no ícone `Controle de código fonte` e, através desta tela, você poderá enviar a atualização do arquivo editado. Basta preencher a mensagem do commit e clicar em `Commit & Push`.

Para sair do Editor VSCode, clique em :arrow_backward: voltar do navegador.

- **Atualizando repositório local com alterações realizadas no repositório remoto**

No terminal do Git, no diretório da pasta referente ao repositório local, faça o seguinte comando:

```
git pull
```

Este comando puxará as alterações do repositório remoto mesclando com os arquivos existentes no repositório local.