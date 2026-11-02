<div align="center">

[🏠 Hub](../../README.md)

# 📡 Wi-Fi, Redes & VPN

*Conectividade e acesso remoto — portais SSL-VPN, controladoras Wi-Fi e captive portals, credenciais de rede sem fio expostas e sistemas de monitoramento de rede.*

</div>

---

> [!CAUTION]
> Portal de VPN e controladora de rede são pontos de entrada críticos. Identificar e reportar exposição é legítimo; tentar autenticar ou conectar sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🔐 Portais VPN](portais-vpn.md) | Pulse/Ivanti, SonicWall, OpenVPN AS, AnyConnect | 🔴 |
| 2 | [📶 Wi-Fi & Controladoras](wifi-e-controladoras.md) | WLC, Aruba, UniFi, MikroTik, captive portals | 🟡 |
| 3 | [🔑 Credenciais Wi-Fi Expostas](credenciais-wifi-expostas.md) | SSID+senha em config/planilha, `wpa_supplicant` | 🔴 |
| 4 | [📊 Monitoramento de Rede](monitoramento-de-rede.md) | LibreNMS, Observium, Icinga, Netdata, Checkmk | 🟡 |

## 🧭 Como usar esta categoria

1. **Portais VPN** identificam o fornecedor (Pulse, SonicWall, Cisco…) — pivô direto para CVEs em [09 · Vulnerabilidades](../09-vulnerabilidades/README.md); SSL-VPN é alvo histórico de exploração.
2. **Controladoras e captive portals** revelam a topologia sem fio e, às vezes, convidados/clientes.
3. **Monitoramento** expõe o mapa da rede (hosts, enlaces, tráfego) — ouro para recon de [07 · Recon de Organização](../07-recon-de-organizacao/README.md).

## 🚧 Fronteira desta categoria

- **Fortinet / GlobalProtect / Citrix Gateway** já estão em [03 · Painéis de Login](../03-infraestrutura-web/paineis-de-login.md) — aqui ficam os **demais** portais VPN, sem duplicar.
- **Roteadores, câmeras e equipamento IoT/ICS** → [06 · IoT & ICS/SCADA](../06-iot-ics-scada/README.md). Aqui o foco é **conectividade e acesso remoto**.
- **Senha em arquivo `.env`/config** → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md); aqui, só credenciais **de rede sem fio** (SSID/PSK).
- **Cacti / PRTG / Zabbix / Nagios** já aparecem em [03](../03-infraestrutura-web/paineis-de-login.md)/[06](../06-iot-ics-scada/README.md) — aqui ficam os **demais** sistemas de NMS.

## 🔗 Categorias relacionadas

- Painéis de login (Fortinet/Citrix) → [03 · Infra Web](../03-infraestrutura-web/paineis-de-login.md)
- Equipamento de rede/IoT → [06 · IoT & ICS/SCADA](../06-iot-ics-scada/README.md)
- CVEs de SSL-VPN → [09 · Vulnerabilidades](../09-vulnerabilidades/README.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
