<div align="center">

[🏠 Hub](../../README.md)

# 🔌 APIs & Webhooks

*A superfície de API de uma organização — documentação interativa, schemas GraphQL, endpoints versionados, webhooks e coleções do Postman expostas.*

</div>

---

> [!CAUTION]
> Documentação de API exposta não é convite para abusar do endpoint. Mapeie a superfície, reporte o que estiver indevidamente público e **não** envie requisições autenticadas sem autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [📖 Documentação de API](documentacao-de-api.md) | Swagger/OpenAPI, Redoc, API Blueprint | 🟡 |
| 2 | [◼ GraphQL](graphql.md) | `/graphql`, GraphiQL, introspection, playgrounds | 🟡 |
| 3 | [🔑 Endpoints & Chaves](endpoints-e-chaves.md) | Rotas `/api/v1`, chaves em URL, tokens em endpoints | 🔴 |
| 4 | [🪝 Webhooks](webhooks.md) | URLs de webhook Slack/Discord/CI, payloads logados | 🔴 |
| 5 | [📦 Postman & Coleções](postman-e-coletas.md) | Coleções públicas, workspaces, environments | 🟡 |

## 🧭 Como usar esta categoria

1. Comece pela **documentação** (Swagger/GraphQL): ela revela toda a superfície de API de uma vez.
2. A doc lista rotas, parâmetros e modelos de autenticação — pivô para recon de [04 · Tecnologias](../04-tecnologias/README.md) e [03 · Infra Web](../03-infraestrutura-web/README.md).
3. Webhooks e chaves em URL são **alto risco**: um webhook vazado permite injeção de mensagens; uma chave em querystring costuma estar em logs e cache.

## 🚧 Fronteira desta categoria

- **Chave/token dentro de arquivo** (`.env`, config, código) → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md). Aqui tratamos a chave **na superfície de API** (em rota, querystring, webhook).
- **Status pages / actuator / health** → [03 · Infra Web](../03-infraestrutura-web/README.md). Aqui o foco é a **API documentada e seus endpoints**.
- **Repositórios de código com segredos** → [02](../02-credenciais-e-segredos/README.md) e buscadores de código do [manual](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md).

## 🔗 Categorias relacionadas

- Segredos em arquivo → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md)
- Painéis e health checks → [03 · Infra Web](../03-infraestrutura-web/README.md)
- Backends mobile (Firebase/endpoints de app) → [17 · Mobile](../17-mobile/README.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
