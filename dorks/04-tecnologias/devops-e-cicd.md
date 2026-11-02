<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [← Bancos de Dados](bancos-de-dados.md)

# ⚙ DevOps & CI/CD

*Ferramentas de build, observabilidade e qualidade expostas — Jenkins, GitLab, Grafana, Prometheus, Jira, SonarQube, Harbor, Argo CD.*

</div>

---

> [!CAUTION]
> Essas ferramentas podem conter código, segredos de pipeline e acesso a produção. Exposição é achado sensível; não acesse sem autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### CI/CD e build

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Dashboard [Jenkins]"` | Dashboard do Jenkins | Google | 🔴 |
| `inurl:/job/ intitle:"Jenkins"` | Jobs do Jenkins | Google | 🟡 |
| `intitle:"GitLab" intext:"A complete DevOps platform"` | Instância GitLab | Google | 🟡 |
| `inurl:/explore intitle:"Gitea"` | Instância Gitea | Google | 🟡 |
| `intitle:"Argo CD"` | Argo CD (deploy) | Google | 🔴 |
| `intitle:"Drone" inurl:/login` | Drone CI | Google | 🟡 |
| `intitle:"TeamCity"` | JetBrains TeamCity | Google | 🟡 |

### Observabilidade

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Grafana" inurl:/dashboards` | Dashboards do Grafana | Google | 🟡 |
| `intitle:"Prometheus Time Series"` | Console do Prometheus | Google | 🟡 |
| `intitle:"Alertmanager"` | Alertmanager | Google | 🟡 |
| `intext:"Powered by Grafana" inurl:/d/` | Dashboards compartilhados | Google | 🟡 |
| `intitle:"Zabbix" inurl:zabbix.php` | Monitoramento Zabbix | Google | 🟡 |

### Qualidade, registry e colaboração

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"SonarQube" inurl:/dashboard` | Análise de código SonarQube | Google | 🟡 |
| `intitle:"Harbor" inurl:/harbor` | Registry de containers Harbor | Google | 🔴 |
| `intitle:"Nexus Repository Manager"` | Repositório Sonatype Nexus | Google | 🟡 |
| `intitle:"Artifactory"` | JFrog Artifactory | Google | 🟡 |
| `inurl:/secure/Dashboard.jspa intitle:"Jira"` | Dashboard do Jira | Google | 🟡 |
| `intitle:"Confluence" inurl:/dashboard.action` | Wiki Confluence | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | Censys | FOFA |
|---|---|---|---|
| `intitle:"Dashboard [Jenkins]"` | `http.title:"Dashboard [Jenkins]"` | `web.endpoints.http.title:"Jenkins"` | `title="Dashboard [Jenkins]"` |
| `intitle:"Grafana" inurl:/dashboards` | `http.title:"Grafana"` | `web.endpoints.http.title:"Grafana"` | `title="Grafana"` |
| `intitle:"Prometheus Time Series"` | `http.title:"Prometheus"` | `web.endpoints.http.title:"Prometheus"` | `title="Prometheus"` |
| `intitle:"Harbor" inurl:/harbor` | `http.title:"Harbor"` | `web.endpoints.http.title:"Harbor"` | `title="Harbor"` |
| `intitle:"Argo CD"` | `http.title:"Argo CD"` | `web.endpoints.http.title:"Argo CD"` | `title="Argo CD"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Ferramenta DevOps por título — 18 variações

```text
intitle:"Jenkins"
intitle:"Drone"
intitle:"Spinnaker"
intitle:"Prometheus"
intitle:"SonarQube"
intitle:"Harbor"
intitle:"Rundeck"
intitle:"Concourse"
intitle:"Woodpecker CI"
intitle:"GoCD"
intitle:"Bamboo"
intitle:"Octopus Deploy"
intitle:"Rancher"
intitle:"Buildkite"
intitle:"Codefresh"
intitle:"Flux"
intitle:"Keptn"
intitle:"Semaphore CI"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Jenkins, Argo CD e Harbor sem auth são 🔴: dão acesso a build/deploy e a segredos de pipeline; apenas confirme a exposição.
- Páginas públicas de produto (marketing do GitLab/Jira) geram ruído — foque em instâncias reais com `site:` do alvo.
- Logins dessas ferramentas também estão em [03 · Painéis de Login](../03-infraestrutura-web/paineis-de-login.md); aqui o foco é a **ferramenta e seu dashboard**.
- Tokens de CI (`glpat-`, `GITHUB_TOKEN`) em arquivos de pipeline ficam em [02 · Tokens de API](../02-credenciais-e-segredos/tokens-de-api.md).

<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [← Bancos de Dados](bancos-de-dados.md)

</div>
