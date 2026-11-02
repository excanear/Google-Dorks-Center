<div align="center">

[🏠 Hub](../../README.md) · [🗺 Mapas & GEOINT](README.md) · [← Rastreamento & Frota](rastreamento-e-frota.md)

# 📷 Mídia com Geolocalização

*Galerias e datasets com coordenadas — fotos geotagueadas em diretórios abertos e tabelas com latitude/longitude.*

</div>

---

> [!CAUTION]
> Coordenadas em fotos revelam onde (e quando) alguém esteve. Analisar exposição é recon; usar a localização de uma pessoa específica sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Galerias e uploads geotagueados

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "DCIM"` | Pasta de câmera/celular exposta | Google | 🔴 |
| `intitle:"index of" inurl:/uploads ext:jpg` | Uploads de imagem em pasta aberta | Google | 🟡 |
| `intitle:"index of" "geotagged"` | Diretório de mídia geotagueada | Google | 🟡 |
| `filetype:kml intext:"<PhotoOverlay>"` | KML com sobreposição de foto | Google | 🟡 |

### Datasets com coordenadas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:csv intext:"latitude" intext:"longitude"` | Dataset com lat/long | Google | 🟡 |
| `ext:json intext:"lat" intext:"lng" intext:"timestamp"` | Pontos com tempo (trajetória) | Google | 🔴 |
| `filetype:xlsx intext:"latitude" intext:"endereço"` | Planilha de locais (BR) | Google | 🟡 |
| `ext:csv intext:"lat" intext:"lon" intext:"device"` | Posições por dispositivo | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `intitle:"index of" "DCIM"` | `intitle:"index of" "DCIM"` | `"index of" DCIM` |
| `filetype:csv intext:"latitude" intext:"longitude"` | `ext:csv "latitude" "longitude"` | `filetype:csv latitude longitude` |
| `intitle:"index of" "geotagged"` | `intitle:"index of" "geotagged"` | `"index of" geotagged` |

> **Metadados de documento:** GPS dentro de PDF/Office (não em mídia solta) é recon de documento — fica em [07 · Recon de Organização](../07-recon-de-organizacao/README.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Pasta de mídia geotagueada em diretório aberto — 3 variações

```text
intitle:"index of" "camera_uploads"
intitle:"index of" "PhotoLibrary"
intitle:"index of" "gps-logs"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Os buscadores **não** indexam EXIF diretamente; o caminho prático é a **pasta aberta** (`DCIM`, `/uploads`) e depois ler o EXIF das imagens com ferramenta própria.
- Dataset com `lat/lng/timestamp` por `device` é efetivamente uma **trajetória** — trate como dado sensível.
- `DCIM` exposto costuma ser backup de celular mal configurado — alto risco de dados pessoais.
- Para posição em tempo real de veículos, veja [Rastreamento & Frota](rastreamento-e-frota.md); aqui o foco é mídia/arquivo **estático** geotagueado.

<div align="center">

[🏠 Hub](../../README.md) · [🗺 Mapas & GEOINT](README.md) · [← Rastreamento & Frota](rastreamento-e-frota.md)

</div>
