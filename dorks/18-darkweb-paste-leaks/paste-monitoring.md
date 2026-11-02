<div align="center">

[🏠 Hub](../../README.md) · [🕵 Dark Web, Paste & Leaks](README.md) · [Próximo: Mirrors & Índices →](mirrors-e-indices.md)

# 📋 Monitoramento de Paste

*Descobrir se o SEU domínio foi mencionado em paste sites (pastebin, paste.ee, rentry, controlc) — monitoramento defensivo, ancorado em `{seu_dominio}`.*

</div>

---

> [!CAUTION]
> Todo dork aqui é ancorado em `{seu_dominio}` — o domínio que você administra ou está autorizado a proteger. O objetivo é **detectar sua própria exposição**, não vasculhar pastes de terceiros. Ao achar algo, contenha e reporte. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Menções do seu domínio em paste sites

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:pastebin.com "{seu_dominio}"` | Seu domínio citado no Pastebin | Google | 🟡 |
| `site:paste.ee "{seu_dominio}"` | Seu domínio no paste.ee | Google | 🟡 |
| `site:rentry.co "{seu_dominio}"` | Seu domínio no rentry | Google | 🟡 |
| `site:controlc.com "{seu_dominio}"` | Seu domínio no controlc | Google | 🟡 |
| `site:justpaste.it "{seu_dominio}"` | Seu domínio no justpaste.it | Google | 🟡 |

### Sinais de credencial do seu domínio em paste

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:pastebin.com "@{seu_dominio}" intext:"password"` | E-mails do seu domínio + senha em paste | Google | 🔴 |
| `site:pastebin.com "{seu_dominio}" intext:"BEGIN RSA PRIVATE KEY"` | Chave privada do seu domínio em paste | Google | 🔴 |
| `site:paste.ee "@{seu_dominio}" intext:"login"` | Logins do seu domínio em paste | Google | 🔴 |
| `"{seu_dominio}" inurl:pastebin.com intext:"dump"` | Dump citando seu domínio | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `site:pastebin.com "{seu_dominio}"` | `site:pastebin.com "{seu_dominio}"` | `site:pastebin.com {seu_dominio}` |
| `site:paste.ee "{seu_dominio}"` | `site:paste.ee "{seu_dominio}"` | `site:paste.ee {seu_dominio}` |
| `site:rentry.co "{seu_dominio}"` | `site:rentry.co "{seu_dominio}"` | `site:rentry.co {seu_dominio}` |

> **Automação defensiva:** serviços como o próprio alerta do Pastebin Pro e o HaveIBeenPwned (domain search) fazem esse monitoramento de forma contínua e legal — veja o [manual de metodologia & OPSEC](../../docs/manual/06-metodologia-recon-e-opsec.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Menção do seu domínio em paste site (ancorado em {seu_dominio}) — 5 variações

```text
site:hastebin.com "{seu_dominio}"
site:dpaste.org "{seu_dominio}"
site:0bin.net "{seu_dominio}"
site:privatebin.net "{seu_dominio}"
site:paste.mozilla.org "{seu_dominio}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `{seu_dominio}` é obrigatório: sem ele, a busca vira coleta de dados de terceiros — fora do escopo desta categoria.
- Pastes expiram e são removidos; o cache do buscador pode persistir — por isso o monitoramento é **recorrente**, não único.
- Ao encontrar credencial do seu domínio: rotacione imediatamente e peça remoção do paste (abuse). Não baixe listas que acompanhem o achado.
- O Pastebin reduziu a indexação pública; combine com os buscadores de infraestrutura/código do [manual](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md).

<div align="center">

[🏠 Hub](../../README.md) · [🕵 Dark Web, Paste & Leaks](README.md) · [Próximo: Mirrors & Índices →](mirrors-e-indices.md)

</div>
