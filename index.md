---
marp: true
emoji: true
---

![w:300](assets/img/docker.svg)

# Docker para Iniciantes
Embale seu código e leve para qualquer lugar




---

## :whale: Acesso ao material

- GitHub Pages:
[erlonpr.github.io/slides-docker](https://erlonpr.github.io/slides-docker/)
- GitHub Repository:
[github.com/erlonpr/slides-docker](https://github.com/erlonpr/slides-docker)

---

## :whale: Sobre mim

Analista de sistemas e programador freelancer

- GitHub: [github.com/erlonpr](https://github.com/erlonpr)
- LinkedIn: [linkedin.com/in/erlonpr](https://linkedin.com/in/erlonpr)
- Blog: [erlonpr.github.io/blog](https://erlonpr.github.io/blog)

![bg right:40%](./assets/img/avatar.svg)

---

## :whale: Conhecimentos necessários

- Linux
- Redes
- Lógica de programação

![bg right:40%](./assets/gif/tux.gif)

---

## :whale: Contextualizando o problema

> "Na minha máquina funciona!"

Programador | **Devops** | Infraestrutura

![bg right:40%](./assets/gif/devops.gif)

---

## :whale: Virtualização vs. Contêinerização

| Máquina Virtual (VM) | Contêiner (Docker) |
| :--- | :--- |
| Emula o hardware e possui um SO completo | Compartilha o Kernel do SO hospedeiro |
| Pesado (Gigas de tamanho) | Leve (Megabytes) |
| Velocidade de inicialização lenta | Velocidade de inicialização rápida |
| Isolamento de SO | Isolamento de processos   |

> Namespaces: Isolam os processos
> Cgroups: Controlam o uso de recursos

---

## :whale: O que é o Docker?

Ferramenta de automação baseada em contêineres que facilita o desenvolvimento, testes e deployment de aplicações.

- Docker
```
[Hardware] -> [Kernel SO Host] -> [Docker Daemon] -> [Contêineres] -> [Aplicação]
```

- Virtualização
```
[Hardware] -> [Kernel SO Host] -> [Hypervisor Hosted] -> [SO Convidado] -> [Aplicação]
```

> *Hypervisor: software que cria e executa máquinas virtuais*
> *- Tipo 1 (Bare-metal): Xen, Hyper-V, Proxmox*
> *- Tipo 2 (Hosted): VMWare, VirtualBox*

---
