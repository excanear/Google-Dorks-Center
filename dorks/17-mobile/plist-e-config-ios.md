<div align="center">

[🏠 Hub](../../README.md) · [📱 Mobile](README.md) · [← APK & IPA](apk-e-ipa.md) · [Próximo: Strings & Segredos Mobile →](strings-e-segredos-mobile.md)

# 🍎 plist & Config iOS

*Arquivos `.plist`, perfis `.mobileconfig` e manifests OTA do iOS expostos — bundle id, perfis de configuração e servidores corporativos.*

</div>

---

> [!CAUTION]
> Um `.mobileconfig` pode conter perfis de VPN/Wi-Fi/MDM corporativos. Identificar exposição é recon; instalar perfis de terceiros ou usar credenciais contidas neles não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Arquivos plist

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:plist` | Arquivos plist em pasta aberta | Google | 🟡 |
| `filetype:plist intext:"CFBundleIdentifier"` | plist de app (bundle id) | Google | 🟡 |
| `filetype:plist intext:"CFBundleShortVersionString"` | Versão do app no plist | Google | 🟢 |
| `intitle:"index of" "Info.plist"` | Info.plist exposto | Google | 🟡 |

### Perfis de configuração e MDM

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:mobileconfig` | Perfis `.mobileconfig` em pasta aberta | Google | 🔴 |
| `filetype:mobileconfig intext:"PayloadContent"` | Perfil de configuração iOS | Google | 🔴 |
| `filetype:mobileconfig intext:"com.apple.vpn"` | Perfil de VPN para iOS | Google | 🔴 |
| `filetype:mobileconfig intext:"com.apple.wifi.managed"` | Perfil de Wi-Fi gerenciado | Google | 🔴 |

### OTA / distribuição

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:manifest.plist intext:"software-package"` | Manifesto OTA de instalação | Google | 🟡 |
| `filetype:plist intext:"kind" intext:"software"` | Item de instalação OTA | Google | 🟡 |
| `intitle:"index of" "embedded.mobileprovision"` | Provisioning profile exposto | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `intitle:"index of" ext:plist` | `intitle:"index of" ext:plist` | `"index of" ext:plist` |
| `intitle:"index of" ext:mobileconfig` | `intitle:"index of" ext:mobileconfig` | `"index of" mobileconfig` |
| `filetype:mobileconfig intext:"PayloadContent"` | `ext:mobileconfig "PayloadContent"` | `filetype:mobileconfig PayloadContent` |

> **Código-fonte:** provisioning profiles e plists commitados aparecem no GitHub Code Search (`filename:embedded.mobileprovision`). Segredos dentro deles → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo iOS em diretório aberto — 4 variações

```text
intitle:"index of" "entitlements.plist"
intitle:"index of" "Settings.bundle"
intitle:"index of" "PkgInfo"
intitle:"index of" "archived-expanded-entitlements.xcent"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `.mobileconfig` é o achado de maior risco: um perfil pode conter configuração de VPN, Wi-Fi (com PSK), proxy e certificados corporativos.
- `embedded.mobileprovision` traz o perfil de assinatura — revela team id, dispositivos e entitlements.
- `Info.plist` isolado costuma ser benigno (metadados), mas confirma bundle id e App Transport Security.
- Credenciais Wi-Fi dentro de um perfil cruzam com [14 · Wi-Fi, Redes & VPN](../14-wifi-redes-vpn/credenciais-wifi-expostas.md).

<div align="center">

[🏠 Hub](../../README.md) · [📱 Mobile](README.md) · [← APK & IPA](apk-e-ipa.md) · [Próximo: Strings & Segredos Mobile →](strings-e-segredos-mobile.md)

</div>
