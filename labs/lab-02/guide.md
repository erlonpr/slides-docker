# Lab 02 - Acessando o interior de um Contêiner

Neste laboratório vamos criar um contêiner Alpine (que rodará em segundo plano) e em seguida vamos entrar no terminal interativo dele. A imagem do Alpine é extremamente leve (cerca de 5MB) e o download é praticamente instantâneo.

## Passo a Passo

> **Preparação:** Antes de iniciar os comandos deste laboratório, abra o seu terminal de preferência. Eu recomendo utilizar o **Windows Terminal (PowerShell)** ou o terminal integrado do **VS Code**.

**1. Criar e iniciar o contêiner do Alpine em segundo plano:**
O comando abaixo baixa a imagem do Alpine e a executa em modo *detached* (`-d`). Para que o contêiner não morra imediatamente (já que ele não tem um processo ativo contínuo nativo), usamos as flags `-it` (Interactive TTY), que deixam o terminal interno aberto aguardando comandos, mesmo ele estando em segundo plano.
```bash
docker run -it -d --name lab-alpine alpine
```

**2. Acessar o terminal do contêiner em execução:**
O comando `exec` permite executar um novo processo dentro de um contêiner já existente. Usamos `-it` para abrir uma sessão interativa (Terminal) usando o `sh` (o Alpine não vem com bash instalado por padrão para economizar espaço).
```bash
docker exec -it lab-alpine sh
```
> *Dica: Assim que executar o comando acima, repare que o seu prompt mudará (ex: `/ #`). Agora você está executando comandos dentro do Alpine! Tente rodar `cat /etc/os-release` ou `ls`.*

**3. Sair do contêiner:**
Para sair do terminal interativo do Alpine e voltar para a sua máquina hospedeira, digite:
```bash
exit
```

**4. Limpar o laboratório:**
Como o contêiner foi criado em background, ele continuará rodando. Para pará-lo e removê-lo, execute:
```bash
docker rm -f lab-alpine
```

> O comando `docker rm` normalmente só apaga contêineres que já estão parados. Ao utilizar a flag `-f` (force), o Docker força a parada imediata do contêiner e já o deleta logo em seguida. É um atalho muito prático que substitui a necessidade de rodar `docker stop` seguido de `docker rm` em um ambiente de testes.
