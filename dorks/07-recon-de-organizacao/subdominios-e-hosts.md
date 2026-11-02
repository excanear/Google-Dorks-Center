<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [Próximo: E-mails & Pessoas →](emails-e-pessoas.md)

# 🌍 Subdomínios & Hosts

*Enumerar a superfície de uma organização: subdomínios, ambientes e hosts relacionados.*

</div>

---

> [!CAUTION]
> Para escopo autorizado. Enumerar por buscador é passivo; varrer/conectar nos hosts é interação. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Enumeração por `site:`

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:*.alvo.com -www` | Todos os subdomínios menos o www | Google | 🟢 |
| `site:*.alvo.com -www -mail -shop` | Subdomínios menos os óbvios | Google | 🟢 |
| `site:*.*.alvo.com` | Subdomínios de segundo nível | Google | 🟢 |
| `site:alvo.com -site:www.alvo.com` | Conteúdo fora do www | Google | 🟢 |
| `site:alvo.com inurl:dev OR inurl:staging OR inurl:test` | Ambientes não-produtivos | Google | 🟡 |
| `site:alvo.com inurl:api OR inurl:admin OR inurl:internal` | Hosts sensíveis | Google | 🟡 |

### Ambientes e hosts específicos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:dev.alvo.com OR site:staging.alvo.com` | Dev/staging diretos | Google | 🟡 |
| `site:vpn.alvo.com OR site:remote.alvo.com` | Acesso remoto | Google | 🟡 |
| `site:jira.alvo.com OR site:confluence.alvo.com` | Ferramentas internas | Google | 🟡 |
| `site:gitlab.alvo.com OR site:git.alvo.com` | Git self-hosted | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Intenção | Google | Yandex | Fonte passiva |
|---|---|---|---|
| Subdomínios | `site:*.alvo.com` | `rhost:com.alvo.*` | crt.sh (Certificate Transparency) |
| URLs históricas | — | — | Wayback CDX: `cdx/search/cdx?url=alvo.com*&fl=original&collapse=urlkey` |
| URLs em massa | — | — | Common Crawl index: `?url=alvo.com*&output=json` |
| Host por cert | — | — | Censys: `host.services.tls.certificates.leaf_data.subject.common_name:alvo.com` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Host/subdomínio sensível de alvo autorizado — 36 variações

```text
site:alvo.com inurl:dev
site:alvo.com inurl:staging
site:alvo.com inurl:test
site:alvo.com inurl:qa
site:alvo.com inurl:uat
site:alvo.com inurl:api
site:alvo.com inurl:admin
site:alvo.com inurl:internal
site:alvo.com inurl:intranet
site:alvo.com inurl:vpn
site:alvo.com inurl:remote
site:alvo.com inurl:mail
site:alvo.com inurl:webmail
site:alvo.com inurl:portal
site:alvo.com inurl:app
site:alvo.com inurl:beta
site:alvo.com inurl:demo
site:alvo.com inurl:cdn
site:alvo.com inurl:assets
site:alvo.com inurl:git
site:alvo.com inurl:jenkins
site:alvo.com inurl:gitlab
site:alvo.com inurl:jira
site:alvo.com inurl:confluence
site:alvo.com inurl:sonar
site:alvo.com inurl:grafana
site:alvo.com inurl:kibana
site:alvo.com inurl:vault
site:alvo.com inurl:sso
site:alvo.com inurl:auth
site:alvo.com inurl:dashboard
site:alvo.com inurl:monitor
site:alvo.com inurl:backup
site:alvo.com inurl:ftp
site:alvo.com inurl:proxy
site:alvo.com inurl:status
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `site:*.alvo.com` pode não listar **todos** os subdomínios (só os indexados) — combine com crt.sh, Wayback CDX e Censys por certificado.
- Troque `alvo.com` pelo domínio **autorizado**. Sem escopo, isto é pesquisa, não recon de um alvo.
- Subdomínios de dev/staging são 🟡 por tenderem a ter menos proteção — mas o achado é só o mapa, não a exploração.

<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [Próximo: E-mails & Pessoas →](emails-e-pessoas.md)

</div>
