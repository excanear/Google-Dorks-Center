<div align="center">

[🏠 Hub](../../README.md) · [🎨 Temáticos](README.md) · [Próximo: Cripto & Blockchain →](cripto-e-blockchain.md)

# 📰 Jornalismo & Investigação

*Fontes e documentos para jornalismo investigativo e OSINT — leaks públicos, documentos oficiais e bases de dados abertas.*

</div>

---

> [!CAUTION]
> Conteúdo vazado pode ter restrições legais e envolver pessoas. Verifique autenticidade, proteja fontes e minimize dados pessoais (LGPD/GDPR). Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Documentos e bases investigativas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:aleph.occrp.org "{termo}"` | OCCRP Aleph (documentos e leaks) | Google | 🟡 |
| `site:documentcloud.org "{termo}"` | DocumentCloud (documentos de redações) | Google | 🟡 |
| `site:icij.org "{termo}"` | Investigações do ICIJ | Google | 🟢 |
| `site:wikileaks.org "{termo}"` | Arquivo WikiLeaks | Google | 🟡 |
| `filetype:pdf "leaked" OR "vazado" "{termo}"` | Documentos marcados como vazados | Google | 🔴 |

### Fontes e corroboração

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:scholar.google.com "{termo}"` | Literatura para corroboração | Google | 🟢 |
| `site:archive.org "{termo}" filetype:pdf` | Documentos no Internet Archive | Google | 🟢 |
| `(site:gov OR site:*.gov.br) "{termo}" filetype:pdf` | Documentos oficiais | Google | 🟢 |
| `site:sec.gov "{empresa}"` | Registros corporativos SEC (EUA) | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Fonte especializada |
|---|---|---|
| `site:documentcloud.org "{termo}"` | `site:documentcloud.org "{termo}"` | busca interna do DocumentCloud |
| `site:archive.org "{termo}" filetype:pdf` | `site:archive.org "{termo}"` | Wayback CDX para URLs históricas |
| `site:aleph.occrp.org "{termo}"` | `site:aleph.occrp.org "{termo}"` | busca interna do Aleph |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Fonte investigativa por host (placeholder {termo}) — 7 variações

```text
site:muckrock.com "{termo}"
site:theblacklight.org "{termo}"
site:datasette.io "{termo}"
site:theintercept.com "{termo}"
site:bellingcat.com "{termo}"
site:propublica.org "{termo}"
site:cryptome.org "{termo}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Verifique sempre a autenticidade**: documento "vazado" pode ser forjado. Corrobore com fontes independentes.
- Proteja fontes e respeite a lei: posse de dados vazados tem restrições; consulte o jurídico da redação.
- Ferramentas de jornalismo (Aleph, DocumentCloud, Bellingcat) complementam os dorks — veja o OSINT Ultimate Hub.

<div align="center">

[🏠 Hub](../../README.md) · [🎨 Temáticos](README.md) · [Próximo: Cripto & Blockchain →](cripto-e-blockchain.md)

</div>
