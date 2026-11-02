<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [← AWS S3](aws-s3.md) · [Próximo: Google Cloud & Firebase →](google-cloud-e-firebase.md)

# 🟦 Azure Blob

*Containers e arquivos do Azure Storage expostos, nos hosts reais da Microsoft (verificados em 2026-11).*

</div>

---

> [!CAUTION]
> Container público pode expor backups e dados pessoais. Listar é passivo; baixar sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Blob e File storage

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:blob.core.windows.net` | Objetos em Blob Storage | Google | 🟡 |
| `site:blob.core.windows.net "EnumerationResults"` | Listagem de container (XML) | Google | 🔴 |
| `site:blob.core.windows.net ext:sql` | Dumps em Blob | Google | 🔴 |
| `site:blob.core.windows.net "backup"` | Backups em Blob | Google | 🔴 |
| `site:blob.core.windows.net confidential` | Objetos confidenciais | Google | 🔴 |
| `site:file.core.windows.net` | Azure Files exposto | Google | 🟡 |
| `site:blob.core.windows.net ext:pdf` | PDFs em Blob | Google | 🟡 |

### Containers e SAS

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:blob.core.windows.net inurl:?comp=list` | Endpoint de listagem de container | Google | 🔴 |
| `inurl:"blob.core.windows.net" intext:"BlobNotFound"` | Containers existentes | Google | 🟢 |
| `inurl:blob.core.windows.net "sig=" "se="` | URLs com token SAS vazado | Google | 🔴 |
| `site:web.core.windows.net` | Static website em Storage | Google | 🟡 |
| `site:dfs.core.windows.net` | Data Lake Gen2 exposto | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | FOFA |
|---|---|---|---|
| `site:blob.core.windows.net "EnumerationResults"` | `site:blob.core.windows.net "EnumerationResults"` | `site:blob.core.windows.net EnumerationResults` | `body="EnumerationResults" && domain="blob.core.windows.net"` |
| `site:blob.core.windows.net ext:sql` | `site:blob.core.windows.net ext:sql` | `site:blob.core.windows.net filetype:sql` | — |
| `inurl:blob.core.windows.net "sig=" "se="` | `instreamset:url:blob.core.windows.net "sig="` | `inurl:blob.core.windows.net sig=` | — |
| `site:dfs.core.windows.net` | `site:dfs.core.windows.net` | `site:dfs.core.windows.net` | `domain="dfs.core.windows.net"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Blob/File storage por subdomínio × termo — 18 variações

```text
site:blob.core.windows.net ext:bak
site:blob.core.windows.net backup
site:blob.core.windows.net ext:xlsx
site:blob.core.windows.net "?comp=list"
site:file.core.windows.net "EnumerationResults"
site:file.core.windows.net ext:sql
site:file.core.windows.net ext:bak
site:file.core.windows.net backup
site:file.core.windows.net confidential
site:file.core.windows.net ext:xlsx
site:file.core.windows.net "?comp=list"
site:dfs.core.windows.net "EnumerationResults"
site:dfs.core.windows.net ext:sql
site:dfs.core.windows.net ext:bak
site:dfs.core.windows.net backup
site:dfs.core.windows.net confidential
site:dfs.core.windows.net ext:xlsx
site:dfs.core.windows.net "?comp=list"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Hosts Azure Storage (2026-11):** `<conta>.blob.core.windows.net`, `.file.core.windows.net`, `.dfs.core.windows.net`, `.web.core.windows.net`, `.queue.core.windows.net`, `.table.core.windows.net`.
- `EnumerationResults` no corpo = **listagem pública** de container; `?comp=list` é o endpoint que a produz.
- **Tokens SAS** (`sig=`, `se=`, `sp=`) em URLs indexadas são credenciais temporárias vazadas — alto risco enquanto válidas.
- `BlobNotFound`/`ResourceNotFound` confirmam a conta, mas não necessariamente exposição de dados.

<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [← AWS S3](aws-s3.md) · [Próximo: Google Cloud & Firebase →](google-cloud-e-firebase.md)

</div>
