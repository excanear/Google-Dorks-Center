<div align="center">

[🏠 Hub](../../README.md) · [📱 Mobile](README.md) · [← Strings & Segredos Mobile](strings-e-segredos-mobile.md)

# 🔌 Backends Mobile

*Configs e pistas que ligam o app ao seu backend — endpoints de API móvel, SDKs de backend e referências a serviços de nuvem.*

</div>

---

> [!CAUTION]
> Descobrir o backend de um app é recon; enviar requisições autenticadas ou testar o serviço sem autorização não é. O armazenamento Firebase/Cloud em si é tratado na [05](../05-cloud-e-storage/README.md). Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Endpoints de API de app

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/mobile/api intext:"version"` | API dedicada a app móvel | Google | 🟡 |
| `inurl:/api/mobile intext:"token"` | Endpoint móvel com token | Google | 🟡 |
| `inurl:/app/config.json intext:"baseUrl"` | Config de app com URL base | Google | 🟡 |
| `filetype:json intext:"apiBaseUrl" intext:"mobile"` | Config móvel com base da API | Google | 🟡 |

### SDKs de backend e serviços

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:json intext:"onesignal_app_id"` | Config de push OneSignal | Google | 🟡 |
| `intext:"applicationId" intext:"clientKey" "Parse"` | Backend Parse Server | Google | 🟡 |
| `inurl:/parse/ intext:"X-Parse-Application-Id"` | Endpoint Parse Server | Google | 🔴 |
| `filetype:json intext:"supabaseUrl" intext:"anonKey"` | Backend Supabase de app | Google | 🟡 |
| `intext:"amplifyconfiguration.json"` | Config AWS Amplify (mobile) | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `inurl:/parse/ intext:"X-Parse-Application-Id"` | `instreamset:url:/parse/ "X-Parse-Application-Id"` | `inurl:parse X-Parse-Application-Id` |
| `filetype:json intext:"onesignal_app_id"` | `ext:json "onesignal_app_id"` | `filetype:json onesignal_app_id` |
| `intext:"amplifyconfiguration.json"` | `"amplifyconfiguration.json"` | `amplifyconfiguration.json` |

> **Fronteira:** Firebase RTDB (`firebaseio.com`), `appspot.com` e Cloud Storage de app são da [05 · Cloud & Storage](../05-cloud-e-storage/google-cloud-e-firebase.md). Aqui tratamos a **config do app** que aponta para o backend, não o bucket/DB em si.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Backend de app móvel por caminho — 8 variações

```text
inurl:/mobile/api
inurl:/api/mobile
inurl:/parse/
inurl:/parse/health
inurl:/app/config.json
inurl:/api/v1/mobile
inurl:/mobileapi
inurl:/m/api
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Parse Server auto-hospedado (`X-Parse-Application-Id`) às vezes fica com master key fraca — a existência do endpoint é o achado; não teste.
- `amplifyconfiguration.json` e `supabaseUrl/anonKey` descrevem todo o backend de um app — a `anonKey` é pública por design, mas revela o projeto.
- OneSignal/Parse/Amplify são **BaaS**; o Firebase/GCP fica na [05 · Cloud & Storage](../05-cloud-e-storage/README.md) para não duplicar.
- Endpoint `/mobile/api` costuma ter menos hardening que a API web — recon útil, teste só com autorização.

<div align="center">

[🏠 Hub](../../README.md) · [📱 Mobile](README.md) · [← Strings & Segredos Mobile](strings-e-segredos-mobile.md)

</div>
