<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [← GraphQL](graphql.md) · [Próximo: Webhooks →](webhooks.md)

# 🔑 Endpoints & Chaves na Superfície

*Rotas versionadas (`/api/v1`), chaves e tokens carregados na URL/querystring, e endpoints de API indexados por engano.*

</div>

---

> [!CAUTION]
> Chave em querystring quase sempre acaba em log de servidor, proxy e cache de buscador. Tratar uma chave encontrada como comprometida e **reportar** é a conduta correta; usá-la não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Rotas de API versionadas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/api/v1` | Superfície REST versionada | Google | 🟡 |
| `inurl:/api/v2` | API v2 indexada | Google | 🟡 |
| `inurl:/rest/ intext:"api"` | Endpoints REST genéricos | Google | 🟡 |
| `inurl:/api/ intitle:"index of"` | Diretório de API aberto | Google | 🟡 |

### Chaves e tokens na URL

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:"api_key="` | API key passada em querystring | Google | 🔴 |
| `inurl:"apikey="` | Variante sem underscore | Google | 🔴 |
| `inurl:"access_token="` | Token OAuth em URL | Google | 🔴 |
| `inurl:"auth_token="` | Token de autenticação em URL | Google | 🔴 |
| `inurl:"client_secret="` | Segredo OAuth client em URL | Google | 🔴 |
| `inurl:"?token=" inurl:/api` | Token em endpoint de API | Google | 🔴 |

### Respostas de API indexadas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/api intext:"access_token"` | JSON de token indexado | Google | 🔴 |
| `inurl:/api intext:"api_key"` | JSON com chave indexado | Google | 🔴 |
| `filetype:json inurl:api intext:"secret"` | Resposta JSON com segredo | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `inurl:/api/v1` | `instreamset:url:/api/v1` | `inurl:api/v1` |
| `inurl:"api_key="` | `instreamset:url:"api_key="` | `inurl:api_key=` |
| `inurl:"access_token="` | `instreamset:url:"access_token="` | `inurl:access_token=` |
| `inurl:/wp-json/wp/v2/users` | `instreamset:url:/wp-json/wp/v2/users` | `inurl:wp-json/wp/v2/users` |

> **Código-fonte:** chaves em código versionado se caçam melhor nos buscadores de código (GitHub Code Search, grep.app) — veja o [manual de código](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md). Aqui tratamos a chave **na URL pública**.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Chave/token carregado na querystring — 6 variações

```text
inurl:"token="
inurl:"x-api-key="
inurl:"auth="
inurl:"bearer="
inurl:"session_token="
inurl:"id_token="
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Chave em `inurl:` tem **alta taxa de positivo real** mas também de exemplos de documentação (`api_key=YOUR_KEY`). Olhe o valor: se parece real, trate como comprometido e reporte.
- `*/wp-json/wp/v2/users` lista logins de WordPress — útil para recon, mas é dado pessoal; respeite a [fronteira ética](../../README.md#-aviso-de-uso-legal-e-ético).
- Chave **em arquivo** (`.env`, `config.php`) é da [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md); aqui ficam só as que vazam **na própria URL/resposta da API**.
- `access_token` em URL costuma ser de curta validade, mas basta estar vivo no cache para ser um incidente.

<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [← GraphQL](graphql.md) · [Próximo: Webhooks →](webhooks.md)

</div>
