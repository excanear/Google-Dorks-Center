<div align="center">

[🏠 Hub](../../README.md)

# 📧 E-mail & Webmail

*E-mail tratado como sistema — interfaces de webmail, servidores MX/SMTP/IMAP, arquivos de mensagem (mbox/.eml) e configurações de relay expostas.*

</div>

---

> [!CAUTION]
> Mensagens e caixas de correio são dados pessoais sob a LGPD/GDPR. Identificar um webmail ou um arquivo de e-mail exposto é recon; ler, baixar ou encaminhar conteúdo de terceiros não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🖥 Interfaces de Webmail](webmail-interfaces.md) | OWA, Zimbra, Roundcube, Horde, RainLoop | 🟡 |
| 2 | [📮 Servidores de E-mail](servidores-de-email.md) | Painéis de MTA, Postfix/iRedMail, banners SMTP/IMAP | 🟡 |
| 3 | [🗂 Listas & Arquivos de Mensagem](listas-e-arquivos.md) | mbox/.eml/.pst, arquivos de lista (pipermail) | 🔴 |
| 4 | [⚙ Relay & Configuração](relay-e-config.md) | `main.cf`, dovecot, aliases, teste de relay | 🔴 |

## 🧭 Como usar esta categoria

1. **Webmail** identifica o produto e a versão — pivô para [04 · Tecnologias](../04-tecnologias/README.md) e para CVEs em [09 · Vulnerabilidades](../09-vulnerabilidades/README.md).
2. **Servidores** são melhor caçados por infraestrutura (Shodan/Censys/FOFA): banners de porta 25/465/587/993 dizem o MTA e a versão.
3. **Arquivos de mensagem** (mbox/.eml/.pst) em diretório aberto são **alto risco** — contêm correspondência real. Não abra conteúdo de terceiros; reporte.

## 🚧 Fronteira desta categoria

- **Credenciais de e-mail em arquivo** (`.env`, `SMTP_PASSWORD`, `sasl_passwd` com senha) → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md). Aqui tratamos o **sistema de e-mail**, não o segredo em si.
- **Painel de login genérico** (sem indicar produto de e-mail) → [03 · Infra Web](../03-infraestrutura-web/README.md). Aqui, só webmail identificável.
- **Webhooks de e-mail transacional** (SendGrid/Mailgun API) → [12 · APIs & Webhooks](../12-apis-e-webhooks/README.md).

## 🔗 Categorias relacionadas

- Segredos em arquivo → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md)
- Painéis de login → [03 · Infra Web](../03-infraestrutura-web/README.md)
- Versão de produto e CVE → [09 · Vulnerabilidades](../09-vulnerabilidades/README.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
