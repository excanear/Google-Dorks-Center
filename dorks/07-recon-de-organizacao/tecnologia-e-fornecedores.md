<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [← Presença em Terceiros](presenca-em-terceiros.md)

# 🧩 Tecnologia & Fornecedores

*Descobrir a stack, os SaaS e os fornecedores que uma organização usa — base para mapear dependências e superfície.*

</div>

---

> [!CAUTION]
> Para escopo autorizado. Identificar fornecedores é recon passivo. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### SaaS e serviços hospedados

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:alvo.atlassian.net` | Jira/Confluence da org | Google | 🟡 |
| `site:alvo.slack.com` | Workspace Slack (se indexado) | Google | 🟢 |
| `site:alvo.zendesk.com` | Suporte Zendesk | Google | 🟢 |
| `site:alvo.freshdesk.com` | Suporte Freshdesk | Google | 🟢 |
| `"alvo" site:status.io OR site:statuspage.io` | Página de status (stack/incidentes) | Google | 🟢 |
| `site:alvo.myshopify.com` | Loja Shopify | Google | 🟢 |

### Stack via código/identificadores

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:alvo.com intext:"gtag(" OR intext:"UA-" OR intext:"G-"` | Google Analytics/Tag | Google | 🟢 |
| `site:alvo.com intext:"recaptcha"` | Uso de reCAPTCHA | Google | 🟢 |
| `site:alvo.com intext:"cloudfront.net"` | CDN CloudFront | Google | 🟢 |
| `site:alvo.com intext:"cdn.shopify" OR intext:"wp-content"` | Plataforma de e-commerce/CMS | Google | 🟢 |

### Fornecedores em terceiros

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `"alvo" "case study" (site:aws.amazon.com OR site:cloud.google.com)` | Estudos de caso de cloud | Google | 🟢 |
| `"alvo" "customer" site:*.vendor.com` | Menção como cliente de fornecedor | Google | 🟢 |
| `intext:"alvo.com" "powered by"` | Serviços que a org usa | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Intenção | Google | PublicWWW | BuiltWith/Wappalyzer |
|---|---|---|---|
| Quem usa um ID de analytics | `intext:"UA-XXXXXXX"` | `"UA-XXXXXXX"` | — |
| Tecnologias de um site | `site:alvo.com intext:"wp-content"` | `"wp-content"` | consulta direta por domínio |
| CDN/stack no HTML | `site:alvo.com intext:"cloudfront.net"` | `"cloudfront.net"` | — |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Fornecedor/SaaS por subdomínio de serviço — 10 variações

```text
site:alvo.statuspage.io
site:alvo.gitbook.io
site:alvo.readme.io
site:alvo.helpscoutdocs.com
site:alvo.freshservice.com
site:alvo.intercom.help
site:alvo.document360.io
site:alvo.helpjuice.com
site:alvo.frontapp.com
site:alvo.canny.io
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Subdomínios de SaaS (`alvo.atlassian.net`, `alvo.zendesk.com`) revelam fornecedores sem tocar na org.
- [PublicWWW](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md) acha todos os sites que compartilham um identificador — útil para mapear ativos de um mesmo dono.
- Fingerprint técnico detalhado (versões) fica em [04 · Tecnologias](../04-tecnologias/README.md); aqui o foco é **quais fornecedores/SaaS** a org usa.

<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [← Presença em Terceiros](presenca-em-terceiros.md)

</div>
