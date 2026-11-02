<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [Próximo: Tokens de API →](tokens-de-api.md)

# 🌱 Variáveis de Ambiente (.env)

*Arquivos `.env` e variantes servidos como texto: a fonte número um de vazamento de segredos em aplicações web modernas.*

</div>

---

> [!CAUTION]
> Um `.env` exposto costuma conter **todas** as credenciais da aplicação de uma vez (banco, e-mail, nuvem, tokens). Localize e reporte para rotação; não use. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Arquivos `.env` em diretórios abertos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ".env"` | `.env` em diretório listável | Google, Bing | 🔴 |
| `intitle:"index of" ".env.local"` | Ambiente local exposto | Google | 🔴 |
| `intitle:"index of" ".env.production"` | Ambiente de produção exposto | Google | 🔴 |
| `inurl:/.env -intitle:"index of"` | `.env` servido diretamente | Google | 🔴 |
| `inurl:.env.bak` | Cópia de backup do `.env` | Google | 🔴 |
| `inurl:.env.save` | `.env` salvo por editor | Google | 🔴 |

### `.env` por conteúdo (servido como texto)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:env "APP_KEY"` | `.env` de Laravel (APP_KEY) | Google | 🔴 |
| `ext:env "DB_PASSWORD"` | Credencial de banco no `.env` | Google | 🔴 |
| `ext:env "DB_HOST" "DB_USERNAME"` | Bloco de banco do `.env` | Google | 🔴 |
| `ext:env "MAIL_PASSWORD"` | Credencial de e-mail | Google | 🔴 |
| `ext:env "AWS_SECRET_ACCESS_KEY"` | Chave AWS no `.env` | Google | 🔴 |
| `ext:env "STRIPE_SECRET_KEY"` | Chave Stripe no `.env` | Google | 🔴 |
| `ext:env "REDIS_PASSWORD"` | Senha do Redis | Google | 🔴 |
| `ext:env "JWT_SECRET"` | Segredo de assinatura JWT | Google | 🔴 |

### Variantes de framework

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ".env.example" -github` | Exemplo que pode ter valores reais | Google | 🟡 |
| `inurl:/storage/.env` | `.env` dentro de /storage (Laravel) | Google | 🔴 |
| `inurl:/config/.env` | `.env` em /config | Google | 🔴 |
| `inurl:/.env.dev OR inurl:/.env.staging` | Ambientes não-produtivos | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Yandex | GitHub Code Search |
|---|---|---|---|---|
| `intitle:"index of" ".env"` | `intitle:"index of" ".env"` | `intitle:"index of" ".env"` | `title:"index of" ".env"` | `path:.env` |
| `ext:env "DB_PASSWORD"` | `ext:env "DB_PASSWORD"` | `filetype:env "DB_PASSWORD"` | `mime:env "DB_PASSWORD"` | `path:.env DB_PASSWORD` |
| `ext:env "APP_KEY"` | `ext:env "APP_KEY"` | `filetype:env "APP_KEY"` | `mime:env "APP_KEY"` | `path:.env APP_KEY` |
| `ext:env "AWS_SECRET_ACCESS_KEY"` | `ext:env "AWS_SECRET_ACCESS_KEY"` | `filetype:env AWS_SECRET_ACCESS_KEY` | `mime:env "AWS_SECRET_ACCESS_KEY"` | `path:.env AWS_SECRET_ACCESS_KEY` |
| `inurl:/.env` | `instreamset:url:/.env` | `inurl:.env` | `url:/.env` | `path:.env` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo .env e variantes em diretório aberto — 12 variações

```text
intitle:"index of" ".env.dev"
intitle:"index of" ".env.development"
intitle:"index of" ".env.staging"
intitle:"index of" ".env.prod"
intitle:"index of" ".env.test"
intitle:"index of" ".env.backup"
intitle:"index of" ".env.bak"
intitle:"index of" ".env.save"
intitle:"index of" ".env.old"
intitle:"index of" ".env.dist"
intitle:"index of" ".env.default"
intitle:"index of" ".env.php"
```

> **Padrão:** Variável de segredo dentro de .env (servido como texto) — 22 variações

```text
ext:env intext:"DB_PASSWORD"
ext:env intext:"DB_PASS"
ext:env intext:"DATABASE_PASSWORD"
ext:env intext:"MYSQL_PASSWORD"
ext:env intext:"MYSQL_ROOT_PASSWORD"
ext:env intext:"POSTGRES_PASSWORD"
ext:env intext:"REDIS_PASSWORD"
ext:env intext:"MAIL_PASSWORD"
ext:env intext:"SMTP_PASSWORD"
ext:env intext:"APP_KEY"
ext:env intext:"APP_SECRET"
ext:env intext:"JWT_SECRET"
ext:env intext:"SECRET_KEY"
ext:env intext:"SESSION_SECRET"
ext:env intext:"AWS_SECRET_ACCESS_KEY"
ext:env intext:"STRIPE_SECRET_KEY"
ext:env intext:"TWILIO_AUTH_TOKEN"
ext:env intext:"MAILGUN_API_KEY"
ext:env intext:"OPENAI_API_KEY"
ext:env intext:"GITHUB_TOKEN"
ext:env intext:"SENTRY_AUTH_TOKEN"
ext:env intext:"ENCRYPTION_KEY"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **`.env.example`/`.env.dist`/`.env.sample`** são intencionais e quase sempre inofensivos (valores `placeholder`). Mantidos só com risco 🟡.
- O conteúdo do `.env` só aparece quando o servidor o entrega como **texto**; muitas stacks bloqueiam `.env` por padrão (retornam 403), então grande parte dos achados é o **nome** no directory listing.
- Tutoriais de Laravel/Node citam `DB_PASSWORD`/`APP_KEY` como exemplo — filtre por `site:` do alvo para confirmar exposição real.
- Em código-fonte, prefira o GitHub Code Search: `.env` costuma ser *gitignored*, mas commits antigos e repositórios de exemplo vazam.

<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [Próximo: Tokens de API →](tokens-de-api.md)

</div>
