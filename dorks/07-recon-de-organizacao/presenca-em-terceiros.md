<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [← Documentos & Metadados](documentos-e-metadados.md) · [Próximo: Tecnologia & Fornecedores →](tecnologia-e-fornecedores.md)

# 🔗 Presença em Terceiros

*Rastro de uma organização em plataformas de terceiros — paste sites, repositórios, boards e fóruns públicos.*

</div>

---

> [!CAUTION]
> Para escopo autorizado. Conteúdo vazado em terceiros pode conter dados sensíveis — localize e reporte, não redistribua. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Paste sites e code snippets

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:pastebin.com "alvo.com"` | Menções em pastes | Google | 🔴 |
| `(site:ghostbin.com OR site:rentry.co) "alvo.com"` | Pastes alternativos | Google | 🔴 |
| `site:gist.github.com "alvo.com"` | Gists citando a org | Google | 🟡 |
| `site:jsfiddle.net OR site:codepen.io "alvo.com"` | Snippets de front-end | Google | 🟡 |

### Repositórios e gestão de projeto

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:github.com "alvo.com"` | Menções no GitHub | Google | 🟡 |
| `site:trello.com "alvo"` | Boards públicos do Trello | Google | 🔴 |
| `site:atlassian.net "alvo"` | Jira/Confluence em cloud | Google | 🟡 |
| `(site:notion.site) "alvo"` | Páginas públicas no Notion | Google | 🟡 |
| `site:docs.google.com "alvo.com"` | Documentos Google compartilhados | Google | 🔴 |

### Fóruns, Q&A e redes

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:stackoverflow.com "alvo.com"` | Perguntas citando a org (stack/erros) | Google | 🟡 |
| `site:reddit.com "alvo.com"` | Discussões sobre a org | Google | 🟢 |
| `site:scribd.com "alvo"` | Documentos no Scribd | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `site:pastebin.com "alvo.com"` | `site:pastebin.com "alvo.com"` | `site:pastebin.com alvo.com` (ou bang `!pastebin`) |
| `site:github.com "alvo.com"` | `site:github.com "alvo.com"` | GitHub Code Search: `"alvo.com"` |
| `site:trello.com "alvo"` | `site:trello.com "alvo"` | `site:trello.com alvo` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Menção da org em paste site — 12 variações

```text
site:ghostbin.com "alvo.com"
site:rentry.co "alvo.com"
site:controlc.com "alvo.com"
site:paste.ee "alvo.com"
site:justpaste.it "alvo.com"
site:dpaste.org "alvo.com"
site:hastebin.com "alvo.com"
site:0bin.net "alvo.com"
site:privatebin.net "alvo.com"
site:paste.mozilla.org "alvo.com"
site:termbin.com "alvo.com"
site:ideone.com "alvo.com"
```

> **Padrão:** Menção da org em plataforma de terceiros — 14 variações

```text
site:trello.com "alvo.com"
site:atlassian.net "alvo.com"
site:notion.site "alvo.com"
site:scribd.com "alvo.com"
site:slideshare.net "alvo.com"
site:issuu.com "alvo.com"
site:figma.com "alvo.com"
site:miro.com "alvo.com"
site:padlet.com "alvo.com"
site:airtable.com "alvo.com"
site:coda.io "alvo.com"
site:calameo.com "alvo.com"
site:flipsnack.com "alvo.com"
site:anyflip.com "alvo.com"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Paste sites e boards públicos** são onde segredos e documentos internos mais vazam por engano — 🔴 quando contêm credenciais.
- Trate conteúdo vazado como evidência: registre e reporte, **não** redistribua (dados vazados têm restrições legais).
- Segredos específicos (tokens, `.env`) são caçados melhor em [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md) com o GitHub Code Search.

<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [← Documentos & Metadados](documentos-e-metadados.md) · [Próximo: Tecnologia & Fornecedores →](tecnologia-e-fornecedores.md)

</div>
