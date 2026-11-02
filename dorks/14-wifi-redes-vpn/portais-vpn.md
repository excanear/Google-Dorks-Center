<div align="center">

[🏠 Hub](../../README.md) · [📡 Wi-Fi, Redes & VPN](README.md) · [Próximo: Wi-Fi & Controladoras →](wifi-e-controladoras.md)

# 🔐 Portais VPN

*Portais SSL-VPN de Pulse/Ivanti, SonicWall, OpenVPN AS, Cisco AnyConnect, Check Point e Sophos — pontos de entrada remota, alvos históricos de CVE.*

</div>

---

> [!CAUTION]
> SSL-VPN é um dos vetores mais explorados em incidentes reais. Mapear o portal e a versão é recon; tentar login ou explorar CVE sem autorização é crime. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Pulse / Ivanti · SonicWall

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/dana-na/auth/url_default/welcome.cgi` | Pulse Connect Secure / Ivanti | Google | 🔴 |
| `intitle:"Pulse Connect Secure"` | Portal Pulse/Ivanti por título | Google | 🔴 |
| `intitle:"SonicWall" inurl:auth.html` | SSL-VPN SonicWall NetExtender | Google | 🔴 |
| `inurl:/sonicwall inurl:/auth` | SonicWall por caminho | Google | 🔴 |

### Cisco · Check Point · OpenVPN

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:+CSCOE+/logon.html` | Cisco ASA AnyConnect WebVPN | Google | 🔴 |
| `inurl:/CACHE/sdesktop/install/` | Cisco ASA Clientless resquício | Google | 🟡 |
| `inurl:/sslvpn/Login intext:"Check Point"` | Check Point Mobile Access | Google | 🔴 |
| `intitle:"OpenVPN Connect" inurl:/__session_start__` | OpenVPN Access Server | Google | 🔴 |
| `inurl:/openvpn/ intitle:"OpenVPN"` | OpenVPN AS por caminho | Google | 🟡 |

### Sophos · Barracuda · Array

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Sophos" inurl:userportal` | Sophos User Portal / SSL-VPN | Google | 🔴 |
| `intitle:"Barracuda" inurl:/cgi-mod/index.cgi` | Barracuda SSL-VPN | Google | 🔴 |
| `intitle:"Array Networks" inurl:/prx/000/http` | Array Networks AG SSL-VPN | Google | 🔴 |
| `intitle:"WatchGuard" inurl:/sslvpn` | WatchGuard Firebox SSL-VPN | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | FOFA |
|---|---|---|
| `intitle:"Pulse Connect Secure"` | `http.title:"Pulse Connect Secure"` | `title="Pulse Connect Secure"` |
| `inurl:/dana-na/auth/url_default/welcome.cgi` | `http.html:"/dana-na/"` | `body="/dana-na/"` |
| `inurl:+CSCOE+/logon.html` | `http.html:"/+CSCOE+/logon.html"` | `body="/+CSCOE+/logon.html"` |
| `intitle:"SonicWall" inurl:auth.html` | `http.title:"SonicWall"` | `title="SonicWall"` |

> **Infraestrutura é o canal mais confiável aqui:** portais VPN costumam ter `http.favicon.hash` característico. Fortinet/GlobalProtect/Citrix estão em [03 · Painéis de Login](../03-infraestrutura-web/paineis-de-login.md). Veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Portal SSL-VPN por caminho — 8 variações

```text
inurl:/my.policy
inurl:/vdesk/hangup.php3
inurl:/sslvpn/Login
inurl:/prx/000/http/
inurl:/cgi-mod/index.cgi
inurl:/workspace/index.html
inurl:/remote/logincheck
inurl:/sonicwall/auth.html
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Pulse/Ivanti (`dana-na`), Cisco ASA (`+CSCOE+`), SonicWall e Citrix acumulam CVEs críticos — a versão do portal costuma estar no HTML/JS. Cruze com [09 · Vulnerabilidades](../09-vulnerabilidades/README.md).
- O caminho `/CACHE/sdesktop/install/` é um resquício clássico de Cisco ASA — indica appliance, mesmo quando o logon está escondido.
- Fortinet/GlobalProtect/Citrix **não** se repetem aqui — vá à [03](../03-infraestrutura-web/paineis-de-login.md).
- Nunca valide um portal tentando autenticar; a existência e a versão já são o achado.

<div align="center">

[🏠 Hub](../../README.md) · [📡 Wi-Fi, Redes & VPN](README.md) · [Próximo: Wi-Fi & Controladoras →](wifi-e-controladoras.md)

</div>
