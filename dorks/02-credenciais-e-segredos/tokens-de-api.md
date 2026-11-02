<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [← Variáveis de Ambiente](variaveis-de-ambiente-env.md) · [Próximo: Senhas em Config & Código →](senhas-em-configuracao-e-codigo.md)

# 🎟 Tokens de API

*Chaves e tokens de API por provedor, identificados pelos prefixos reais de cada serviço (verificados em 2026-11).*

</div>

---

> [!CAUTION]
> Um token vazado dá acesso programático à conta do provedor. **Reporte para revogação**; nunca autentique com ele. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Cloud (AWS, GCP, Azure)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"AKIA" ext:env` | Access key ID da AWS em `.env` | Google | 🔴 |
| `intext:"AKIA" ext:txt "aws_secret_access_key"` | Par de chaves AWS em texto | Google | 🔴 |
| `ext:json "aws_access_key_id" "aws_secret_access_key"` | Credenciais AWS em JSON | Google | 🔴 |
| `intext:"AIza" ext:json` | API key do Google em JSON | Google | 🔴 |
| `inurl:/credentials "aws_access_key_id"` | Arquivo de credenciais AWS CLI | Google | 🔴 |
| `ext:env "AZURE_CLIENT_SECRET"` | Secret de app registration do Azure | Google | 🔴 |

### Pagamentos (Stripe, PayPal)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"sk_live_" ext:env` | Chave secreta de produção do Stripe | Google | 🔴 |
| `intext:"sk_live_" ext:js` | Chave Stripe exposta em JS | Google | 🔴 |
| `intext:"rk_live_" -test` | Restricted key do Stripe (produção) | Google | 🔴 |
| `ext:env "PAYPAL_CLIENT_SECRET"` | Secret do PayPal | Google | 🔴 |

### Mensageria e e-mail (Slack, SendGrid, Twilio, Mailgun)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"xoxb-" ext:txt` | Bot token do Slack | Google | 🔴 |
| `intext:"xoxp-"` | User token do Slack | Google | 🔴 |
| `inurl:hooks.slack.com/services` | Webhook de entrada do Slack | Google | 🔴 |
| `intext:"SG." ext:env "SENDGRID"` | API key do SendGrid | Google | 🔴 |
| `ext:env "TWILIO_AUTH_TOKEN"` | Auth token do Twilio | Google | 🔴 |
| `ext:env "MAILGUN_API_KEY"` | API key do Mailgun | Google | 🔴 |

### Dev, Git e IA (GitHub, GitLab, OpenAI)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"ghp_" ext:env` | Personal access token do GitHub | Google | 🔴 |
| `intext:"github_pat_"` | Fine-grained PAT do GitHub | Google | 🔴 |
| `intext:"glpat-" ext:yml` | PAT do GitLab em YAML de CI | Google | 🔴 |
| `intext:"sk-proj-" ext:env` | API key de projeto da OpenAI | Google | 🔴 |
| `ext:env "OPENAI_API_KEY"` | Variável de chave da OpenAI | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | GitHub Code Search |
|---|---|---|---|
| `intext:"AKIA" ext:env` | `"AKIA" ext:env` | `"AKIA" filetype:env` | `/AKIA[0-9A-Z]{16}/` |
| `intext:"sk_live_" ext:env` | `"sk_live_" ext:env` | `"sk_live_" filetype:env` | `/sk_live_[0-9a-zA-Z]{24}/` |
| `intext:"ghp_" ext:env` | `"ghp_" ext:env` | `"ghp_" filetype:env` | `/ghp_[0-9A-Za-z]{36}/` |
| `intext:"xoxb-" ext:txt` | `"xoxb-" ext:txt` | `"xoxb-" filetype:txt` | `/xoxb-[0-9A-Za-z-]+/` |
| `intext:"AIza" ext:json` | `"AIza" ext:json` | `"AIza" filetype:json` | `/AIza[0-9A-Za-z_\-]{35}/` |
| `inurl:hooks.slack.com/services` | `instreamset:url:hooks.slack.com/services` | `inurl:hooks.slack.com/services` | `content:hooks.slack.com/services` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Prefixo de token real × arquivo de ambiente/config — 65 variações

```text
intext:"AKIA" ext:txt
intext:"AKIA" ext:json
intext:"AKIA" ext:yml
intext:"AKIA" ext:log
intext:"AKIA" ext:cfg
intext:"ASIA" ext:env
intext:"ASIA" ext:txt
intext:"ASIA" ext:json
intext:"ASIA" ext:yml
intext:"ASIA" ext:log
intext:"ASIA" ext:cfg
intext:"AIza" ext:env
intext:"AIza" ext:txt
intext:"AIza" ext:yml
intext:"AIza" ext:log
intext:"AIza" ext:cfg
intext:"sk_live_" ext:txt
intext:"sk_live_" ext:json
intext:"sk_live_" ext:yml
intext:"sk_live_" ext:log
intext:"sk_live_" ext:cfg
intext:"rk_live_" ext:env
intext:"rk_live_" ext:txt
intext:"rk_live_" ext:json
intext:"rk_live_" ext:yml
intext:"rk_live_" ext:log
intext:"rk_live_" ext:cfg
intext:"xoxb-" ext:env
intext:"xoxb-" ext:json
intext:"xoxb-" ext:yml
intext:"xoxb-" ext:log
intext:"xoxb-" ext:cfg
intext:"xoxp-" ext:env
intext:"xoxp-" ext:txt
intext:"xoxp-" ext:json
intext:"xoxp-" ext:yml
intext:"xoxp-" ext:log
intext:"xoxp-" ext:cfg
intext:"ghp_" ext:txt
intext:"ghp_" ext:json
intext:"ghp_" ext:yml
intext:"ghp_" ext:log
intext:"ghp_" ext:cfg
intext:"github_pat_" ext:env
intext:"github_pat_" ext:txt
intext:"github_pat_" ext:json
intext:"github_pat_" ext:yml
intext:"github_pat_" ext:log
intext:"github_pat_" ext:cfg
intext:"glpat-" ext:env
intext:"glpat-" ext:txt
intext:"glpat-" ext:json
intext:"glpat-" ext:log
intext:"glpat-" ext:cfg
intext:"SG." ext:env
intext:"SG." ext:txt
intext:"SG." ext:json
intext:"SG." ext:yml
intext:"SG." ext:log
intext:"SG." ext:cfg
intext:"sk-proj-" ext:txt
intext:"sk-proj-" ext:json
intext:"sk-proj-" ext:yml
intext:"sk-proj-" ext:log
intext:"sk-proj-" ext:cfg
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Prefixos verificados em 2026-11** (fontes: listas públicas de secret scanning; confirme na doc do provedor antes de uso crítico):
  - AWS `AKIA`/`ASIA`/`ABIA`/`ACCA` · GCP `AIza` · Slack `xox[baprs]-` · GitHub `ghp_`/`gho_`/`ghu_`/`ghs_`/`ghr_`/`github_pat_` · GitLab `glpat-` · Stripe `sk_live_`/`sk_test_`/`rk_live_`/`pk_live_` · SendGrid `SG.` · OpenAI `sk-proj-`/`sk-svcacct-`/`sk-admin-` (legado `sk-`) · Twilio `AC…`.
- **Chaves públicas** (`pk_live_` do Stripe, `AIza` de Maps restrita por referer) existem para uso client-side e **não** são necessariamente vazamento — avalie o contexto.
- **Exemplos de documentação** usam tokens falsos (`sk_live_xxx`, `AKIAIOSFODNN7EXAMPLE`). Confirme que o valor é real antes de reportar.
- O **GitHub Code Search com regex** é a ferramenta mais eficaz aqui; busque o padrão completo do token, não só o prefixo.
- Chaves privadas, keystores e service-account JSON completos ficam em [01 · Chaves & Certificados](../01-exposicao-de-arquivos/chaves-e-certificados.md).

<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [← Variáveis de Ambiente](variaveis-de-ambiente-env.md) · [Próximo: Senhas em Config & Código →](senhas-em-configuracao-e-codigo.md)

</div>
