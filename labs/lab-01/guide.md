# Lab 01 - Primeiros Passos com Docker

Este laboratório tem o objetivo de demonstrar a execução do seu primeiro contêiner e o gerenciamento básico pelo terminal.

## Passo a Passo

> **Preparação:** Antes de iniciar os comandos deste laboratório, abra o seu terminal de preferência. Eu recomendo utilizar o **Windows Terminal (PowerShell)** ou o terminal integrado do **VS Code**.

**1. Executar o Hello World:**
O comando abaixo irá baixar a imagem `hello-world` do Docker Hub (caso não tenha na máquina local) e executá-la. Essa imagem apenas imprime uma mensagem de sucesso e o contêiner é encerrado logo em seguida.
```bash
docker run hello-world
```

**2. Listar contêineres em execução:**
O comando `ps` (process status) mostra os contêineres que estão rodando *neste exato momento*. Como o `hello-world` já rodou e encerrou, ele não aparecerá aqui.
```bash
docker ps
```

**3. Listar todos os contêineres (incluindo os parados):**
A flag `-a` (all) mostra todo o histórico de contêineres na sua máquina.
Aqui você conseguirá ver o seu contêiner do `hello-world` com o status de `Exited` (Finalizado).
```bash
docker ps -a
```
