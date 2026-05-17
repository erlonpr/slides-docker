# Lab 03 - Banco de dados PostgreSQL com Docker Compose

Este laboratório guiará você na criação de um banco de dados PostgreSQL utilizando o Docker Compose e na conexão a ele diretamente pelo VS Code.

## Passo a passo

**1. Preparando a pasta do projeto:**
- Crie uma pasta no seu computador chamada `lab-03`.
- Abra o VS Code.
- Vá em `File > Open Folder...` (Arquivo > Abrir Pasta...) e selecione a pasta `lab-03` que você acabou de criar.

**2. Obtendo o arquivo de configuração:**
- Acesse a seguinte URL no seu navegador:
  [https://github.com/erlonpr/slides-docker/blob/main/labs/lab-03/docker-compose.yml](https://github.com/erlonpr/slides-docker/blob/main/labs/lab-03/docker-compose.yml)
- Na tela do GitHub, no canto superior direito da caixa de código, clique no botão **Download raw file** (representado pelo ícone de uma setinha de download).
- Salve o arquivo baixado dentro da sua pasta `lab-03` garantindo que o nome do arquivo permaneça exatamente como `docker-compose.yml`. (Dica: você também pode copiar o conteúdo da página e criar o arquivo manualmente direto no VS Code).

**3. Instalando a extensão do Docker no VS Code:**
- No VS Code, abra a aba de Extensões (`Ctrl+Shift+X` ou `Cmd+Shift+X` no Mac).
- Busque e instale a extensão oficial do **Docker** (ID: `ms-azuretools.vscode-docker`).

**4. Subindo o banco de dados:**
- Após instalar a extensão do Docker, volte para o explorador de arquivos do VS Code.
- Clique com o **botão direito do mouse** sobre o arquivo `docker-compose.yml`.
- Escolha a opção **Compose Up**. O Docker vai baixar a imagem do PostgreSQL e iniciar o banco de dados em segundo plano.

**5. Preparando para conectar no banco de dados:**
- Vá novamente na aba de Extensões do VS Code.
- Busque e instale a ferramenta de banco de dados **SQLTools** (ID: `mtxr.sqltools`).
- Em seguida, instale também o driver específico para PostgreSQL: **SQLTools PostgreSQL/Cockroach Driver** (ID: `mtxr.sqltools-driver-pg`).

**6. Acessando o banco de dados:**
- Com as extensões instaladas, um novo ícone de banco de dados (SQLTools) aparecerá na barra lateral esquerda do VS Code.
- Clique nele, adicione uma nova conexão clicando em "Add New Connection" e escolha **PostgreSQL**.
- Preencha os dados de conexão de acordo com as variáveis de ambiente definidas no arquivo `docker-compose.yml`:
  - **Connection Name:** `lab-03`  
  - **Server Address:** `localhost`
  - **Port:** `5432`
  - **Database:** `lab_db`
  - **Username:** `admin`
  - **Password:** No campo "User password", selecione a opção **SQLTools Driver Credentials** (deixe o campo de texto em branco na tela).

- Na parte inferior da tela, clique em **Test Connection**. O VS Code abrirá um campo de texto no **topo da janela** solicitando a senha. Digite `p@ssw0rd` e aperte Enter para validar a conexão.
- Após o teste retornar sucesso, clique em **Save Connection**.
- Uma nova tela irá abrir mostrando um resumo da conexão salva. Nela, basta clicar no botão **CONNECT NOW** para finalmente acessar o seu banco de dados!

**7. Executando seu primeiro comando SQL:**
- Com a conexão ativa no SQLTools, clique no botão **New SQL File** (Novo arquivo SQL).
- Para testar a sua conexão, vamos criar uma tabela chamada `docker` no banco atual (`lab_db`) e inserir um dado de teste:

```sql
CREATE TABLE docker (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    descricao TEXT
);

INSERT INTO docker (nome, descricao) VALUES ('Contêiner', 'Ambiente isolado em execução');

SELECT * FROM docker;
```
- Para executar, basta selecionar todo o bloco de código acima no VS Code e clicar em **Run Selected Query** no menu que aparece em cima do código ou usar o atalho `Ctrl+E`, `Ctrl+E`.

**8. Encerrando o banco de dados:**
- Após finalizar os seus testes, é uma boa prática desligar o ambiente para não consumir os recursos do seu computador à toa.
- Volte para o explorador de arquivos do VS Code.
- Clique com o **botão direito do mouse** sobre o arquivo `docker-compose.yml`.
- Escolha a opção **Compose Down**.
- A extensão do Docker irá parar e remover os contêineres e a rede criados por este laboratório de forma automática. *(Não se preocupe: os seus dados estarão salvos no volume `pgdata` e estarão lá intactos na próxima vez que você fizer o Compose Up!)*

