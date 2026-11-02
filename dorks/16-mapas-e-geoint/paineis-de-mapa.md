<div align="center">

[🏠 Hub](../../README.md) · [🗺 Mapas & GEOINT](README.md) · [← Arquivos Geoespaciais](arquivos-geoespaciais.md) · [Próximo: Rastreamento & Frota →](rastreamento-e-frota.md)

# 🧭 Painéis de Mapa

*Servidores de mapa — GeoServer, ArcGIS Server, MapServer, QGIS Server e GeoNode — expondo camadas e, às vezes, dados internos.*

</div>

---

> [!CAUTION]
> Um servidor de mapa pode publicar camadas que não deveriam ser públicas. Listar serviços é recon; baixar ou usar camadas sensíveis sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### GeoServer / GeoNode

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/geoserver/web/` | Admin web do GeoServer | Google | 🔴 |
| `intitle:"GeoServer" inurl:/geoserver` | GeoServer por título | Google | 🟡 |
| `inurl:/geoserver/ows intext:"GetCapabilities"` | Capabilities WMS/WFS do GeoServer | Google | 🟡 |
| `intitle:"GeoNode"` | Plataforma GeoNode | Google | 🟡 |

### ArcGIS

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/arcgis/rest/services` | Diretório de serviços ArcGIS REST | Google | 🟡 |
| `intitle:"ArcGIS REST Services Directory"` | Services Directory por título | Google | 🟡 |
| `inurl:/arcgis/manager` | ArcGIS Server Manager (admin) | Google | 🔴 |
| `inurl:/rest/services inurl:MapServer` | MapService publicado | Google | 🟡 |

### MapServer / QGIS / OGC

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/cgi-bin/mapserv` | Endpoint MapServer | Google | 🟡 |
| `inurl:/qgisserver intext:"GetCapabilities"` | QGIS Server OGC | Google | 🟡 |
| `inurl:"request=GetCapabilities" intext:"WMS_Capabilities"` | Serviço WMS genérico (OGC) | Google | 🟡 |
| `intext:"mapbox.accessToken" intext:"pk."` | Token público Mapbox no frontend | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | FOFA |
|---|---|---|
| `inurl:/geoserver/web/` | `http.html:"/geoserver/web/"` | `body="/geoserver/web/"` |
| `intitle:"ArcGIS REST Services Directory"` | `http.title:"ArcGIS REST Services Directory"` | `title="ArcGIS REST Services Directory"` |
| `inurl:/cgi-bin/mapserv` | `http.html:"mapserv"` | `body="mapserv"` |
| `intitle:"GeoNode"` | `http.title:"GeoNode"` | `title="GeoNode"` |

> **Infraestrutura:** GeoServer e ArcGIS têm favicons e caminhos característicos; no FOFA, `app="GeoServer"`. Veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Servidor de mapa por caminho — 4 variações

```text
inurl:/qgisserver
inurl:/mapguide/
inurl:/gwc/service/
inurl:/geonetwork/srv
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `/geoserver/web/` e `/arcgis/manager` são **administrativos** — expô-los é grave. `GetCapabilities` lista todas as camadas publicadas de uma vez.
- A **chave pública** do Mapbox (`pk.`) é projetada para o frontend e não é segredo; a secreta (`sk.`) é da [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).
- Muitos servidores de mapa são **públicos por missão** (IDE/portais gov) — o achado é a camada interna/privada exposta.
- `WMS_Capabilities` indexado é um ótimo pivô: lê-se o catálogo inteiro sem autenticar.

<div align="center">

[🏠 Hub](../../README.md) · [🗺 Mapas & GEOINT](README.md) · [← Arquivos Geoespaciais](arquivos-geoespaciais.md) · [Próximo: Rastreamento & Frota →](rastreamento-e-frota.md)

</div>
