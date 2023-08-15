# :books:Trabalhando com Branches - Criando, Mesclando, Deletando e Tratando Conflitos

Caso precise consultar os comandos básicos do Git, clique [aqui](./5%20-%20Estrutura%20Git%20-%20Comandos%20Básicos.md).

Definições do que é Branch Aula 1

### :computer: Temas da Aula

**Definições de Branch**.

Uma branch (ou ramo, em português) é uma linha independente de desenvolvimento dentro de um repositório Git. Ele permite que você crie uma cópia do código e faça alterações nele sem afetar o branch principal ou outros branches.  

Imagine que você está trabalhando em um projeto com uma equipe de desenvolvedores. O código do projeto está armazenado em um repositório Git com um branch principal chamado **`main`**. Esse branch contém a versão estável e testada do código, que está pronta para ser lançada para os usuários.

Agora, imagine que você deseja adicionar um novo recurso ao projeto. Em vez de fazer alterações diretamente no branch **`main`**, você pode criar um novo branch a partir dele, chamado **`new-feature`**. Esse branch será uma cópia exata do branch `main` no momento em que foi criado.

Você pode então mudar para o branch **`new-feature`** e começar a fazer alterações no código para adicionar o novo recurso. Enquanto isso, outros desenvolvedores podem continuar trabalhando no branch **`main`** ou em seus próprios branches, sem serem afetados pelas alterações que você está fazendo. 

Quando o novo recurso estiver pronto e testado, você pode mesclar as alterações do branch **`new-feature`** de volta ao branch **`main`**. Isso adicionará o novo recurso ao código principal do projeto, sem afetar o histórico de commits ou causar conflitos com o trabalho de outros desenvolvedores.

Os branches são uma ferramenta poderosa que permite que várias pessoas trabalhem em um projeto simultaneamente, sem interferir umas nas outras. Eles também facilitam o gerenciamento de versões e o teste de novos recursos antes de adicioná-los ao código principal. É uma boa prática usar branches sempre que estiver trabalhando em um projeto com outras pessoas ou quando estiver fazendo alterações significativas no código.

##### Branch MASTER ou MAIN?

Anteriormente, o nome padrão do branch principal no Git era **`master`**, mas recentemente muitas ferramentas e serviços, incluindo o GitHub, mudaram para usar **`main`** como o nome padrão. Se você estiver usando uma versão mais antiga do Git ou se já tiver um repositório local com um branch principal chamado **`master`**, pode usar o comando **`git branch -M main`** para renomeá-lo para **`main`** antes de fazer push das alterações para o repositório remoto no GitHub. Ressaltando que isso no caso de um repositório criado anteriormente e a branch está nomeada como **`master`.** Para facilitar caso o padrão do seu Git seja master pode utilizar o comando abaixo para configurar de forma global o seu GitBash. Após isso todas as branches criadas terão como padrão **`main`**.

```bash
git config --global init.defaultBranch main
```

___

**Trabalhando com Branches**

Fazendo uma analogia ao universo dos HQs, uma branch é como se fosse um universo e, ao criar uma nova branch, esta seria um universo paralelo, ou seja, tem as mesmas características, porém segue ramificações distintas. Isso permite que você faça alterações em cada uma delas sem afetar as demais.

É como se fossem vários programadores trabalhando no mesmo projeto sem alterar o projeto do outro. Desta forma, a branch principal não precisa ser alterada no momento do desenvolvimento ou edições do código.

Ao trabalhar com branches, é importante lembrar que a branch principal (geralmente chamada de `main` ou `master`) não precisa ser alterada durante o desenvolvimento ou edição do código. Em vez disso, você pode criar uma nova branch para fazer suas alterações e, depois, mesclar essa branch com a principal quando estiver pronto para integrar suas alterações ao projeto.

Desta forma, após alterar ou criar novos códigos em uma branch paralela, basta mesclá-la com a principal.

> **Dicas adicionais para trabalhar com Branches**
>
> - Dê nomes significativos às suas branches para que você possa facilmente identificar o que elas representam.
> - Use branches para trabalhar em diferentes ideias ou tarefas. Isso permitirá que você experimente e explore diferentes opções sem afetar o projeto principal.
> - Quando estiver satisfeito com as alterações que fez em uma branch, mexa-a na branch principal. Isso combinará as alterações da branch com a branch principal e atualizará o projeto principal.
> - Use branches para gerenciar conflitos. Se você fizer alterações em uma branch que também foram feitas na branch principal, poderá usar o comando `git merge` para combinar as alterações e resolver quaisquer conflitos.

___

**Consultando Branches**

Para consultar branches existentes podem ser utilizados os exemplos abaixo:

```bash
git branch
```

Por exemplo, se você estiver na branch `main` e tiver duas branches adicionais, `teste` e `desenvolvimento`, o comando `git branch` exibirá a seguinte saída:

```bash
* main # A Branch que estiver selecionada será destacada por um *
  teste
  desenvolvimento
```

Outro comando para consultar branches e seus respectivos commits é:

```bash
git branch -v
```

O resultado será similar a:

```bash
* main        15cef9b [ahead 3] Commit 2 - Main
  teste       319467f Commit 3 - teste
```

Nesta visualização, a primeira coluna representa o nome das branches, a segunda coluna é o ID do commit mais recente em cada branch e a terceira coluna é a descrição do commit correspondente.

___

**Criando e alternando entre Branches**

Para criar uma nova branch e alternar de `main`, devemos utilizar o seguinte comando:

```Bash
git checkout -b teste
```

Detalhamento do comando:

- `git` é o comando para o Git.
- `checkout` é o comando para alternar para uma branch.
- `-b` é a opção para criar uma nova branch.
- `teste` é o nome da nova branch.

Para alternar entre branches devemos utilizar o seguinte comando:

```bash
git checkout Main
```

Detalhamento do comando:

- `git` é o comando para o Git.
- `checkout` é o comando para alternar para uma branch.
- `Main` nome da Branch que será direcionado.

---

**Mesclando Branches**

Com arquivos criados nas branches `Main` e `teste`, podemos mesclar o que está na `teste` para `Main`. Para isso, é necessário que você esteja na branch `Main` e execute o seguinte código:

```bash
git merge teste	
```

Detalhamento do comando:

- `git` é o comando para o Git.
- `merge` mescla os arquivos.
- `teste` Nome da Branch que os arquivos serão buscados para mescla.

Após a mescla das branches, os arquivos que estavam na linha paralela `teste` foram movidos/mesclados com os da branch `main`.

---

**Excluindo Branches**

Não sendo mais necessário a utilização de uma branch “paralela”, a mesma poderá ser excluída através do comando:

```Bash
git branch -d teste
```

Detalhamento do comando:

- `git` é o comando para o Git.
- `branch` informa que o objeto a ser trabalhado são as branches.
- `-d` Comando para deletar uma branch.
- `teste` Nome da branch que será excluída.

---

**Tratamento de conflitos `merge`**

Supondo que duas pessoas estão trabalhando no mesmo arquivo (README.md), porém em repositórios diferentes, a primeira pessoa no local e a segunda no remoto.

A segunda pessoa realizou uma alteração na segunda linha do arquivo e salvou no repositório remoto.

A primeira pessoa editou a mesma segunda linha do mesmo arquivo no repositório local e, ao enviar para o repositório remoto, não foi permitido pelo fato da versão do arquivo que está lá já possuir uma alteração no mesmo local alterado.

Será necessário realizar o comando `git pull` para puxar os arquivos alterados do repositório remoto para o local. Após este procedimento, é necessário abrir o arquivo conflitado e lá estarão apresentadas devidamente os trechos em conflito.

Para solucionar o problema, o usuário deverá fazer a alteração mantendo o que julgar necessário. Após este procedimento, será possível realizar novo commit e envio do arquivo para repositório remoto já com a versão mais nova das alterações.

> **Procedimento para replicar esse conflito:**
>
> 1 - Crie um arquivo TESTECONFLITO.md no repositório local.
>
> 2 - Dentro do arquivo, informe um título e uma breve descrição.
>
> 3 - Envie este arquivo para o repositório remoto.
>
> 4 - No repositório remoto (GitHub), faça uma alteração na descrição do arquivo.
>
> 5 - Faça o commit no repositório remoto.
>
> 6 - Volte ao repositório local e faça uma alteração na mesma descrição do arquivo.
>
> 7 - Tente realizar o envio `push` do arquivo para repositório remoto. Que rejeitará o arquivo pelas informações divergentes do arquivo.
>
> 8 - Execute o comando `push` para buscar o arquivo do repositório remoto.
>
> 9 - Abra o arquivo no repositório local e será exibido as alterações feitas no repositório local e no remoto. Desta forma, permite que usuário faça o tratamento e salve o arquivo para novo envio.
>
> 10 - Envie o arquivo para repositório local.

Desta forma, é possível entender o processo para tratamento de conflitos.