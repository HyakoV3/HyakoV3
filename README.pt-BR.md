# Eduardo Garcia

[English](README.md) · **Português**

**Engenheiro de infraestrutura e backend.** Opero uma frota de produção self-hosted pequena — e trato "pequena" como restrição de engenharia, não como desculpa.

A maior parte do meu trabalho vive em repositórios privados, então meu gráfico de contribuições não diz quase nada sobre mim. Esta página é a versão honesta do que está por trás dele.

---

## Em números

![Métricas](github-metrics.svg)

<sub>Gerado diariamente. Inclui repositórios privados de forma agregada — contagens e linguagens, nunca nomes.</sub>

---

## O que eu realmente opero

Uma frota de seis hosts (casa + nuvem), com nomes tirados do panteão nórdico — porque infraestrutura que você não consegue nomear é infraestrutura sobre a qual você não consegue conversar às 3 da manhã.

- **~60 serviços em containers distribuídos em 26 stacks Compose** — redes em camadas, só o proxy reverso exposto pra internet, segredo nenhum versionado.
- **Três proxies reversos em produção** (Traefik, Caddy e um Traefik gerenciado por PaaS), porque o ingress certo depende de quem vai operar, não do que está na moda.
- **DNS autoritativo que eu controlo de ponta a ponta**, mais firewall, fail2ban e docs de recuperação por host pro estado que arquivo Compose nenhum captura.
- **Migração da frota inteira de ARM64 pra x86_64**, planejada em fases e executada sem perder serviço — as máquinas antigas só foram deletadas depois que as novas se provaram.

## O que eu construo

**Pipeline de automação de mídia** — ~18 mil linhas de Bash e Python em volta do ffmpeg: normalização de loudness, geração e limpeza de legendas via LLM, e trilha de auditoria de toda chamada de modelo em SQLite, pra que custo e qualidade sejam mensuráveis em vez de achismo.

**Aplicações** — serviços em Go, backends Java, frontends Vue/TypeScript, PostgreSQL. Tudo containerizado, publicado por um control plane self-hosted, atrás do meu próprio DNS.

---

## Ferramentas

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Java](https://img.shields.io/badge/Java-E76F00?style=flat-square&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Vue](https://img.shields.io/badge/Vue-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Traefik](https://img.shields.io/badge/Traefik-24A1C1?style=flat-square&logo=traefikproxy&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat-square&logo=caddy&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-1A1A1A?style=flat-square&logo=linux&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![ffmpeg](https://img.shields.io/badge/ffmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![Vim](https://img.shields.io/badge/Vim-019733?style=flat-square&logo=vim&logoColor=white)

---

## Como eu trabalho

- **Se não está versionado e documentado, não existe.** Todo host tem um caminho escrito de volta do zero.
- **Chato ganha de esperto.** Seis hosts não precisam de Kubernetes; precisam de arquivos Compose que alguém consiga ler com pressa.
- **Migração é em fases, reversível e documentada** — inclusive as decisões que eu voltei atrás, e o porquê.
- **Eu mato coisas de propósito.** Serviço que parou de se pagar é removido e registrado como decisão, não deixado rodando por via das dúvidas.
- **Português e inglês**, terminal em primeiro lugar, `vim` e só.

---

<sub>Os repositórios aqui são privados por decisão — trabalho de cliente e de infraestrutura. Converso com prazer sobre arquitetura, trade-offs e modos de falha.</sub>

📫 **Contato:** [LinkedIn](https://linkedin.com/in/edu-costa-garcia/) · edicgarcia@gmail.com

