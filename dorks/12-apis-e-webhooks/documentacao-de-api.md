<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [Próximo: GraphQL →](graphql.md)

# 📖 Documentação de API

*Swagger UI, OpenAPI/JSON schemas, Redoc e API Blueprint expostos — a planta completa da API em uma página.*

</div>

---

> [!CAUTION]
> A doc revela rotas, parâmetros e esquema de autenticação. Use para mapear a superfície e reportar exposição indevida; não dispare requisições autenticadas sem autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Swagger UI

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:swagger-ui.html` | Swagger UI clássico (springfox) | Google, Bing | 🟡 |
| `inurl:/swagger-ui/index.html` | Swagger UI (springdoc) | Google | 🟡 |
| `intitle:"Swagger UI"` | Qualquer instância Swagger UI | Google, Bing | 🟡 |
| `inurl:/swagger/index.html` | Swashbuckle (.NET) | Google | 🟡 |
| `inurl:swagger intitle:"Swagger UI"` | Swagger UI por caminho e título | Google | 🟡 |

### Schemas OpenAPI / JSON

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/v2/api-docs` | Schema OpenAPI 2 (springfox) | Google | 🟡 |
| `inurl:/v3/api-docs` | Schema OpenAPI 3 (springdoc) | Google | 🟡 |
| `inurl:openapi.json` | Schema OpenAPI servido como JSON | Google | 🟡 |
| `inurl:swagger.json` | Schema Swagger bruto | Google | 🟡 |
| `filetype:yaml inurl:openapi` | Schema OpenAPI em YAML | Google | 🟡 |

### Outros geradores de doc

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"ReDoc"` | Documentação Redoc | Google | 🟡 |
| `inurl:/redoc` | Caminho Redoc | Google | 🟡 |
| `intitle:"API Documentation" inurl:/docs` | Portal de docs de API | Google | 🟢 |
| `inurl:/rapidoc` | RapiDoc viewer | Google | 🟡 |
| `intext:"Powered by Slate"` | Docs estáticas Slate | Google | 🟢 |
| `inurl:apiblueprint OR ext:apib` | API Blueprint fonte | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `inurl:swagger-ui.html` | `instreamset:url:swagger-ui.html` | `inurl:swagger-ui.html` |
| `intitle:"Swagger UI"` | `intitle:"Swagger UI"` | `intitle:"Swagger UI"` |
| `inurl:/v3/api-docs` | `instreamset:url:/v3/api-docs` | `inurl:api-docs` |
| `inurl:openapi.json` | `instreamset:url:openapi.json` | `inurl:openapi.json` |
| `intitle:"ReDoc"` | `intitle:"ReDoc"` | `intitle:ReDoc` |

> **Infraestrutura (FOFA/Shodan):** no FOFA, `body="swagger-ui"` ou `title="Swagger UI"`; no Shodan, `http.title:"Swagger UI"` e `http.html:"swagger-ui"` encontram instâncias fora do índice dos buscadores web. Veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Rota de documentação de API indexada — 6 variações

```text
inurl:/swagger.json
inurl:/swagger/v1/swagger.json
inurl:/api/swagger.json
inurl:/docs/swagger.json
inurl:/api/swagger-ui.html
inurl:/swagger/ui
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Muita doc de API é **pública de propósito** (APIs de produto). O achado interessante é a doc de API **interna/privada** exposta por engano — procure rotas administrativas, ambientes `staging`/`dev` e títulos de produto interno.
- `*/v2/api-docs` e `*/v3/api-docs` entregam o **JSON cru** — mais fácil de parsear que a UI, e às vezes exposto sem a UI.
- A doc lista o **esquema de autenticação** (Bearer, API key, OAuth) — isso é recon, não acesso. Token/chave em arquivo fica em [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).
- Combine com `site:` para focar um alvo autorizado; combine com `-site:github.com` para tirar ruído de repositórios.

<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [Próximo: GraphQL →](graphql.md)

</div>
