# Autenticando via Chave SSH no GitHub

O Git opera de forma independente em relação a um repositório remoto. No entanto, ao conectar o Git ao GitHub, é possível permitir o trabalho de pessoas em localizações distintas, como equipes que operam em regime de Home-Office.

Atualmente, o GitHub oferece três métodos de autenticação: via navegador da web, Token ou Chave SSH.

Uma chave SSH é um par de chaves criptográficas usadas para autenticar sua conta do GitHub. Ela é usada para aumentar a segurança da sua conta, pois permite estabelecer uma conexão segura entre o Git e o GitHub sem a necessidade de inserir sua senha toda vez que você realiza uma operação.

## Gerando uma Chave SSH pelo Git

1. Abra o terminal Git Bash.

2. Verifique se você já possui uma chave SSH existente:

   ```
   ls -al ~/.ssh
   ```

   Se você já possui uma chave SSH, ela será exibida na lista de arquivos. Caso contrário, você precisará gerar uma nova chave.

3. Gere uma nova chave SSH:

   ```bash
   ssh-keygen -t rsa -b 4096 -C "seu_email@example.com"
   ```

   Substitua `seu_email@example.com` pelo endereço de e-mail associado à sua conta do GitHub.

4. Quando solicitado a inserir um local para salvar a chave, pressione Enter para aceitar o local padrão.
5. Quando solicitado a inserir uma senha, digite uma senha forte e pressione Enter. Essa senha será usada para desbloquear sua chave SSH sempre que você realizar uma operação que exija autenticação.

## Gerando uma Chave SSH pelo GitHub

1. Acesse sua conta no GitHub.
2. Clique na imagem do usuário no canto superior direito.
3. Selecione “Settings”.
4. Na nova página, na coluna esquerda, clique em “SSH and GPG keys”.
5. Clique em “New SSH key”.
6. Preencha o campo “Title” com um nome descritivo para a chave, como o nome do seu computador.
7. Siga as instruções na tela para gerar e adicionar a chave SSH à sua conta do GitHub.

## Adicionando a Chave SSH à sua Conta do GitHub

1. Copie a chave pública gerada para a área de transferência:

   ```bash
   clip < ~/.ssh/id_rsa.pub
   ```

2. Acesse sua conta no GitHub.
3. Clique na imagem do usuário no canto superior direito.
4. Selecione “Settings”.
5. Na nova página, na coluna esquerda, clique em “SSH and GPG keys”.
6. Clique em “New SSH key”.
7. Preencha o campo “Title” com um nome descritivo para a chave, como o nome do seu computador.
8. Cole a chave pública no campo “Key”.
9. Clique em “Add SSH key”.

## Adicionando a Chave SSH ao Agente SSH

1. Abra o terminal Git Bash.
2. Inicie o agente SSH:

   ```bash
   eval "$(ssh-agent -s)"
   ```

3. Adicione a chave privada ao agente SSH:

   ```bash
   ssh-add ~/.ssh/sua_chave_privada
   ```

   Substitua `sua_chave_privada` pelo nome da chave privada gerada pelo Git ou pelo GitHub.

## Testando a Conexão SSH

1. Abra o terminal Git Bash.
2. Teste a conexão SSH com o GitHub:

   ```bash
   ssh -T git@github.com
   ```

   Se a conexão for bem-sucedida, você verá uma mensagem de boas-vindas do GitHub.

## Clonando um Repositório Remoto

Após configurar sua chave SSH, você pode clonar um repositório remoto para o local desejado:

```bash
git clone "link ssh do repositório"
```

O Git usará automaticamente sua chave SSH para autenticar sua conta do GitHub e iniciar o clone do repositório remoto para sua máquina.