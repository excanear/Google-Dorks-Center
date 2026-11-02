<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [← Endpoints & Chaves](endpoints-e-chaves.md) · [Próximo: Postman & Coleções →](postman-e-coletas.md)

# 🪝 Webhooks

*URLs de webhook de Slack, Discord, Teams e CI vazadas em código/docs, e payloads de webhook logados publicamente.*

</div>

---

> [!CAUTION]
> Uma URL de webhook vazada permite **injetar mensagens** no canal de destino — não a utilize. Trate como segredo comprometido e reporte para rotação. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### URLs de webhook de chat/alerta

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"hooks.slack.com/services/"` | Webhook de entrada do Slack | Google, Bing | 🔴 |
| `intext:"discord.com/api/webhooks/"` | Webhook do Discord | Google | 🔴 |
| `intext:"discordapp.com/api/webhooks/"` | Webhook Discord (domínio antigo) | Google | 🔴 |
| `inurl:"outlook.office.com/webhook/"` | Webhook do Microsoft Teams | Google | 🔴 |
| `intext:"hooks.zapier.com/hooks/catch/"` | Webhook de automação Zapier | Google | 🟡 |

### Webhooks em arquivos de config/CI

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:yml intext:"hooks.slack.com"` | Webhook Slack em pipeline/config | Google | 🔴 |
| `filetype:env intext:"WEBHOOK_URL"` | Variável de webhook em `.env` | Google | 🔴 |
| `inurl:/.github/workflows intext:"webhook"` | Webhook em GitHub Actions | Google | 🟡 |
| `filetype:json intext:"webhookUrl"` | Config JSON com URL de webhook | Google | 🔴 |

### Payloads e receivers de webhook

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/webhook intext:"X-Hub-Signature"` | Receiver verificando assinatura GitHub | Google | 🟡 |
| `inurl:/webhooks/ intitle:"index of"` | Diretório de payloads exposto | Google | 🔴 |
| `intext:"payload" inurl:/webhook filetype:log` | Log de payloads de webhook | Google | 🔴 |
| `inurl:/api/webhooks intext:"event"` | Endpoint receptor de eventos | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `intext:"hooks.slack.com/services/"` | `"hooks.slack.com/services/"` | `"hooks.slack.com/services/"` |
| `intext:"discord.com/api/webhooks/"` | `"discord.com/api/webhooks/"` | `"discord.com/api/webhooks/"` |
| `filetype:env intext:"WEBHOOK_URL"` | `ext:env "WEBHOOK_URL"` | `filetype:env WEBHOOK_URL` |
| `inurl:/webhooks/ intitle:"index of"` | `instreamset:url:/webhooks/ intitle:"index of"` | `inurl:webhooks "index of"` |

> **Código-fonte:** webhooks vazam muito em repositórios — GitHub Code Search (`"hooks.slack.com/services/"`), grep.app e PublicWWW pegam o que os buscadores web não indexam. Veja o [manual de código](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** URL de webhook por host — 5 variações

```text
intext:"outlook.office.com/webhook/"
intext:"maker.ifttt.com/trigger/"
intext:"webhook.site/"
intext:"hooks.integromat.com/"
intext:"hook.us1.make.com/"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Webhook do Slack/Discord na forma completa (`.../services/T.../B.../xxxx`) é **credencial funcional** — qualquer um com a URL posta no canal. Nunca teste enviando mensagem.
- Muito resultado vem de **tutoriais e exemplos** com URLs fictícias; confira se o token parece real antes de reportar.
- O par "webhook + segredo de assinatura" (`X-Hub-Signature`, `webhook secret`) também pertence a [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md) quando está em arquivo; aqui o foco é a **URL de webhook em si**.
- Payloads logados (`filetype:log`) podem conter dados de eventos reais — respeite a fronteira de dados pessoais.

<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [← Endpoints & Chaves](endpoints-e-chaves.md) · [Próximo: Postman & Coleções →](postman-e-coletas.md)

</div>
