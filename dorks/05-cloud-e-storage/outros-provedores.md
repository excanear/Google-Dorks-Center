<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [← Google Cloud & Firebase](google-cloud-e-firebase.md) · [Próximo: Dashboards & Índices Abertos →](dashboards-e-indices-abertos.md)

# 🟩 Outros Provedores

*Object storage além dos três grandes — DigitalOcean Spaces, Backblaze B2, Wasabi, Alibaba OSS, Cloudflare R2, Oracle, IBM, OVH (hosts verificados em 2026-11).*

</div>

---

> [!CAUTION]
> As mesmas regras valem: listar é passivo, baixar sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### S3-compatíveis populares

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:digitaloceanspaces.com` | DigitalOcean Spaces | Google | 🟡 |
| `site:digitaloceanspaces.com "ListBucketResult"` | Listagem de Space | Google | 🔴 |
| `site:backblazeb2.com` | Backblaze B2 | Google | 🟡 |
| `inurl:f000.backblazeb2.com` | Endpoint público do B2 | Google | 🟡 |
| `site:wasabisys.com` | Wasabi Storage | Google | 🟡 |
| `site:s3.wasabisys.com "ListBucketResult"` | Listagem no Wasabi | Google | 🔴 |
| `inurl:aliyuncs.com inurl:oss` | Alibaba OSS | Google | 🟡 |
| `site:oss-cn-hangzhou.aliyuncs.com` | OSS região Hangzhou | Google | 🟡 |

### Mais provedores

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:r2.dev` | Cloudflare R2 (domínio público) | Google | 🟡 |
| `inurl:r2.cloudflarestorage.com` | Endpoint S3 do R2 | Google | 🟡 |
| `inurl:objectstorage inurl:oraclecloud.com` | Oracle Object Storage | Google | 🟡 |
| `site:cloud-object-storage.appdomain.cloud` | IBM Cloud Object Storage | Google | 🟡 |
| `inurl:io.cloud.ovh.net inurl:s3` | OVHcloud Object Storage | Google | 🟡 |
| `inurl:storage.yandexcloud.net` | Yandex Object Storage | Google | 🟡 |
| `site:cdn.scaleway.com OR inurl:s3.fr-par.scw.cloud` | Scaleway Object Storage | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | FOFA |
|---|---|---|---|
| `site:digitaloceanspaces.com "ListBucketResult"` | `site:digitaloceanspaces.com "ListBucketResult"` | `site:digitaloceanspaces.com ListBucketResult` | `body="ListBucketResult" && domain="digitaloceanspaces.com"` |
| `site:s3.wasabisys.com "ListBucketResult"` | `site:s3.wasabisys.com "ListBucketResult"` | `site:s3.wasabisys.com ListBucketResult` | `domain="wasabisys.com"` |
| `inurl:r2.cloudflarestorage.com` | `instreamset:url:r2.cloudflarestorage.com` | `inurl:r2.cloudflarestorage.com` | `domain="r2.cloudflarestorage.com"` |
| `inurl:aliyuncs.com inurl:oss` | `instreamset:url:aliyuncs.com oss` | `inurl:aliyuncs.com oss` | `domain="aliyuncs.com"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Provedor S3-compatível por host (listagem/objetos) — 10 variações

```text
site:nyc3.digitaloceanspaces.com "ListBucketResult"
site:sfo3.digitaloceanspaces.com "ListBucketResult"
site:ams3.digitaloceanspaces.com "ListBucketResult"
site:f000.backblazeb2.com "ListBucketResult"
site:oss-cn-hangzhou.aliyuncs.com "ListBucketResult"
site:oss-cn-beijing.aliyuncs.com "ListBucketResult"
site:r2.cloudflarestorage.com "ListBucketResult"
site:storage.yandexcloud.net "ListBucketResult"
site:s3.fr-par.scw.cloud "ListBucketResult"
site:s3.io.cloud.ovh.net "ListBucketResult"
```

> **Padrão:** Provedor S3-compatível por host × termo — 33 variações

```text
site:nyc3.digitaloceanspaces.com backup
site:nyc3.digitaloceanspaces.com ext:sql
site:nyc3.digitaloceanspaces.com confidential
site:sfo3.digitaloceanspaces.com backup
site:sfo3.digitaloceanspaces.com ext:sql
site:sfo3.digitaloceanspaces.com confidential
site:ams3.digitaloceanspaces.com backup
site:ams3.digitaloceanspaces.com ext:sql
site:ams3.digitaloceanspaces.com confidential
site:s3.wasabisys.com backup
site:s3.wasabisys.com ext:sql
site:s3.wasabisys.com confidential
site:f000.backblazeb2.com backup
site:f000.backblazeb2.com ext:sql
site:f000.backblazeb2.com confidential
site:oss-cn-hangzhou.aliyuncs.com backup
site:oss-cn-hangzhou.aliyuncs.com ext:sql
site:oss-cn-hangzhou.aliyuncs.com confidential
site:oss-cn-beijing.aliyuncs.com backup
site:oss-cn-beijing.aliyuncs.com ext:sql
site:oss-cn-beijing.aliyuncs.com confidential
site:r2.cloudflarestorage.com backup
site:r2.cloudflarestorage.com ext:sql
site:r2.cloudflarestorage.com confidential
site:storage.yandexcloud.net backup
site:storage.yandexcloud.net ext:sql
site:storage.yandexcloud.net confidential
site:s3.fr-par.scw.cloud backup
site:s3.fr-par.scw.cloud ext:sql
site:s3.fr-par.scw.cloud confidential
site:s3.io.cloud.ovh.net backup
site:s3.io.cloud.ovh.net ext:sql
site:s3.io.cloud.ovh.net confidential
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Hosts (2026-11):** `<space>.<region>.digitaloceanspaces.com` · `f<nnn>.backblazeb2.com` · `s3.<region>.wasabisys.com` · `<bucket>.oss-<region>.aliyuncs.com` · `<hash>.r2.cloudflarestorage.com` / `pub-<hash>.r2.dev` · `objectstorage.<region>.oraclecloud.com` · `*.cloud-object-storage.appdomain.cloud` · `s3.<region>.io.cloud.ovh.net` · `storage.yandexcloud.net`.
- Provedores **S3-compatíveis** devolvem o mesmo `ListBucketResult` da AWS — o mesmo padrão de listagem funciona.
- Muitos usam **CDN na frente**, ocultando o host real; cruze com certificados (crt.sh) e DNS.

<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [← Google Cloud & Firebase](google-cloud-e-firebase.md) · [Próximo: Dashboards & Índices Abertos →](dashboards-e-indices-abertos.md)

</div>
