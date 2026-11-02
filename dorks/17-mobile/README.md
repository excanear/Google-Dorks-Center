<div align="center">

[🏠 Hub](../../README.md)

# 📱 Mobile

*O artefato móvel como alvo — binários APK/IPA/AAB, configs iOS (plist/mobileconfig), segredos embutidos em apps e os backends que eles consomem.*

</div>

---

> [!CAUTION]
> Baixar um app para analisá-lo é, em geral, legítimo; usar segredos extraídos dele ou atacar o backend sem autorização não é. Respeite também os termos e direitos do app. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [📦 APK & IPA](apk-e-ipa.md) | Binários Android/iOS em diretórios abertos | 🟡 |
| 2 | [🍎 plist & Config iOS](plist-e-config-ios.md) | `.plist`, `.mobileconfig`, OTA manifests | 🟡 |
| 3 | [🔑 Strings & Segredos Mobile](strings-e-segredos-mobile.md) | `strings.xml`, `google-services.json`, chaves | 🔴 |
| 4 | [🔌 Backends Mobile](backends-mobile.md) | Configs apontando para Firebase/endpoints de app | 🟡 |

## 🧭 Como usar esta categoria

1. **Binários** (APK/IPA) permitem análise estática — pivô para strings, endpoints e chaves embutidas.
2. **Config iOS** (plist/mobileconfig) revela bundle id, perfis e, às vezes, servidores corporativos.
3. **Segredos mobile** (`google-services.json`, `strings.xml`) são o elo entre o app e seu backend — ligam a [02 · Credenciais](../02-credenciais-e-segredos/README.md) e [05 · Cloud](../05-cloud-e-storage/README.md).

## 🚧 Fronteira desta categoria

- **Chaves/tokens** extraídos (Google API key, secrets) → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md). Aqui, só o **artefato** que os contém.
- **Firebase RTDB / `appspot.com` / `firebaseio.com`** → [05 · Cloud & Storage](../05-cloud-e-storage/google-cloud-e-firebase.md). Aqui, só a **config do app** que aponta para eles.
- **APIs e webhooks** de produto → [12 · APIs & Webhooks](../12-apis-e-webhooks/README.md). Aqui, só o **backend específico de um app mobile**.

## 🔗 Categorias relacionadas

- Segredos extraídos → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md)
- Firebase/Cloud Storage → [05 · Cloud & Storage](../05-cloud-e-storage/README.md)
- Superfície de API → [12 · APIs & Webhooks](../12-apis-e-webhooks/README.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
