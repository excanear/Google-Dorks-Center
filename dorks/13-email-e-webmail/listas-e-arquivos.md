<div align="center">

[🏠 Hub](../../README.md) · [📧 E-mail & Webmail](README.md) · [← Servidores de E-mail](servidores-de-email.md) · [Próximo: Relay & Configuração →](relay-e-config.md)

# 🗂 Listas & Arquivos de Mensagem

*Caixas e mensagens exportadas (mbox, .eml, .pst, .msg) e arquivos de listas de discussão em diretórios abertos — correspondência real exposta.*

</div>

---

> [!CAUTION]
> Estes arquivos contêm **mensagens reais de pessoas**. Confirmar a exposição é recon; abrir, baixar ou redistribuir conteúdo de terceiros viola a LGPD/GDPR. Reporte ao responsável. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Arquivos de caixa/mensagem em diretório aberto

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:mbox` | Caixas mbox em pasta aberta | Google | 🔴 |
| `intitle:"index of" ext:eml` | Mensagens .eml soltas | Google | 🔴 |
| `intitle:"index of" ext:pst` | Arquivos de dados do Outlook (.pst) | Google | 🔴 |
| `intitle:"index of" ext:msg` | Mensagens do Outlook (.msg) | Google | 🔴 |
| `intitle:"index of" "Maildir"` | Diretório Maildir exposto | Google | 🔴 |

### Arquivos de listas de discussão

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/pipermail/` | Arquivo público de listas (Mailman) | Google | 🟡 |
| `intitle:"index of" "pipermail"` | Diretório pipermail aberto | Google | 🟡 |
| `inurl:/mailman/private/` | Arquivo **privado** de lista exposto | Google | 🔴 |
| `inurl:/listserv intext:"archives"` | Arquivos LISTSERV | Google | 🟡 |
| `intitle:"The Mail Archive"` | Espelho de listas públicas | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `intitle:"index of" ext:mbox` | `intitle:"index of" ext:mbox` | `title:"index of" mime:mbox` |
| `intitle:"index of" ext:eml` | `intitle:"index of" ext:eml` | `title:"index of" mime:eml` |
| `inurl:/pipermail/` | `instreamset:url:/pipermail/` | `url:/pipermail/` |
| `intitle:"index of" ext:pst` | `intitle:"index of" ext:pst` | `title:"index of" mime:pst` |

> **Wayback/CDX:** mensagens removidas da web às vezes permanecem no Wayback. Buscar `*.eml`/`*.mbox` no CDX de um domínio pode recuperar o que saiu do ar — veja o [manual de código e arquivos](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo de mensagem em diretório aberto por extensão — 2 variações

```text
intitle:"index of" ext:ost
intitle:"index of" ext:emlx
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `inurl:/mailman/private/` indexado é um vazamento sério: o arquivo deveria exigir senha. Reporte imediatamente.
- `.pst`/`.ost` são caixas inteiras do Outlook — um único arquivo pode conter anos de correspondência.
- `pipermail` e `The Mail Archive` costumam ser listas **públicas por design** (open source); risco baixo, mas confirme o contexto.
- Exportações de contatos em CSV com e-mails cruzam com [01 · Exposição de Arquivos](../01-exposicao-de-arquivos/README.md); mantenha o foco em arquivos de **mensagem** aqui.

<div align="center">

[🏠 Hub](../../README.md) · [📧 E-mail & Webmail](README.md) · [← Servidores de E-mail](servidores-de-email.md) · [Próximo: Relay & Configuração →](relay-e-config.md)

</div>
