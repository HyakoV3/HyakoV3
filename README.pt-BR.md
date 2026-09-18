# Eduardo Garcia

[English](README.md) · **Português**

**Engenheiro de backend — e meu próprio time de infraestrutura.** Serviços em Java e Go em produção, sobre uma frota self-hosted pequena que eu trato como restrição de engenharia, não como desculpa.

A maior parte do meu trabalho vive em repositórios privados. O gráfico de contribuições mostra o volume; esta página mostra o que está por trás dele.


---

## O que eu construo

**Java é onde a maior parte do meu código vive.** Serviços Spring Boot sobre PostgreSQL: JPA, migração de schema versionada com Flyway, Spring Security com provedor de identidade externo, Redis pra cache, Actuator pra health e métricas. Cada um entrega a aplicação inteira — API em Java, frontend Vue/TypeScript, nginx, tudo declarado em Compose e publicado num control plane self-hosted atrás do meu próprio DNS.

**Go pras partes que exigem throughput** — workers de longa duração e serviços de integração, onde uma JVM por processo seria a troca errada.

**Pipeline de automação de mídia** — ~18 mil linhas de Bash e Python em volta do ffmpeg: normalização de loudness, geração e limpeza de legendas via LLM, e trilha de auditoria de toda chamada de modelo em SQLite, pra que custo e qualidade sejam mensuráveis em vez de achismo.

## O que eu realmente opero

Uma frota de seis hosts (casa + nuvem), com nomes tirados do panteão nórdico — porque infraestrutura que você não consegue nomear é infraestrutura sobre a qual você não consegue conversar às 3 da manhã.

- **~60 serviços em containers distribuídos em 26 stacks Compose** — redes em camadas, só o proxy reverso exposto pra internet, segredo nenhum versionado.
- **Três proxies reversos em produção** (Traefik, Caddy e um Traefik gerenciado por PaaS), porque o ingress certo depende de quem vai operar, não do que está na moda.
- **DNS autoritativo que eu controlo de ponta a ponta**, mais firewall, fail2ban e docs de recuperação por host pro estado que arquivo Compose nenhum captura.
- **Migração da frota inteira de ARM64 pra x86_64**, planejada em fases e executada sem perder serviço — as máquinas antigas só foram deletadas depois que as novas se provaram.

---

## Em números

![Métricas](github-metrics.svg)

<sub>Gerado diariamente. Inclui repositórios privados de forma agregada — contagens e linguagens, nunca nomes.</sub>

---

## Ferramentas

**Linguagens** — Java · Go · TypeScript/Vue · Python · Bash

**Infraestrutura** — Docker Compose · Traefik · Caddy · Linux · DNS autoritativo

**Dados e mídia** — PostgreSQL · Redis · SQLite · ffmpeg

---

## Como eu trabalho

- **Se não está versionado e documentado, não existe.** Todo host tem um caminho escrito de volta do zero.
- **Chato ganha de esperto.** Seis hosts não precisam de Kubernetes; precisam de arquivos Compose que alguém consiga ler com pressa.
- **Migração é em fases, reversível e documentada** — inclusive as decisões que eu voltei atrás, e o porquê.
- **Eu mato coisas de propósito.** Serviço que parou de se pagar é removido e registrado como decisão, não deixado rodando por via das dúvidas.
- **Português e inglês**, terminal em primeiro lugar, `vim` e só.

---

<sub>Os repositórios aqui são privados por decisão — trabalho de cliente e de infraestrutura. Converso com prazer sobre arquitetura, trade-offs e modos de falha.</sub>

📫 **Contato:** [LinkedIn](https://linkedin.com/in/edu-costa-garcia/) · edicgarcia@outlook.com

