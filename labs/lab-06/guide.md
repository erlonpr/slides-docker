# Configuração de CI/CD com GitHub Actions e Docker

## O que é o GitHub Actions?

O GitHub Actions é uma plataforma de automação (CI/CD) integrada diretamente ao GitHub. Ela permite que você construa, teste e publique (faça o *deploy*) de seus projetos de forma automática sempre que algo acontecer no seu repositório.

### Como ele funciona?

A estrutura do GitHub Actions é dividida em alguns conceitos principais:

- **Eventos (Triggers):** O que dá o gatilho para a automação iniciar (ex: fazer um `push` na branch `main`).
- **Workflows:** O processo automatizado inteiro, escrito em um arquivo YAML.
- **Jobs:** Blocos de tarefas dentro do workflow. Por padrão, rodam em paralelo, mas podem ser configurados para depender uns dos outros.
- **Runners:** Os servidores (máquinas virtuais) onde as tarefas rodam de fato (ex: um servidor Linux Ubuntu cedido pelo GitHub).
- **Steps:** As ações individuais executadas dentro de um job. Um passo pode ser um simples comando de terminal (`run`) ou o uso de uma **Action** pronta (um pacote de código reutilizável, que pode inclusive ser a execução de um contêiner Docker).

## Exemplo prático

Para visualizar um exemplo prático de CI/CD utilizando um contêiner Docker com GitHub Actions, acesse a seguinte URL:

- [https://github.com/erlonpr/slides-docker/blob/main/.github/workflows/deploy.yml](https://github.com/erlonpr/slides-docker/blob/main/.github/workflows/deploy.yml)

> Neste arquivo, você poderá analisar detalhadamente como um contêiner do Marp CLI é utilizado como uma Action para converter os arquivos Markdown em slides e publicá-los no GitHub Pages.
