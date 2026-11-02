<div align="center">

[🏠 Hub](../../README.md) · [📱 Mobile](README.md) · [← plist & Config iOS](plist-e-config-ios.md) · [Próximo: Backends Mobile →](backends-mobile.md)

# 🔑 Strings & Segredos Mobile

*`strings.xml`, `google-services.json`, `GoogleService-Info.plist` e `AndroidManifest.xml` expostos — onde os segredos do app costumam morar.*

</div>

---

> [!CAUTION]
> Estes arquivos frequentemente contêm chaves de API e identificadores de projeto. Encontrá-los é recon; usar as chaves é acesso não autorizado. Trate qualquer segredo como comprometido e reporte. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Config de projeto (Firebase/Google)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "google-services.json"` | Config Firebase Android | Google | 🔴 |
| `intitle:"index of" "GoogleService-Info.plist"` | Config Firebase iOS | Google | 🔴 |
| `filetype:json intext:"current_key" intext:"mobilesdk_app_id"` | google-services servido direto | Google | 🔴 |
| `filetype:plist intext:"API_KEY" intext:"GCM_SENDER_ID"` | GoogleService-Info servido | Google | 🔴 |

### Recursos e manifest Android

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "strings.xml"` | Recursos de string (podem ter chaves) | Google | 🟡 |
| `intitle:"index of" "AndroidManifest.xml"` | Manifesto Android exposto | Google | 🟡 |
| `filetype:xml intext:"android:name" intext:"API_KEY"` | Chave em meta-data do manifest | Google | 🔴 |
| `intitle:"index of" "network_security_config.xml"` | Config de segurança de rede | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `intitle:"index of" "google-services.json"` | `intitle:"index of" "google-services.json"` | `"index of" google-services.json` |
| `intitle:"index of" "GoogleService-Info.plist"` | `intitle:"index of" "GoogleService-Info.plist"` | `"index of" GoogleService-Info.plist` |
| `intitle:"index of" "strings.xml"` | `intitle:"index of" "strings.xml"` | `"index of" strings.xml` |

> **Código-fonte é o canal mais rico:** `google-services.json` e `strings.xml` vazam muito em repositórios — GitHub Code Search (`filename:google-services.json`). A **chave em si** é da [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Recurso/config Android em diretório aberto — 3 variações

```text
intitle:"index of" "secrets.xml"
intitle:"index of" "apikeys.xml"
intitle:"index of" "local.properties"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `google-services.json`/`GoogleService-Info.plist` contêm a API key do Firebase e o app id — frequentemente restringíveis, mas tratados como segredo quando sem restrição.
- `strings.xml` é o esconderijo clássico de chaves hardcoded em Android (`maps_api_key`, tokens).
- `network_security_config.xml` revela se o app aceita cleartext/pinning — recon de postura, não segredo.
- O **arquivo** é desta categoria; a **chave** encontrada é um achado para a [02](../02-credenciais-e-segredos/README.md), e o backend para onde ela aponta, para [05 · Cloud](../05-cloud-e-storage/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [📱 Mobile](README.md) · [← plist & Config iOS](plist-e-config-ios.md) · [Próximo: Backends Mobile →](backends-mobile.md)

</div>
