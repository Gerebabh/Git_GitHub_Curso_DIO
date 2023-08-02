# :books: Aula 2 - Salvando Alterações no Repositório Local

Caso precise consultar os comandos básicos do Git, clique  [aqui]([Git_GitHub_Curso_DIO/Aula 0 - Estrutura Git - Comandos Básicos.md at main · Gerebabh/Git_GitHub_Curso_DIO](https://github.com/Gerebabh/Git_GitHub_Curso_DIO/blob/main/Aula 0 - Estrutura Git - Comandos Básicos.md)).

### :computer: Temas da aula

- Status dos arquivos.
- Criação de arquivos.
- Criação do arquivo README.md
- Ciclo do arquivo no Git.

```mermaid
graph LR
  UNTRACKED -->|Adiciona o arquivo| STAGED
  UNTRACKED -->|Remove o arquivo| UNTRACKED
  UNMODIFIED -->|Edita o arquivo| MODIFIED
  MODIFIED -->|"Staged" arquivo| STAGED
  STAGED -->|COMMIT| UNMODIFIED
```

Copiar

- Criação de arquivos em Mark Down - [Versão Gratuita Online](https://readme.so/pt).
- Utilização do `echo` para criação de arquivos como exemplo o `.gitignore`.
- Utilização `git add`, `git commit`, `git log`.