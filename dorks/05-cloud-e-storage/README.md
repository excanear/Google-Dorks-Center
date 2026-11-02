<div align="center">

[🏠 Hub](../../README.md)

# ☁ Cloud & Storage

*Buckets, containers e consoles de armazenamento em nuvem expostos — AWS S3, Azure Blob, Google Cloud/Firebase e outros provedores.*

</div>

---

> [!CAUTION]
> Buckets abertos frequentemente contêm dados pessoais e backups inteiros. Listar o índice público é passivo; **baixar ou enumerar objetos** sem autorização pode configurar acesso indevido (LGPD, CFAA). Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🟧 AWS S3](aws-s3.md) | `s3.amazonaws.com`, buckets e listagens | 🔴 |
| 2 | [🟦 Azure Blob](azure-blob.md) | `blob.core.windows.net`, containers | 🔴 |
| 3 | [🟨 Google Cloud & Firebase](google-cloud-e-firebase.md) | `storage.googleapis.com`, `firebaseio.com` | 🔴 |
| 4 | [🟩 Outros Provedores](outros-provedores.md) | DigitalOcean, Backblaze, Wasabi, R2, OSS… | 🔴 |
| 5 | [🗂 Dashboards & Índices Abertos](dashboards-e-indices-abertos.md) | Consoles e índices de storage | 🟡–🔴 |

## 🧭 Como usar esta categoria

1. Troque o placeholder de bucket/host pelo **escopo autorizado**.
2. Buckets mal configurados listam objetos via XML (`ListBucketResult`) — é isso que muitos dorks miram.
3. Para enumeração em escala, prefira ferramentas dedicadas e as **APIs oficiais**, respeitando ToS; dork é ponto de partida.

## 🔗 Categorias relacionadas

- Service-account JSON do GCP e chaves → [01 · Chaves & Certificados](../01-exposicao-de-arquivos/chaves-e-certificados.md)
- Tokens e chaves de cloud em arquivos → [02 · Tokens de API](../02-credenciais-e-segredos/tokens-de-api.md)
- `firebaseConfig` em frontend → [02 · Secrets em Frontend & JS](../02-credenciais-e-segredos/secrets-em-frontend-e-js.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
