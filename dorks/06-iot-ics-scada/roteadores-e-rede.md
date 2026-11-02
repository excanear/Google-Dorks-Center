<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [← Câmeras & DVR](cameras-e-dvr.md) · [Próximo: Impressoras & NAS →](impressoras-e-nas.md)

# 🌐 Roteadores & Rede

*Equipamentos de rede com interface de gestão exposta — roteadores, switches, firewalls e access points.*

</div>

---

> [!CAUTION]
> Interfaces de rede expostas são porta de entrada para a infraestrutura. Mapear é passivo; autenticar/configurar sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Roteadores domésticos e SOHO

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"RouterOS" "MikroTik"` | MikroTik RouterOS | Google | 🔴 |
| `intitle:"Tizi" OR intitle:"DD-WRT" inurl:/Info.live.htm` | DD-WRT status | Google | 🟡 |
| `intitle:"TP-LINK" inurl:/userRpm/` | Painel TP-Link | Google | 🟡 |
| `intitle:"ASUS Wireless Router"` | Roteadores ASUS | Google | 🟡 |
| `intitle:"Netgear" inurl:/start.htm` | Roteadores Netgear | Google | 🟡 |
| `intitle:"Fritz!Box"` | AVM Fritz!Box | Google | 🟡 |

### Equipamentos corporativos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Cisco" inurl:/level/15/exec/` | Cisco IOS web (nível 15) | Google | 🔴 |
| `inurl:/cgi-bin/luci intitle:"OpenWrt"` | OpenWrt LuCI | Google | 🟡 |
| `intitle:"pfSense" inurl:/index.php` | Firewall pfSense | Google | 🔴 |
| `intitle:"OPNsense"` | Firewall OPNsense | Google | 🔴 |
| `intitle:"UniFi Network"` | Controladora Ubiquiti UniFi | Google | 🟡 |
| `intitle:"Zyxel" inurl:/cgi-bin/` | Equipamentos Zyxel | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Intenção | Shodan | Censys | FOFA |
|---|---|---|---|
| MikroTik | `product:"MikroTik RouterOS"` | `host.services.software:(vendor="MikroTik")` | `app="MikroTik"` |
| pfSense | `http.title:"pfSense"` | `web.endpoints.http.title:"pfSense"` | `title="pfSense"` |
| UniFi | `http.title:"UniFi Network"` | `web.endpoints.http.title:"UniFi"` | `title="UniFi Network"` |
| Cisco IOS | `product:"Cisco IOS http config"` | `host.services.software:(vendor="Cisco")` | `app="Cisco"` |
| Fritz!Box | `http.title:"FRITZ!Box"` | `web.endpoints.http.title:"FRITZ!Box"` | `title="FRITZ!Box"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Equipamento de rede por título — 16 variações

```text
intitle:"RouterOS"
intitle:"TP-LINK"
intitle:"NETGEAR"
intitle:"pfSense"
intitle:"OpenWrt"
intitle:"DD-WRT"
intitle:"Zyxel"
intitle:"DrayTek Vigor"
intitle:"Huawei HG"
intitle:"D-Link"
intitle:"Linksys"
intitle:"Tenda"
intitle:"Technicolor"
intitle:"Sagemcom"
intitle:"Cambium Networks"
intitle:"Peplink"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- MikroTik, pfSense e Cisco web expostos são 🔴: alvos de exploração conhecidos; apenas confirme.
- Equipamentos de rede são melhor caçados em Shodan/Censys/FOFA por `product:`/banner.
- Páginas de simulador/manual de fabricantes geram ruído — combine com `site:` quando houver alvo.
- Login de dispositivo também em [03 · Painéis de Login](../03-infraestrutura-web/paineis-de-login.md).

<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [← Câmeras & DVR](cameras-e-dvr.md) · [Próximo: Impressoras & NAS →](impressoras-e-nas.md)

</div>
