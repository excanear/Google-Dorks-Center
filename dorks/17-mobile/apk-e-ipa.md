<div align="center">

[🏠 Hub](../../README.md) · [📱 Mobile](README.md) · [Próximo: plist & Config iOS →](plist-e-config-ios.md)

# 📦 APK & IPA

*Binários de aplicativo (Android `.apk`/`.aab`, iOS `.ipa`) em diretórios abertos, repositórios de build e espelhos.*

</div>

---

> [!CAUTION]
> Analisar um app que você pode baixar legitimamente é prática comum de pesquisa; redistribuir binários proprietários ou usar segredos extraídos não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Binários em diretórios abertos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:apk` | APKs em pasta aberta | Google | 🟡 |
| `intitle:"index of" ext:ipa` | IPAs em pasta aberta | Google | 🟡 |
| `intitle:"index of" ext:aab` | Android App Bundles | Google | 🟡 |
| `intitle:"index of" "app-release.apk"` | Build de release Android | Google | 🟡 |
| `intitle:"index of" "app-debug.apk"` | Build de debug (mais verboso) | Google | 🔴 |

### Builds e distribuição interna

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/downloads ext:apk intext:"version"` | Downloads de APK versionado | Google | 🟡 |
| `intitle:"index of" "output-metadata.json"` | Metadados de build Gradle | Google | 🟡 |
| `inurl:/builds ext:ipa` | IPAs de build interno | Google | 🔴 |
| `intext:"itms-services://" intext:"manifest.plist"` | Distribuição OTA iOS (ad-hoc) | Google | 🟡 |
| `inurl:/dist ext:apk` | Pasta de distribuição com APK | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `intitle:"index of" ext:apk` | `intitle:"index of" ext:apk` | `title:"index of" mime:apk` |
| `intitle:"index of" ext:ipa` | `intitle:"index of" ext:ipa` | `title:"index of" mime:ipa` |
| `intitle:"index of" "app-release.apk"` | `intitle:"index of" "app-release.apk"` | `title:"index of" "app-release.apk"` |

> **Código-fonte:** APKs e metadados commitados aparecem no GitHub Code Search (`filename:output-metadata.json`) e no Wayback. Veja o [manual de código e arquivos](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Binário de app em diretório aberto por extensão — 2 variações

```text
intitle:"index of" ext:xapk
intitle:"index of" ext:ipk
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `app-debug.apk` é mais valioso que o release: costuma ter logging verboso, endpoints de homologação e flags de debug.
- `output-metadata.json` (Gradle) revela versão, applicationId e variantes — ótimo recon antes de baixar o binário.
- Distribuição OTA iOS (`itms-services://` + `manifest.plist`) indica entrega ad-hoc/enterprise — veja [plist & Config iOS](plist-e-config-ios.md).
- Muito APK indexado é de sites de pirataria; o interessante é o **build interno** de uma organização exposto por engano.

<div align="center">

[🏠 Hub](../../README.md) · [📱 Mobile](README.md) · [Próximo: plist & Config iOS →](plist-e-config-ios.md)

</div>
