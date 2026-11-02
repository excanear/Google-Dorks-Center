<div align="center">

[🏠 Hub](../../README.md) · [📧 E-mail & Webmail](README.md) · [← Listas & Arquivos](listas-e-arquivos.md)

# ⚙ Relay & Configuração

*Arquivos de configuração de MTA (`main.cf`, `dovecot.conf`, aliases) em diretórios abertos e sinais de servidores propensos a open relay.*

</div>

---

> [!CAUTION]
> Config de MTA exposta revela domínios, aliases e, às vezes, segredos. Identificar é recon; testar relay enviando e-mail por servidor de terceiros é abuso. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Arquivos de configuração de MTA

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "main.cf"` | Config principal do Postfix | Google | 🔴 |
| `intitle:"index of" "master.cf"` | Config de serviços do Postfix | Google | 🟡 |
| `intitle:"index of" "dovecot.conf"` | Config do Dovecot (IMAP/POP3) | Google | 🔴 |
| `intitle:"index of" "aliases" "postfix"` | Mapa de aliases do Postfix | Google | 🟡 |
| `filetype:cf intext:"myhostname"` | `main.cf` servido direto | Google | 🔴 |

### Sinais de relay e config de envio

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"550 relay not permitted"` | Banner de rejeição de relay | Google | 🟢 |
| `intext:"Relaying denied" inurl:mail` | Mensagem de relay negado | Google | 🟢 |
| `filetype:ini intext:"SMTP" intext:"port"` | Config SMTP de app em `.ini` | Google | 🟡 |
| `intitle:"index of" "transport" "postfix"` | Tabela de transporte do Postfix | Google | 🟡 |
| `filetype:conf intext:"relayhost"` | Diretiva `relayhost` exposta | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `intitle:"index of" "main.cf"` | `intitle:"index of" "main.cf"` | `"index of" main.cf` |
| `intitle:"index of" "dovecot.conf"` | `intitle:"index of" "dovecot.conf"` | `"index of" dovecot.conf` |
| `filetype:conf intext:"relayhost"` | `ext:conf "relayhost"` | `filetype:conf relayhost` |
| `filetype:ini intext:"SMTP"` | `ext:ini "SMTP"` | `filetype:ini SMTP` |

> **Código-fonte:** `main.cf`/`dovecot.conf` commitados aparecem no GitHub Code Search (`filename:main.cf myhostname`). Segredos dentro deles (`sasl_passwd`) são da [02](../02-credenciais-e-segredos/README.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo de configuração de MTA em diretório aberto — 5 variações

```text
intitle:"index of" "sendmail.cf"
intitle:"index of" "virtual"
intitle:"index of" "transport"
intitle:"index of" "sender_canonical"
intitle:"index of" "mailname"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `main.cf`/`dovecot.conf` expostos revelam a topologia de e-mail do domínio (hostnames, redes confiáveis, aliases) — ótimo recon, mas não contêm, por si, senhas.
- `sasl_passwd` **com valor** é credencial → trate como [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md) e reporte como comprometido.
- Banners "relay not permitted" indicam servidor **bem** configurado; são úteis para mapear MTAs, não vulnerabilidades.
- Nunca verifique open relay enviando e-mail de teste por um servidor que você não administra.

<div align="center">

[🏠 Hub](../../README.md) · [📧 E-mail & Webmail](README.md) · [← Listas & Arquivos](listas-e-arquivos.md)

</div>
