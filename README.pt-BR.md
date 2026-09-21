# Eduardo Garcia

[English](README.md) · **Português**

**Engenheiro de software · arquiteto de BI · operações.** Duas décadas entregando Java e Python, transformando dado em decisão e operando os sistemas onde tudo isso vive — inclusive uma frota self-hosted pequena que eu trato como restrição de engenharia, não como desculpa.

A maior parte do meu trabalho vive em repositórios privados. O gráfico de contribuições mostra o volume; esta página mostra o que está por trás dele.

---

## O que eu construo

**Java é onde a maior parte do meu código vive.** Serviços Spring Boot em arquitetura hexagonal (ports & adapters), sobre PostgreSQL: JPA, migração de schema versionada com Flyway, Spring Security com provedor de identidade externo, Redis pra cache, Actuator pra health e métricas. Cada um entrega a aplicação inteira — API em Java, frontend Vue/TypeScript, nginx, tudo declarado em Compose e publicado num control plane self-hosted atrás do meu próprio DNS.

**Go pras partes que exigem throughput** — workers de longa duração e serviços de integração, onde uma JVM por processo seria a troca errada.

**Pipeline de automação de mídia** — ~18 mil linhas de Bash e Python em volta do ffmpeg: normalização de loudness, geração e limpeza de legendas via LLM, e trilha de auditoria de toda chamada de modelo em SQLite, pra que custo e qualidade sejam mensuráveis em vez de achismo.

## Dados e BI

**Duas décadas do lado dos dados no setor público**, onde o volume é grande e as perguntas são políticas: pipelines de ETL em Pentaho, modelagem dimensional sobre PostgreSQL e Oracle, dashboards em Power BI pro negócio e em Grafana pra operação, automação em Python costurando tudo.

A parte de que mais me orgulho não tem glamour: uma **camada de analytics de service desk versionada** — dashboards do Grafana e uma biblioteca de SQL de indicadores de gestão (tíquetes por departamento, incidentes por grupo, cumprimento de SLA) mantidas no git como qualquer outro código, pra que um número num slide possa ser rastreado até a query que o produziu.

Isso aparece em tudo que eu escrevo: cada aplicação acima tem uma camada de relatório e agregação, porque sistema que não consegue se explicar em números não está pronto.

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

**Linguagens** — Java · Go · Python · TypeScript/Vue · Bash · SQL / PL/SQL

**Dados e BI** — PostgreSQL · Oracle · Power BI · Pentaho Data Integration · Grafana · Prometheus

**Infraestrutura** — Docker Compose · Traefik · Caddy · Linux · DNS autoritativo

**Mídia** — ffmpeg · SQLite · Redis

<sub>Certificações: Grafana Labs (Grafana, Loki, Prometheus) · Power BI · ETL avançado com PDI · Python para SysAdmins.</sub>

---

## Como eu trabalho

- **Se não é medido, é opinião.** Dashboard pro negócio, dashboard pros servidores, tabela de auditoria pras chamadas de LLM — o mesmo instinto, três domínios.
- **Se não está versionado e documentado, não existe.** Todo host tem um caminho escrito de volta do zero.
- **Chato ganha de esperto.** Seis hosts não precisam de Kubernetes; precisam de arquivos Compose que alguém consiga ler com pressa.
- **Migração é em fases, reversível e documentada** — inclusive as decisões que eu voltei atrás, e o porquê.
- **Eu mato coisas de propósito.** Serviço que parou de se pagar é removido e registrado como decisão, não deixado rodando por via das dúvidas.
- **Português e inglês**, terminal em primeiro lugar, `vim` e só.

---

<sub>Os repositórios aqui são privados por decisão — trabalho de cliente, de setor público e de infraestrutura. Converso com prazer sobre arquitetura, trade-offs e modos de falha.</sub>

📫 **Contato:** edicgarcia@outlook.com
