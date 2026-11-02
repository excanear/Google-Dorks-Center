<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [Próximo: Roteadores & Rede →](roteadores-e-rede.md)

# 📷 Câmeras & DVR

*Câmeras IP, gravadores DVR/NVR e webcams expostos. Localizar é passivo; visualizar feed sem autorização viola privacidade e a lei.*

</div>

---

> [!CAUTION]
> Acessar o feed de uma câmera sem autorização é invasão de privacidade e pode ser crime (Lei 12.737/2012, CFAA). Apenas confirme a exposição e reporte ao responsável. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Interfaces de câmera (web)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Live View / - AXIS"` | Câmeras AXIS | Google | 🔴 |
| `intitle:"webcamXP 5"` | Software webcamXP | Google | 🔴 |
| `intitle:"Network Camera" inurl:/view/view.shtml` | Câmeras de rede genéricas | Google | 🔴 |
| `inurl:/view/index.shtml` | Visualização ao vivo genérica | Google | 🔴 |
| `intitle:"IP Camera" inurl:/web/` | Interface de câmera IP | Google | 🔴 |
| `intitle:"WEB SERVICE" "Hikvision"` | Câmeras Hikvision | Google | 🔴 |
| `intitle:"DVR" inurl:/login.rsp` | Login de DVR | Google | 🔴 |
| `inurl:/doc/page/login.asp "DVR"` | DVR por página de login | Google | 🔴 |
| `intitle:"NetworkCamera" "Panasonic"` | Câmeras Panasonic | Google | 🔴 |

### Protocolos de vídeo

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/view/viewer_index.shtml` | Viewer MJPG | Google | 🔴 |
| `intitle:"Live NetSnap Cam-Server feed"` | NetSnap | Google | 🔴 |
| `inurl:8080 intitle:"Webcam" "snapshot"` | Snapshot de webcam | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

> Câmeras são achadas melhor por buscadores de infraestrutura (banner + screenshot).

| Intenção | Shodan | Censys | FOFA | ZoomEye |
|---|---|---|---|---|
| Câmeras com screenshot | `has_screenshot:true screenshot.label:webcam` | — | `body="webcam"` | `app:"webcam"` |
| Hikvision | `product:"Hikvision IP Camera"` | `host.services.software:(vendor="Hikvision")` | `app="Hikvision"` | `app:"Hikvision"` |
| Dahua | `product:"Dahua"` | — | `app="Dahua"` | `app:"Dahua"` |
| RTSP (fluxo de vídeo) | `port:554 has_screenshot:true` | `host.services.port:554` | `protocol="rtsp"` | `port:554` |
| AXIS | `http.title:"Live View / - AXIS"` | `web.endpoints.http.title:"AXIS"` | `title="Live View / - AXIS"` | `app:"AXIS"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Interface de câmera por título — 18 variações

```text
intitle:"Network Camera"
intitle:"IP Camera"
intitle:"IPCam"
intitle:"Live View"
intitle:"NetworkCamera"
intitle:"GeoVision"
intitle:"webcam 7"
intitle:"i-Catcher Console"
intitle:"EvoCam"
intitle:"AXIS Video Server"
intitle:"Hikvision"
intitle:"Dahua"
intitle:"FOSCAM"
intitle:"Panasonic Network Camera"
intitle:"Vivotek"
intitle:"Mobotix"
intitle:"ACTi"
intitle:"Milesight Network Camera"
```

> **Padrão:** Endpoint de câmera por URL — 6 variações

```text
inurl:/view/view.shtml
inurl:/cgi-bin/guestimage.html
inurl:/control/userimage.html
inurl:/axis-cgi/mjpg/video.cgi
inurl:/webcapture.jpg
inurl:/snapshotjpeg
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Páginas de **demo/manual** de fabricantes geram ruído — confirme que é um dispositivo real.
- RTSP (porta 554) e os filtros `has_screenshot`/`screenshot.label` do Shodan são o caminho mais eficaz; interfaces web cobrem o resto.
- **Nunca** acesse o feed: o objetivo é confirmar exposição e notificar, não visualizar.
- Logins de DVR/câmera também aparecem em [03 · Painéis de Login](../03-infraestrutura-web/paineis-de-login.md); aqui o foco é o **dispositivo**.

<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [Próximo: Roteadores & Rede →](roteadores-e-rede.md)

</div>
