<div align="center">

[🏠 Hub](../../README.md) · [📡 Wi-Fi, Redes & VPN](README.md) · [← Portais VPN](portais-vpn.md) · [Próximo: Credenciais Wi-Fi →](credenciais-wifi-expostas.md)

# 📶 Wi-Fi & Controladoras

*Controladoras WLAN (Cisco WLC, Aruba, UniFi, Ruckus, Meraki), roteadores MikroTik e captive/hotspot portals expostos.*

</div>

---

> [!CAUTION]
> Controladora de Wi-Fi gerencia toda a rede sem fio; um captive portal pode listar convidados. Identificar é recon; autenticar ou alterar configuração sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Controladoras WLAN

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Cisco" intitle:"Wireless LAN Controller"` | Cisco WLC | Google | 🔴 |
| `intitle:"Aruba" inurl:/screens/wms/wms.login` | Aruba Mobility Controller | Google | 🔴 |
| `intitle:"RUCKUS" inurl:/admin/login.jsp` | Ruckus SmartZone/ZoneDirector | Google | 🔴 |
| `intitle:"Meraki" inurl:/manage/account/login` | Cisco Meraki Dashboard | Google | 🟡 |

### Roteadores e hotspots

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"RouterOS" inurl:/webfig` | MikroTik RouterOS WebFig | Google | 🔴 |
| `intitle:"mikrotik hotspot"` | Hotspot/captive portal MikroTik | Google | 🟡 |
| `intitle:"Tomato" intext:"Router"` | Firmware Tomato | Google | 🟡 |
| `inurl:/wds/login intitle:"EnGenius"` | Controladora EnGenius | Google | 🟡 |

### Captive portals

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/login intext:"captive portal"` | Captive portal genérico | Google | 🟢 |
| `intitle:"Guest WiFi" inurl:login` | Portal de Wi-Fi para convidados | Google | 🟡 |
| `inurl:/guest/s/ intitle:"UniFi"` | Portal de convidado UniFi | Google | 🟡 |
| `intext:"powered by CoovaChilli"` | Hotspot CoovaChilli | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | FOFA |
|---|---|---|
| `intitle:"UniFi Network"` | `http.title:"UniFi Network"` | `title="UniFi Network"` |
| `intitle:"RouterOS" inurl:/webfig` | `http.title:"RouterOS"` | `title="RouterOS"` |
| `intitle:"pfSense"` | `http.title:"pfSense"` | `title="pfSense"` |
| `intitle:"mikrotik hotspot"` | `http.html:"mikrotik hotspot"` | `body="mikrotik hotspot"` |

> **Infraestrutura:** MikroTik e UniFi têm portas e favicons característicos; Winbox (MikroTik) aparece no Shodan por `port:8291`. Veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Controladora/hotspot por caminho — 8 variações

```text
inurl:/screens/wms/wms.login.html
inurl:/wsg/login.jsp
inurl:/webfig/
inurl:/hotspot/login.html
inurl:/guest/s/default/
inurl:/manage/account/login
inurl:/admin/login.jsp
inurl:/cgi-bin/luci
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Controladoras (`WLC`, `Aruba`, `Ruckus`) expõem toda a infraestrutura sem fio — expô-las na internet é erro grave de segmentação.
- MikroTik `RouterOS`/`webfig` e `pfSense`/`OPNsense` são roteadores/firewalls — se o foco for o dispositivo físico, cruze com [06 · IoT & ICS/SCADA](../06-iot-ics-scada/README.md); aqui o foco é a **função de rede sem fio/borda**.
- Captive portal "Guest WiFi" às vezes vaza lista de dispositivos/convidados — respeite a fronteira de dados pessoais.
- Roteadores domésticos genéricos sem marca ficam melhor em [06](../06-iot-ics-scada/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [📡 Wi-Fi, Redes & VPN](README.md) · [← Portais VPN](portais-vpn.md) · [Próximo: Credenciais Wi-Fi →](credenciais-wifi-expostas.md)

</div>
