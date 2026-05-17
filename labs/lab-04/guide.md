# Lab 04 - DevContainers (Ambiente de Desenvolvimento Node.js)

Este laboratório tem como objetivo demonstrar, na prática, como é fácil preparar um ambiente de desenvolvimento padronizado e isolado utilizando a extensão **Dev Containers** do VS Code. Vamos rodar uma aplicação Node.js sem precisar instalar o Node.js na sua própria máquina!

## Passo a Passo

**1. Preparando a pasta do projeto:**
- Crie uma pasta no seu computador chamada `lab-04`.
- Abra o VS Code.
- Vá no menu superior em **File > Open Folder...** (Arquivo > Abrir Pasta...) e selecione a pasta `lab-04` que você acabou de criar.

**2. Obtendo os arquivos da aplicação Node.js:**
- Acesse as URLs abaixo no seu navegador. Para cada uma delas, lembre-se de usar o botão **Download raw file** (localizado no canto superior direito da caixa de código, com o ícone de uma setinha de download).
  - [index.js](https://github.com/erlonpr/slides-docker/blob/main/labs/lab-04/index.js)
  - [package.json](https://github.com/erlonpr/slides-docker/blob/main/labs/lab-04/package.json)
- Salve ambos os arquivos baixados diretamente na raiz da sua pasta `lab-04`.

**3. Obtendo a configuração do Dev Container:**
- No VS Code, crie uma nova pasta chamada exatamente **`.devcontainer`** (não esqueça do ponto inicial).
- Acesse a URL abaixo e faça o download do arquivo de configuração:
  - [devcontainer.json](https://github.com/erlonpr/slides-docker/blob/main/labs/lab-04/.devcontainer/devcontainer.json)
- Salve esse arquivo **dentro** da pasta `.devcontainer` que você acabou de criar.

**4. Instalando a Extensão Dev Containers:**
- No VS Code, abra a aba de **Extensions** (Extensões) na barra lateral esquerda.
- Pesquise por **Dev Containers** (extensão oficial da Microsoft, com identificador `ms-vscode-remote.remote-containers`).
- Clique em **Install** e aguarde a conclusão.

**5. Abrindo o projeto dentro do Contêiner:**
- Pressione a tecla `F1` (ou `Ctrl+Shift+P` no Windows/Linux, `Cmd+Shift+P` no Mac) para abrir a Paleta de Comandos do VS Code.
- Digite **`Dev Containers: Reopen in Container`** e selecione essa opção.
- O VS Code vai recarregar a janela e começar a construir o contêiner com o ambiente Node.js. *Nota: Esse processo pode demorar alguns minutos na primeira vez, pois a imagem base do Node.js será baixada da internet.*

**6. Rodando a aplicação:**
- Após o ambiente carregar com sucesso, perceba que o seu VS Code está rodando **de dentro** do contêiner!
- Abra um novo terminal no VS Code acessando o menu **Terminal > New Terminal**.
- Digite o comando abaixo para executar o projeto:
  ```bash
  npm start
  ```
- Você deverá ver a seguinte mensagem ser exibida na tela:
  > **"Na minha máquina funciona... e no container também!"**

**7. Encerrando e saindo do Dev Container:**
- Após finalizar seus testes, você deve retornar o seu editor para a máquina local.
- Pressione novamente `F1` (ou `Ctrl+Shift+P`).
- Digite e selecione a opção **`Dev Containers: Reopen Folder Locally`**.
- O VS Code será recarregado e voltará a acessar a pasta local de forma normal.
- *(Opcional)* Você pode fechar o contêiner que ficou rodando em segundo plano indo na extensão oficial do Docker na barra lateral, clicando com o botão direito sobre o contêiner em execução e selecionando "Stop".
