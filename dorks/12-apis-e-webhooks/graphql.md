<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [← Documentação de API](documentacao-de-api.md) · [Próximo: Endpoints & Chaves →](endpoints-e-chaves.md)

# ◼ GraphQL

*Endpoints `/graphql`, consoles GraphiQL/Playground e schemas expostos por introspection.*

</div>

---

> [!CAUTION]
> Um endpoint GraphQL com introspection habilitada entrega o schema inteiro. Mapear o schema é recon; executar mutations ou consultas pesadas sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Endpoints e consoles

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/graphiql` | Console GraphiQL interativo | Google | 🟡 |
| `intitle:"GraphiQL"` | GraphiQL por título | Google | 🟡 |
| `intitle:"GraphQL Playground"` | Apollo/Prisma Playground | Google | 🟡 |
| `inurl:/v1/graphql` | Endpoint GraphQL versionado (Hasura) | Google | 🟡 |
| `inurl:/console intext:"Hasura"` | Console administrativo Hasura | Google | 🔴 |

### Pistas de schema e introspection

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"__schema" inurl:graphql` | Resposta de introspection indexada | Google | 🟡 |
| `intext:"query { __typename }"` | Ping GraphQL documentado | Google | 🟢 |
| `inurl:graphql intext:"mutation"` | Doc expondo mutations | Google | 🟡 |
| `ext:graphql OR ext:gql` | Arquivos de schema `.graphql` | Google | 🟡 |
| `inurl:/graphql intext:"StackblitzStack"` | Playground embutido | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `inurl:/graphql` | `instreamset:url:/graphql` | `inurl:graphql` |
| `intitle:"GraphiQL"` | `intitle:"GraphiQL"` | `intitle:GraphiQL` |
| `intitle:"GraphQL Playground"` | `intitle:"GraphQL Playground"` | `intitle:"GraphQL Playground"` |
| `ext:graphql` | `ext:graphql` | `filetype:graphql` |
| `inurl:/v1/graphql` | `instreamset:url:/v1/graphql` | `inurl:v1/graphql` |

> **Infraestrutura:** Shodan `http.html:"GraphiQL"` ou `http.title:"GraphQL Playground"`; FOFA `body="graphiql"`. Encontram consoles sem link indexado.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Caminho GraphQL/console por rota — 7 variações

```text
inurl:/api/graphql
inurl:/graphql/console
inurl:/subscriptions
inurl:/altair
inurl:/voyager
inurl:/playground
inurl:/query
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Introspection** habilitada em produção é má configuração comum — entrega todo o schema (tipos, campos, mutations). Isso é o achado; a exploração de cada mutation exige autorização.
- Consoles **Hasura/Apollo** com permissões frouxas podem expor dados — o console em si é o indicador de risco.
- `/graphql` responde a `GET` em muitos frameworks; o que indexa nos buscadores costuma ser a **página do console**, não o endpoint JSON.
- GraphQL é frequentemente a camada sobre o mesmo banco da API REST — cruze com [documentação de API](documentacao-de-api.md).

<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [← Documentação de API](documentacao-de-api.md) · [Próximo: Endpoints & Chaves →](endpoints-e-chaves.md)

</div>
