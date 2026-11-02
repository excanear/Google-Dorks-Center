<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [← Azure Blob](azure-blob.md) · [Próximo: Outros Provedores →](outros-provedores.md)

# 🟨 Google Cloud & Firebase

*Buckets do Google Cloud Storage e bancos/arquivos do Firebase expostos, nos hosts reais do Google (verificados em 2026-11).*

</div>

---

> [!CAUTION]
> Realtime Databases e buckets abertos do Firebase vazam dados de apps inteiros. Listar é passivo; baixar/alterar sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Google Cloud Storage

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:storage.googleapis.com` | Objetos no GCS | Google | 🟡 |
| `site:storage.googleapis.com "ListBucketResult"` | Listagem de bucket GCS | Google | 🔴 |
| `site:storage.googleapis.com ext:sql` | Dumps em GCS | Google | 🔴 |
| `site:storage.googleapis.com "backup"` | Backups em GCS | Google | 🔴 |
| `site:storage.cloud.google.com` | Links autenticados de objeto | Google | 🟡 |
| `site:storage.googleapis.com confidential` | Objetos confidenciais | Google | 🔴 |

### Firebase

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:firebaseio.com` | Realtime Databases | Google | 🔴 |
| `site:firebaseio.com ".json"` | Endpoint REST do RTDB | Google | 🔴 |
| `site:firebasestorage.googleapis.com` | Firebase Storage | Google | 🟡 |
| `site:firebasestorage.app` | Novo domínio de Firebase Storage | Google | 🟡 |
| `site:appspot.com intitle:"index of"` | App Engine com listagem | Google | 🟡 |
| `inurl:firebaseio.com intext:"Permission denied"` | RTDB existente, mas protegido | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | FOFA |
|---|---|---|---|
| `site:storage.googleapis.com "ListBucketResult"` | `site:storage.googleapis.com "ListBucketResult"` | `site:storage.googleapis.com ListBucketResult` | `body="ListBucketResult" && domain="storage.googleapis.com"` |
| `site:firebaseio.com ".json"` | `site:firebaseio.com ".json"` | `site:firebaseio.com .json` | `domain="firebaseio.com"` |
| `site:firebasestorage.googleapis.com` | `site:firebasestorage.googleapis.com` | `site:firebasestorage.googleapis.com` | `domain="firebasestorage.googleapis.com"` |
| `site:appspot.com intitle:"index of"` | `site:appspot.com intitle:"index of"` | `site:appspot.com intitle:"index of"` | `domain="appspot.com"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** GCS/Firebase por host × termo — 15 variações

```text
site:storage.googleapis.com backup
site:storage.googleapis.com ext:csv
site:storage.googleapis.com dump
site:firebasestorage.googleapis.com "ListBucketResult"
site:firebasestorage.googleapis.com ext:sql
site:firebasestorage.googleapis.com backup
site:firebasestorage.googleapis.com confidential
site:firebasestorage.googleapis.com ext:csv
site:firebasestorage.googleapis.com dump
site:appspot.com "ListBucketResult"
site:appspot.com ext:sql
site:appspot.com backup
site:appspot.com confidential
site:appspot.com ext:csv
site:appspot.com dump
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Hosts Google (2026-11):** `storage.googleapis.com/<bucket>`, `<bucket>.storage.googleapis.com`, `storage.cloud.google.com`, `<proj>.firebaseio.com`, `<proj>.firebasestorage.googleapis.com`, `firebasestorage.app`, `<proj>.appspot.com`.
- Um RTDB aberto responde `.json` com os dados; `Permission denied` indica regra de segurança ativa.
- `firebaseConfig`/`apiKey` em JS não é vazamento por si só — ver [02 · Secrets em Frontend & JS](../02-credenciais-e-segredos/secrets-em-frontend-e-js.md); o risco está nas **regras** do projeto.
- Service-account JSON do GCP fica em [01 · Chaves & Certificados](../01-exposicao-de-arquivos/chaves-e-certificados.md).

<div align="center">

[🏠 Hub](../../README.md) · [☁ Cloud & Storage](README.md) · [← Azure Blob](azure-blob.md) · [Próximo: Outros Provedores →](outros-provedores.md)

</div>
