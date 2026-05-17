# Lab 05 - OS as a Container (Linux no Navegador)

Este laboratório tem como objetivo demonstrar, na prática, como é fácil subir um ambiente de trabalho Linux completo utilizando o Docker Compose e acessá-lo diretamente pelo seu navegador web.

## Passo a Passo

**1. Preparando o ambiente:**
- Crie uma pasta no seu computador chamada `lab-05`.
- Abra o VS Code.
- Vá no menu superior em **File > Open Folder...** (Arquivo > Abrir Pasta...) e selecione a pasta `lab-05` que você acabou de criar.

**2. Obtendo o arquivo de configuração:**
- Acesse a seguinte URL no seu navegador:
  [https://github.com/erlonpr/slides-docker/blob/main/labs/lab-05/docker-compose.yml](https://github.com/erlonpr/slides-docker/blob/main/labs/lab-05/docker-compose.yml)
- Na tela do GitHub, no canto superior direito da caixa de código, clique no botão **Download raw file** (representado pelo ícone de uma setinha de download).
- Salve o arquivo baixado dentro da sua pasta `lab-05` garantindo que o nome do arquivo permaneça exatamente como `docker-compose.yml`.

**3. Subindo o Ambiente Linux:**
- Com a extensão oficial do Docker já instalada no seu VS Code, vá no explorador de arquivos na lateral esquerda.
- Clique com o **botão direito do mouse** sobre o arquivo `docker-compose.yml`.
- Selecione a opção **Compose Up**. 
- O Docker começará a baixar a imagem e criar o contêiner. Isso pode levar alguns minutos, pois ele está baixando um sistema operacional inteiro!

**4. Acessando o seu novo Desktop:**
- Após o terminal indicar que o contêiner foi iniciado com sucesso, abra o seu navegador de internet 
- Acesse a seguinte URL: [http://localhost:3000](http://localhost:3000)

> Certifique-se de digitar exatamente **http://** (sem o "S"). Muitos navegadores atuais tentam forçar o redirecionamento automático para `https://`, o que fará a página exibir um erro de conexão. Para a porta 3000 do nosso laboratório, você deve usar explicitamente o protocolo HTTP puro.

**5. Encerrando o laboratório:**
- Após testar e navegar pelo seu ambiente Linux, lembre-se de liberar os recursos da sua máquina.
- Volte ao VS Code, clique novamente com o botão direito no arquivo `docker-compose.yml` e selecione **Compose Down**.
