<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [← .htpasswd & Auth Básica](htpasswd-e-auth-basica.md)

# 🖥 Secrets em Frontend & JS

*Chaves e segredos embutidos em JavaScript de cliente, bundles e configs públicas — expostos por desenho, mas frequentemente sensíveis demais para o front.*

</div>

---

> [!CAUTION]
> Nem todo segredo em JS é vazamento (chaves públicas existem), mas muitos são credenciais que nunca deveriam sair do servidor. Avalie o contexto e reporte os que forem sensíveis. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Firebase e Google no cliente

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"firebaseConfig" "apiKey"` | Bloco de config do Firebase | Google | 🟡 |
| `ext:js "apiKey:" "authDomain:" "projectId:"` | Config Firebase em JS | Google | 🟡 |
| `intext:"databaseURL" "firebaseio.com"` | URL de Realtime Database | Google | 🔴 |
| `ext:js "AIza"` | API key do Google embutida em JS | Google | 🟡 |

### Chaves de serviço em JS

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:js "pk_live_"` | Publishable key do Stripe (pública) | Google | 🟢 |
| `ext:js "sk_live_"` | ⚠ Secret key do Stripe no front (grave) | Google | 🔴 |
| `ext:js "access_token" "bearer"` | Token de acesso embutido | Google | 🔴 |
| `ext:js "aws_access_key_id"` | Credencial AWS em JS | Google | 🔴 |
| `ext:js "apikey" "sendgrid"` | Chave SendGrid em JS | Google | 🔴 |

### Comentários e arquivos de build

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:js "TODO" "password"` | Senha em comentário de JS | Google | 🟡 |
| `inurl:main.js "secret"` | Bundle principal com "secret" | Google | 🟡 |
| `inurl:/static/js/ "apiKey"` | Chave em bundle de build React | Google | 🟡 |
| `ext:map "sourcesContent" "password"` | Source map vazando código com senha | Google | 🔴 |
| `inurl:.js.map "secret"` | Source maps expostos | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | PublicWWW / GitHub |
|---|---|---|---|
| `intext:"firebaseConfig" "apiKey"` | `"firebaseConfig" "apiKey"` | `"firebaseConfig" apiKey` | PublicWWW: `"firebaseConfig"` |
| `ext:js "sk_live_"` | `ext:js "sk_live_"` | `filetype:js "sk_live_"` | GitHub: `/sk_live_[0-9a-zA-Z]{24}/ language:javascript` |
| `ext:js "AIza"` | `ext:js "AIza"` | `filetype:js "AIza"` | GitHub: `/AIza[0-9A-Za-z_\-]{35}/` |
| `inurl:/static/js/ "apiKey"` | `instreamset:url:/static/js/ apiKey` | `inurl:static/js apiKey` | PublicWWW: `"apiKey"` |
| `inurl:.js.map "secret"` | `instreamset:url:.js.map secret` | `inurl:.js.map secret` | — |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Segredo/campo sensível embutido em JavaScript de cliente — 8 variações

```text
ext:js intext:"apiKey"
ext:js intext:"api_key"
ext:js intext:"access_token"
ext:js intext:"authToken"
ext:js intext:"firebaseConfig"
ext:js intext:"databaseURL"
ext:js intext:"x-api-key"
ext:js intext:"bearer "
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Chaves públicas por desenho:** `pk_live_` (Stripe), `apiKey` do Firebase (protegida por regras do projeto) e `AIza` restrita por referer **não** são vazamento por si só — o risco está na má configuração por trás.
- **`sk_live_`, tokens de acesso e chaves AWS em JS são sempre graves** — não deveriam existir no cliente.
- **Source maps** (`.js.map` com `sourcesContent`) reconstroem o código original, incluindo segredos inlined.
- [PublicWWW](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md) busca no HTML/JS servido e acha identificadores por todo o índice; útil para medir difusão de uma chave.

<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [← .htpasswd & Auth Básica](htpasswd-e-auth-basica.md)

</div>
