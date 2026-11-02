<div align="center">

[🏠 Hub](../../README.md) · [🗺 Mapas & GEOINT](README.md) · [Próximo: Painéis de Mapa →](paineis-de-mapa.md)

# 📁 Arquivos Geoespaciais

*KML/KMZ, GPX, GeoJSON e Shapefile em diretórios abertos — territórios, rotas e ativos mapeados.*

</div>

---

> [!CAUTION]
> Trilhas GPX podem conter o deslocamento de uma pessoa; camadas podem revelar infraestrutura sensível. Confirmar exposição é recon; usar dados de localização de terceiros não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### KML / KMZ (Google Earth)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:kml` | Arquivos KML em pasta aberta | Google | 🟡 |
| `intitle:"index of" ext:kmz` | Arquivos KMZ compactados | Google | 🟡 |
| `filetype:kml intext:"<coordinates>"` | KML com coordenadas | Google | 🟡 |
| `filetype:kml intext:"Placemark"` | KML com pontos marcados | Google | 🟢 |

### GPX (trilhas GPS)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:gpx` | Trilhas GPX em pasta aberta | Google | 🔴 |
| `filetype:gpx intext:"<trkpt"` | GPX com pontos de trilha | Google | 🔴 |
| `filetype:gpx intext:"<wpt"` | GPX com waypoints | Google | 🟡 |

### GeoJSON / Shapefile / vetor

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:geojson intext:"FeatureCollection"` | Camadas GeoJSON | Google | 🟡 |
| `intitle:"index of" ext:shp` | Shapefiles em pasta aberta | Google | 🟡 |
| `intitle:"index of" ext:gdb` | Geodatabase (ESRI) | Google | 🟡 |
| `intitle:"index of" ext:dwg intext:"map"` | Plantas CAD georreferenciadas | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `intitle:"index of" ext:kml` | `intitle:"index of" ext:kml` | `title:"index of" mime:kml` |
| `intitle:"index of" ext:gpx` | `intitle:"index of" ext:gpx` | `title:"index of" mime:gpx` |
| `ext:geojson intext:"FeatureCollection"` | `ext:geojson "FeatureCollection"` | `mime:geojson "FeatureCollection"` |
| `intitle:"index of" ext:shp` | `intitle:"index of" ext:shp` | `title:"index of" mime:shp` |

> **Wayback/CDX:** camadas removidas às vezes sobrevivem no Wayback; buscar `*.kml`/`*.geojson` no CDX de um domínio recupera o que saiu do ar — veja o [manual de código e arquivos](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo geoespacial em diretório aberto por extensão — 2 variações

```text
intitle:"index of" ext:geojson
intitle:"index of" ext:topojson
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Muito KML/GeoJSON é **dado público aberto** (gov, pesquisa) — valioso para GEOINT, baixo risco. O cuidado é com camadas **internas** expostas por engano (perímetros, dutos, antenas).
- GPX com `<trkpt>` registra **movimento real** — se for de pessoa, é dado sensível; registre a exposição, não os dados.
- Shapefile vem em conjunto (`.shp/.shx/.dbf`); o `.dbf` carrega os atributos (às vezes nomes/endereços).
- Metadados de GPS em **documentos** (não em arquivo geoespacial) ficam em [07 · Recon de Organização](../07-recon-de-organizacao/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [🗺 Mapas & GEOINT](README.md) · [Próximo: Painéis de Mapa →](paineis-de-mapa.md)

</div>
