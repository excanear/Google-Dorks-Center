<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [← ICS/SCADA & PLC](ics-scada-plc.md)

# 🔌 Outros Dispositivos

*VoIP, automação residencial, UPS, media servers e outros dispositivos conectados com interface exposta.*

</div>

---

> [!CAUTION]
> Mapear é passivo; acessar/configurar sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### VoIP e telefonia

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"FreePBX" inurl:/admin/config.php` | PBX FreePBX | Google | 🔴 |
| `intitle:"Grandstream Device Configuration"` | Telefones Grandstream | Google | 🟡 |
| `intitle:"Polycom" "SoundPoint"` | Telefones Polycom | Google | 🟡 |
| `intitle:"Asterisk" inurl:/static/config/` | PBX Asterisk | Google | 🟡 |

### Smart home, UPS e mídia

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Home Assistant"` | Hub Home Assistant | Google | 🟡 |
| `intitle:"openHAB"` | Automação openHAB | Google | 🟡 |
| `intitle:"APC" "Network Management Card"` | UPS APC | Google | 🟡 |
| `intitle:"Plex" inurl:/web/index.html` | Media server Plex | Google | 🟡 |
| `intitle:"Jellyfin"` | Media server Jellyfin | Google | 🟡 |
| `intitle:"PRTG Network Monitor"` | Monitoramento PRTG | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Intenção | Shodan | FOFA |
|---|---|---|
| FreePBX | `http.title:"FreePBX"` | `title="FreePBX"` |
| Home Assistant | `http.title:"Home Assistant"` | `title="Home Assistant"` |
| APC UPS | `http.title:"APC" product:"APC"` | `title="APC"` |
| Plex | `http.title:"Plex"` | `title="Plex"` |
| SIP/VoIP (5060) | `port:5060` | `port="5060" && protocol="sip"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Dispositivo diverso por título — 11 variações

```text
intitle:"FreePBX"
intitle:"Polycom"
intitle:"Plex"
intitle:"APC"
intitle:"Asterisk Management"
intitle:"3CX Phone System"
intitle:"Yealink"
intitle:"Shelly"
intitle:"Tasmota"
intitle:"ESPHome"
intitle:"Sonoff"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Media servers (Plex/Jellyfin) e smart home são frequentemente **expostos de propósito** pelo dono — avalie o contexto.
- PBX (FreePBX/Asterisk) expostos são 🔴: risco de fraude de tarifação (toll fraud); apenas confirme.
- VoIP por porta 5060 (SIP) é melhor achado em Shodan/FOFA.

<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [← ICS/SCADA & PLC](ics-scada-plc.md)

</div>
