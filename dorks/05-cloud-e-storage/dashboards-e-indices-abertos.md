<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [← Outros Provedores](outros-provedores.md)

# 🗂 Dashboards & Índices Abertos

*Consoles de nuvem e índices de storage self-hosted expostos — MinIO, buckets em CDN e páginas de índice de object storage.*

</div>

---

> [!CAUTION]
> Consoles de storage dão controle sobre os dados. Exposição é 🔴; não acesse sem autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Object storage self-hosted

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"MinIO Browser"` | Navegador web do MinIO | Google | 🔴 |
| `inurl:/minio/ intext:"MinIO"` | Console MinIO por caminho | Google | 🔴 |
| `intitle:"SeaweedFS"` | Filer do SeaweedFS | Google | 🟡 |
| `intitle:"Garage" "S3"` | Storage Garage | Google | 🟡 |
| `intitle:"Ceph" inurl:/#/dashboard` | Dashboard do Ceph | Google | 🔴 |
| `intitle:"OpenStack Swift"` | Object storage Swift | Google | 🟡 |

### Índices e gateways

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"ListBucketResult" intitle:"index of"` | Índice de bucket genérico | Google | 🔴 |
| `inurl:/storage/v1/b/ "items"` | API JSON do GCS listando buckets | Google | 🔴 |
| `inurl:?prefix= intext:"CommonPrefixes"` | Navegação de prefixos S3/compatível | Google | 🟡 |
| `intitle:"Directory Listing" "cloud"` | Listagem de storage em CDN | Google | 🟡 |
| `inurl:/filestash OR intitle:"Filestash"` | Gateway web de arquivos | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | Censys | FOFA |
|---|---|---|---|
| `intitle:"MinIO Browser"` | `http.title:"MinIO Browser"` | `web.endpoints.http.title:"MinIO"` | `title="MinIO Browser"` |
| `intitle:"Ceph" inurl:/#/dashboard` | `http.title:"Ceph"` | `web.endpoints.http.title:"Ceph"` | `title="Ceph"` |
| `intitle:"OpenStack Swift"` | `http.title:"OpenStack"` | `web.endpoints.http.title:"OpenStack"` | `title="OpenStack"` |
| `intext:"ListBucketResult" intitle:"index of"` | `http.html:"ListBucketResult"` | `web.endpoints.http.body:"ListBucketResult"` | `body="ListBucketResult"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Console/gerenciador de storage self-hosted por título — 4 variações

```text
intitle:"Ceph"
intitle:"Filestash"
intitle:"Pydio"
intitle:"Nextcloud"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- MinIO/Ceph/Swift sem auth são 🔴 — dão acesso a objetos; apenas confirme a exposição.
- Consoles self-hosted em **portas específicas** (MinIO 9001, Ceph 8443) são melhor achados por Shodan/FOFA com `port:`.
- `ListBucketResult`/`CommonPrefixes` são a assinatura universal de listagem S3-compatível — valem para qualquer provedor da categoria.
- Interfaces de gerenciamento genéricas (não-storage) ficam em [03 · Interfaces de Gerenciamento](../03-infraestrutura-web/interfaces-de-gerenciamento.md).

<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [← Outros Provedores](outros-provedores.md)

</div>
