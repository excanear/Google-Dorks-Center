<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [← E-mails & Pessoas](emails-e-pessoas.md) · [Próximo: Presença em Terceiros →](presenca-em-terceiros.md)

# 📑 Documentos & Metadados

*Documentos públicos de uma organização que vazam nomes de usuário, software, caminhos internos e versões — matéria-prima de recon.*

</div>

---

> [!CAUTION]
> Para escopo autorizado. Baixar e extrair metadados de documentos públicos é passivo, mas respeite LGPD/GDPR quanto a dados pessoais embutidos. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Documentos da organização

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:alvo.com filetype:pdf` | Todos os PDFs da org | Google | 🟢 |
| `site:alvo.com (filetype:doc OR filetype:docx)` | Documentos Word | Google | 🟢 |
| `site:alvo.com (filetype:xls OR filetype:xlsx)` | Planilhas | Google | 🟡 |
| `site:alvo.com filetype:pptx` | Apresentações | Google | 🟢 |
| `site:alvo.com ext:txt inurl:/doc` | Notas e textos | Google | 🟢 |

### Documentos que vazam metadados/stack

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:alvo.com filetype:pdf intext:"Microsoft Word"` | Produtor do PDF (software) | Google | 🟢 |
| `site:alvo.com ext:docx intext:"Author"` | Autoria em documentos | Google | 🟡 |
| `site:alvo.com ext:xml intext:"generator"` | Gerador em XML/config | Google | 🟢 |
| `site:alvo.com filetype:pdf "\\\\" "fileserver"` | Caminhos UNC em documentos | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `site:alvo.com filetype:pdf` | `site:alvo.com filetype:pdf` | `site:alvo.com mime:pdf` |
| `site:alvo.com (filetype:doc OR filetype:docx)` | `site:alvo.com (ext:doc OR ext:docx)` | `site:alvo.com (mime:doc \| mime:docx)` |
| `site:alvo.com filetype:pptx` | `site:alvo.com filetype:pptx` | `site:alvo.com mime:pptx` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Documento da organização por extensão — 17 variações

```text
site:alvo.com filetype:doc
site:alvo.com filetype:docx
site:alvo.com filetype:xls
site:alvo.com filetype:xlsx
site:alvo.com filetype:ppt
site:alvo.com filetype:csv
site:alvo.com filetype:txt
site:alvo.com filetype:rtf
site:alvo.com filetype:odt
site:alvo.com filetype:xml
site:alvo.com filetype:json
site:alvo.com filetype:log
site:alvo.com filetype:bak
site:alvo.com filetype:sql
site:alvo.com filetype:conf
site:alvo.com filetype:ini
site:alvo.com filetype:yml
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Documentos públicos carregam **metadados** (autor, software, caminho) — use ferramentas de EXIF/metadados após a coleta autorizada.
- Caminhos UNC (`\\servidor\share`) revelam nomes de servidores internos — ótimo pivô de rede.
- Documentos **sensíveis** (confidenciais, com dados pessoais) são tratados em [01 · Exposição de Arquivos](../01-exposicao-de-arquivos/README.md); aqui o foco é recon de superfície e stack.

<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [← E-mails & Pessoas](emails-e-pessoas.md) · [Próximo: Presença em Terceiros →](presenca-em-terceiros.md)

</div>
