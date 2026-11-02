<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [Próximo: Azure Blob →](azure-blob.md)

# 🟧 AWS S3

*Buckets S3 públicos e listagens expostas, nos hosts reais da AWS (verificados em 2026-11).*

</div>

---

> [!CAUTION]
> Listar um bucket público é passivo; baixar objetos sem autorização não é. Reporte ao dono. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Buckets e listagens

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:s3.amazonaws.com` | Objetos no host S3 global | Google | 🟡 |
| `site:s3.amazonaws.com intitle:"index of"` | Listagem de bucket | Google | 🔴 |
| `site:s3.amazonaws.com "ListBucketResult"` | XML de listagem de bucket | Google | 🔴 |
| `site:s3.amazonaws.com confidential` | Objetos confidenciais | Google | 🔴 |
| `site:s3.amazonaws.com ext:sql` | Dumps em S3 | Google | 🔴 |
| `site:s3.amazonaws.com ext:xlsx` | Planilhas em S3 | Google | 🔴 |
| `site:s3.amazonaws.com "backup"` | Backups em S3 | Google | 🔴 |

### Hosts regionais e virtual-host

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:s3-external-1.amazonaws.com` | Endpoint legado us-east-1 | Google | 🟡 |
| `inurl:.s3.amazonaws.com "index of"` | Bucket em virtual-host | Google | 🔴 |
| `inurl:.s3.amazonaws.com ext:pdf` | PDFs em bucket virtual-host | Google | 🟡 |
| `inurl:s3.amazonaws.com intext:"AccessDenied" -site:docs.aws.amazon.com` | Buckets existentes mas privados | Google | 🟢 |
| `site:amazonaws.com "ListBucketResult" "Key"` | Chaves de objetos listadas | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Shodan/FOFA |
|---|---|---|---|
| `site:s3.amazonaws.com "ListBucketResult"` | `site:s3.amazonaws.com "ListBucketResult"` | `site:s3.amazonaws.com ListBucketResult` | FOFA: `body="ListBucketResult"` |
| `site:s3.amazonaws.com intitle:"index of"` | `site:s3.amazonaws.com intitle:"index of"` | `site:s3.amazonaws.com intitle:"index of"` | — |
| `inurl:.s3.amazonaws.com ext:pdf` | `instreamset:url:.s3.amazonaws.com ext:pdf` | `inurl:.s3.amazonaws.com filetype:pdf` | — |
| `site:s3.amazonaws.com "backup"` | `site:s3.amazonaws.com backup` | `site:s3.amazonaws.com backup` | — |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Bucket S3 por host × termo de exposição — 44 variações

```text
site:s3.amazonaws.com "index of"
site:s3.amazonaws.com backup
site:s3.amazonaws.com ext:csv
site:s3.amazonaws.com ext:bak
site:s3.amazonaws.com ext:zip
site:s3.amazonaws.com password
site:s3.amazonaws.com dump
site:s3.amazonaws.com invoice
site:s3-us-west-2.amazonaws.com confidential
site:s3-us-west-2.amazonaws.com "index of"
site:s3-us-west-2.amazonaws.com backup
site:s3-us-west-2.amazonaws.com ext:sql
site:s3-us-west-2.amazonaws.com ext:xlsx
site:s3-us-west-2.amazonaws.com ext:csv
site:s3-us-west-2.amazonaws.com ext:bak
site:s3-us-west-2.amazonaws.com ext:zip
site:s3-us-west-2.amazonaws.com "ListBucketResult"
site:s3-us-west-2.amazonaws.com password
site:s3-us-west-2.amazonaws.com dump
site:s3-us-west-2.amazonaws.com invoice
site:s3-eu-west-1.amazonaws.com confidential
site:s3-eu-west-1.amazonaws.com "index of"
site:s3-eu-west-1.amazonaws.com backup
site:s3-eu-west-1.amazonaws.com ext:sql
site:s3-eu-west-1.amazonaws.com ext:xlsx
site:s3-eu-west-1.amazonaws.com ext:csv
site:s3-eu-west-1.amazonaws.com ext:bak
site:s3-eu-west-1.amazonaws.com ext:zip
site:s3-eu-west-1.amazonaws.com "ListBucketResult"
site:s3-eu-west-1.amazonaws.com password
site:s3-eu-west-1.amazonaws.com dump
site:s3-eu-west-1.amazonaws.com invoice
site:s3.ap-southeast-1.amazonaws.com confidential
site:s3.ap-southeast-1.amazonaws.com "index of"
site:s3.ap-southeast-1.amazonaws.com backup
site:s3.ap-southeast-1.amazonaws.com ext:sql
site:s3.ap-southeast-1.amazonaws.com ext:xlsx
site:s3.ap-southeast-1.amazonaws.com ext:csv
site:s3.ap-southeast-1.amazonaws.com ext:bak
site:s3.ap-southeast-1.amazonaws.com ext:zip
site:s3.ap-southeast-1.amazonaws.com "ListBucketResult"
site:s3.ap-southeast-1.amazonaws.com password
site:s3.ap-southeast-1.amazonaws.com dump
site:s3.ap-southeast-1.amazonaws.com invoice
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Hosts S3 válidos (2026-11):** `s3.amazonaws.com`, `s3-<region>.amazonaws.com`, `<bucket>.s3.amazonaws.com`, `<bucket>.s3.<region>.amazonaws.com`. CDNs na frente (CloudFront) escondem o bucket real.
- `ListBucketResult` no corpo indica **listagem pública** — o achado mais valioso; `AccessDenied` indica bucket existente mas fechado.
- Muito conteúdo em S3 é **público por desenho** (assets de site). Confirme sensibilidade antes de reportar.
- Credenciais AWS (`AKIA…`) em arquivos ficam em [02 · Tokens de API](../02-credenciais-e-segredos/tokens-de-api.md).

<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [Próximo: Azure Blob →](azure-blob.md)

</div>
