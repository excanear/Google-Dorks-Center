<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [← Servidores Web & App](servidores-web-e-app.md) · [Próximo: DevOps & CI/CD →](devops-e-cicd.md)

# 🗄 Bancos de Dados

*Exposição de serviços de banco e suas UIs web — MySQL, PostgreSQL, MongoDB, Elasticsearch, Redis, CouchDB, Kibana.*

</div>

---

> [!CAUTION]
> Um banco exposto pode conter dados pessoais e credenciais. **Não conecte nem consulte** sem autorização (Lei 12.737/2012, CFAA). Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Interfaces web de dados

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Elasticsearch" inurl:9200 "cluster_name"` | API do Elasticsearch exposta | Google | 🔴 |
| `inurl:9200/_cat/indices` | Índices do Elasticsearch | Google | 🔴 |
| `intitle:"Kibana" inurl:/app/kibana` | Console Kibana | Google | 🔴 |
| `intitle:"CouchDB" inurl:/_utils/` | Fauxton (CouchDB) | Google | 🔴 |
| `inurl:8086/query intext:"influxdb"` | API do InfluxDB | Google | 🟡 |
| `intext:"Welcome to the Solr Admin"` | Console do Apache Solr | Google | 🔴 |

### Fingerprint e artefatos de banco

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"mongodb://localhost" -github` | Referência a MongoDB em conteúdo | Google | 🟡 |
| `intext:"PostgreSQL" "could not connect to server"` | Erro de conexão Postgres | Google | 🟡 |
| `intitle:"index of" "redis.conf"` | Configuração do Redis | Google | 🟡 |
| `intext:"# Redis configuration file" ext:conf` | redis.conf servido como texto | Google | 🟡 |
| `intext:"-- MySQL dump" -site:github.com` | Cabeçalho de dump MySQL em página | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

> A exposição de serviço de banco é o território por excelência de Shodan/Censys/FOFA.

| Intenção | Shodan | Censys | FOFA |
|---|---|---|---|
| Elasticsearch | `product:"Elastic" port:9200` | `host.services.port:9200` | `app="Elasticsearch" && port="9200"` |
| MongoDB | `product:"MongoDB" port:27017` | `host.services.service_name="MONGODB"` | `protocol="mongodb"` |
| Redis | `product:"Redis" port:6379` | `host.services.service_name="REDIS"` | `protocol="redis" && port="6379"` |
| CouchDB | `product:"CouchDB" port:5984` | `host.services.port:5984` | `body="Welcome" && port="5984"` |
| Kibana | `http.title:"Kibana"` | `web.endpoints.http.title:"Kibana"` | `title="Kibana"` |

| Google | Bing |
|---|---|
| `inurl:9200/_cat/indices` | `instreamset:url:9200/_cat/indices` |
| `intitle:"CouchDB" inurl:/_utils/` | `intitle:"CouchDB" inurl:/_utils/` |
| `intext:"Welcome to the Solr Admin"` | `inbody:"Welcome to the Solr Admin"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Endpoint de UI/API de banco por URL — 16 variações

```text
inurl:9200/_cluster/health
inurl:9200/_nodes
inurl:5984/_utils/
inurl:8086/query
inurl:8983/solr/
inurl:7474/browser/
inurl:15672/
inurl:8529/_db/
inurl:2480/studio/index.html
inurl:9000/play
inurl:8123/play
inurl:9090/graph
inurl:5601/app/home
inurl:8086/health
inurl:9000/dashboard
inurl:7473/browser/
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Banco exposto é 🔴: **nunca** consulte sem autorização — mesmo um `GET` já é interação com o alvo.
- Erros de SQL em página (`error in your SQL syntax`) podem indicar **injeção** — o padrão de parâmetro vulnerável fica em **09 · Vulnerabilidades** (Fase 3).
- phpMyAdmin/Adminer/Mongo Express (UI) ficam em [03 · Interfaces de Gerenciamento](../03-infraestrutura-web/interfaces-de-gerenciamento.md); aqui é o **serviço/engine**.
- Dumps `.sql` em diretório ficam em [01 · Dumps de Banco](../01-exposicao-de-arquivos/dumps-de-banco-de-dados.md).

<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [← Servidores Web & App](servidores-web-e-app.md) · [Próximo: DevOps & CI/CD →](devops-e-cicd.md)

</div>
