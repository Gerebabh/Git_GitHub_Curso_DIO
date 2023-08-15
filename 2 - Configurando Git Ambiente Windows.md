# Configuração Inicial do Ambiente Git no Windows

Este guia irá ajudá-lo a configurar o Git em seu ambiente para que você possa começar a utilizar essa poderosa ferramenta de controle de versão.

## Passo a Passo

1. **Crie uma Pasta para Seu Repositório Local**:

   - Antes de começar, crie uma pasta em seu computador onde você deseja manter seus repositórios locais. Por exemplo, nomeie a pasta como `Repositorio_Local`.

2. **Acesse o Git Bash**:

   - Navegue até a pasta `Repositorio_Local` que você criou.
   - Clique com o botão direito do mouse na pasta.
   - Selecione a opção `Git Bash Here`.
   - O terminal do Git será aberto em uma janela.

   Na janela aberta, você verá algo como:

   ```css
   [Nome do computador][MINGw64(nome do compilador)][Endereço ao qual o terminal está apontando]
   ```

3. **Sintaxe de Comando - Git**

   Como exemplo será utilizado o comando para configurar de forma global o usuário para todos os repositórios Git.

   ```bash
   git config --global user.name "nome do usuário"
   ```

   Aqui está o detalhamento do comando:

   - `git`: Comando Git padrão para várias operações.

   - `config`: Usado para configurações do Git.

   - `--`: É um indicador de que o que vem a seguir é uma opção.

   - `global`: Define configurações para todos os repositórios Git.

   - `user.name`: Parâmetro a ser configurado (nome do usuário).

   - `"nome do usuário"`: Nome do usuário a ser definido.

     ```bash
     git config --global user.email "email do usuário"  # Define de forma global o email do usuário.
     git config --global init.defaultBranch main  # Configura para que todo novo repositório a ser criado a branch padrão será nomeada como main.
     ```

     Maiores detalhes sobre Branches podem ser encontrados [aqui.](./Aula%205%20-%20Trabalhando%20com%20Branches%20-%20Criando%2C%20Mesclando%2C%20Deletando%20e%20Tratando%20Conflitos.md)

     Utilize estes comando para definir estas configurações no Git.

     

4. **Verifique Suas Configurações Globais e Individuais**:

   - Para visualizar suas configurações globais, utilize o seguinte comando:

     ```bash
     git config --global --list
     ```

     Isso exibirá informações como seu e-mail, nome de usuário e configurações padrão.

     Exemplo de saída:

     ```bash
     user.email=email@dominio.com
     user.name=usuário
     init.defaultbranch=main
     ```

     Aqui está o detalhamento do comando:

     - `git`: Comando Git padrão para várias operações.
     - `config`: Usado para configurações do Git.
     - `--`: É um indicador de que o que vem a seguir é uma opção.
     - `global`: Define configurações para todos os repositórios Git.
     - `list`: Exibe uma lista de configurações.

   - Você também pode consultar configurações individuais de forma específica. Por exemplo, para consultar o nome do usuário:

     ```bash
     git config user.name # Resultado "nome do usuário"
     ```

   - Caso você vá utilizar um novo repositório, é possível definir parâmetros de forma pontual, como usuário, e-mail, branch, entre outros. Para isso, esteja com o terminal aberto no diretório do novo repositório. Por exemplo, para alterar o e-mail definido neste repositório:

     ```bash
     git config user.email "novo email"
     ```

     Vale ressaltar que, para consultar as configurações neste novo repositório, o comando `--global` deve ser retirado. Você também pode consultar todas as configurações do novo repositório:

     ```bash
     git config --list
     ```

   - Os comandos apresentados acima são apenas exemplos de como começar com o Git. Eles podem ser adaptados para diferentes objetivos, tornando o Git uma ferramenta flexível para suas necessidades de desenvolvimento.

5. **Configuração do tema de exibição no terminal Git**

   Com o terminal aberto basta clicar dentro com o botão direito do mouse e selecionar `Opções`. Na nova janela selecione `Looks` e escolha a opção de sua preferência na lista `Theme`.
