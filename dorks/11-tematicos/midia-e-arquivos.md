<div align="center">

[🏠 Hub](../../README.md) · [🎨 Temáticos](README.md) · [← Vagas & Mercado](vagas-e-mercado.md)

# 🎬 Mídia & Arquivos

*Streams, players e arquivos de mídia expostos — áudio, vídeo e playlists em diretórios abertos.*

</div>

---

> [!CAUTION]
> Respeite direitos autorais. Streams privados expostos são achado de má configuração — reporte, não consuma. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Arquivos de mídia em diretórios abertos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" (ext:mp4 OR ext:mkv)` | Vídeos em diretórios abertos | Google | 🟡 |
| `intitle:"index of" ext:mp3` | Áudios em diretórios abertos | Google | 🟡 |
| `intitle:"index of" "movies" ext:mp4` | Pastas de filmes | Google | 🟡 |
| `intitle:"index of" ext:m3u8` | Playlists HLS | Google | 🟡 |
| `intitle:"index of" ext:srt` | Legendas | Google | 🟢 |

### Players e streams

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "webcam" ext:jpg` | Snapshots de câmera em pasta | Google | 🟡 |
| `inurl:/hls/ ext:m3u8` | Streams HLS | Google | 🟡 |
| `inurl:.m3u8 intext:"#EXTM3U"` | Manifests de stream | Google | 🟡 |
| `intitle:"VLC media player" inurl:/requests/` | Interface web do VLC | Google | 🟡 |
| `intitle:"Icecast Streaming Server"` | Servidor de streaming Icecast | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `intitle:"index of" ext:mp4` | `intitle:"index of" ext:mp4` | `title:"index of" mime:mp4` |
| `inurl:.m3u8 intext:"#EXTM3U"` | `instreamset:url:.m3u8 "#EXTM3U"` | `url:.m3u8 "#EXTM3U"` |
| `intitle:"Icecast Streaming Server"` | `intitle:"Icecast Streaming Server"` | `title:"Icecast Streaming Server"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo de mídia em diretório aberto por extensão — 13 variações

```text
intitle:"index of" ext:mp4
intitle:"index of" ext:mkv
intitle:"index of" ext:avi
intitle:"index of" ext:mov
intitle:"index of" ext:flac
intitle:"index of" ext:wav
intitle:"index of" ext:m3u
intitle:"index of" ext:webm
intitle:"index of" ext:ogg
intitle:"index of" ext:aac
intitle:"index of" ext:ts
intitle:"index of" ext:mpg
intitle:"index of" ext:ogv
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Muita mídia em diretório aberto é **conteúdo legítimo público** — avalie direitos autorais e contexto.
- Snapshots de webcam em pasta cruzam com [06 · Câmeras & DVR](../06-iot-ics-scada/cameras-e-dvr.md); não acesse feed privado.
- Streams HLS (`.m3u8`) expostos podem ser privados mal configurados — reporte, não consuma.

<div align="center">

[🏠 Hub](../../README.md) · [🎨 Temáticos](README.md) · [← Vagas & Mercado](vagas-e-mercado.md)

</div>
