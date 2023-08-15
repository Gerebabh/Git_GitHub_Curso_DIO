# Autenticando via Token no GitHub

O Git opera de forma independente em relação a um repositório remoto. No entanto, ao conectar o Git ao GitHub, é possível permitir o trabalho de pessoas em localizações distintas, como equipes que operam em regime de Home-Office.

Atualmente, o GitHub oferece três métodos de autenticação: via navegador da web, Token ou Chave SSH.

Um token é uma sequência de caracteres gerada pelo GitHub que pode ser usada como uma alternativa à senha para autenticar sua conta. Ele é usado para aumentar a segurança da sua conta, pois permite conceder permissões específicas para acessar seus repositórios e dados. Além disso, você pode gerar vários tokens com diferentes permissões e prazos de validade, permitindo um controle mais granular sobre o acesso à sua conta.

Para começar, é necessário ter uma conta no GitHub. Se você ainda não possui uma, crie uma agora.

## Autenticação via Navegador da Web

Quando você tenta clonar um repositório, o Git pode solicitar que você abra o navegador para autenticar sua conta do GitHub. Depois de autenticar com sucesso, o Git memoriza essas credenciais, evitando que você precise autenticar novamente toda vez que clonar um repositório.

## Criando um Repositório Remoto no GitHub

1. Acesse sua conta no GitHub.
2. Crie um novo repositório:
   - Clique em “Novo Repositório”.
   - Escolha um nome, por exemplo: “ola-mundo”.
   - Adicione uma breve descrição do repositório (Opcional). Exemplo: “Meu primeiro repositório remoto.”
   - Defina se o repositório será Público ou Privado, dependendo de quem você deseja que tenha acesso. Para fins de aprendizado, escolha Privado.
   - Marque a opção `Add a README file`.
   - Clique em “Criar Repositório”.

## Gerando um Token

1. Clique na imagem do usuário no canto superior direito.
2. Selecione “Settings”.
3. Na nova página, na coluna esquerda, clique em “<> Developer Settings”.
4. Escolha “Personal access tokens” e “Tokens (classic)”.
5. Clique em “Generate new token (classic)”.
6. Preencha o campo “Note” para descrever a finalidade do token, como o nome do projeto.
7. Defina o prazo de validade do Token.
8. Escolha as permissões que deseja conceder com o Token.
9. Clique em “Generate token”.

Depois de gerado, lembre-se de copiar o token, pois ele só será mostrado uma vez por questões de segurança. Se o perder, será necessário gerar um novo token.

Na seção “Personal access tokens\Tokens (Classics)”, você poderá visualizar os tokens criados, suas datas de expiração e também deletá-los.

## Configurando o Token no Terminal do Git Bash

Você pode armazenar o token no terminal Git de duas formas: permanentemente ou temporariamente. A configuração pode ser feita de forma global ou específica para um repositório.

**Configuração Permanente** - Normalmente usada em computadores de uso exclusivo:

```bash
git config --global credential.helper store
```

 Copiar

Essa configuração armazena suas credenciais de forma segura, permitindo que você as utilize sempre que necessário.

**Configuração Temporária** - Indicada para computadores compartilhados:

```bash
git config --global credential.helper cache
```

 Copiar

Essa configuração mantém suas credenciais em cache por um período de tempo, evitando autenticações frequentes em um intervalo curto.

## Realizando um Clone do Repositório

Após configurar suas credenciais, você pode clonar um repositório remoto para o local desejado:

```bash
git clone "link https do repositório"
```

 Copiar

O Git solicitará seu nome de usuário do GitHub e, no campo da senha, cole o Token gerado. Após inserir corretamente as credenciais, o clone será iniciado e o repositório remoto será copiado para sua máquina.

## Localizando as Credenciais Salvas

No Windows, as credenciais do Git são armazenadas em diferentes locais, dependendo da configuração. Se você usou a configuração store, as credenciais podem ser encontradas no Gerenciador de Credenciais do Windows. Para verificar a configuração atual, você pode usar o seguinte comando no Git Bash:

```bash
git config --global --show-origin credential.helper
```

 Copiar