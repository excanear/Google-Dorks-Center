<div align="center">

[🏠 Hub](../../README.md) · [📡 Wi-Fi, Redes & VPN](README.md) · [← Credenciais Wi-Fi](credenciais-wifi-expostas.md)

# 📊 Monitoramento de Rede

*Sistemas de NMS (LibreNMS, Observium, Icinga, Netdata, Checkmk, Smokeping) expostos — o mapa vivo da rede: hosts, enlaces e tráfego.*

</div>

---

> [!CAUTION]
> Um NMS exposto revela a topologia interna inteira. Olhar o que está público é recon; autenticar ou extrair séries de dados sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Plataformas de NMS

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"LibreNMS"` | NMS LibreNMS | Google | 🟡 |
| `intitle:"Observium"` | NMS Observium | Google | 🟡 |
| `intitle:"Icinga" inurl:/icingaweb2` | Icinga Web 2 | Google | 🟡 |
| `intitle:"Checkmk" inurl:/check_mk` | Checkmk monitoring | Google | 🟡 |
| `intitle:"Netdata" inurl:/dashboard` | Dashboard Netdata em tempo real | Google | 🟡 |

### Gráficos e weathermaps

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/smokeping/smokeping.cgi` | Smokeping latency grapher | Google | 🟢 |
| `intitle:"Network Weathermap"` | Mapa de tráfego (Cacti Weathermap) | Google | 🟡 |
| `inurl:/cacti/graph_view.php` | Visão de gráficos do Cacti (dados) | Google | 🟡 |
| `intitle:"MRTG" intext:"Traffic Analysis"` | Gráficos MRTG de tráfego | Google | 🟢 |
| `intitle:"ntopng"` | Análise de fluxo ntopng | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | FOFA |
|---|---|---|
| `intitle:"LibreNMS"` | `http.title:"LibreNMS"` | `title="LibreNMS"` |
| `intitle:"Observium"` | `http.title:"Observium"` | `title="Observium"` |
| `intitle:"Netdata" inurl:/dashboard` | `http.title:"Netdata"` | `title="Netdata"` |
| `intitle:"ntopng"` | `http.title:"ntopng"` | `title="ntopng"` |

> **Infraestrutura:** o painel de NMS costuma estar em porta alta (`19999` para Netdata, por exemplo). Cacti/PRTG/Zabbix/Nagios de **login** estão em [03 · Painéis de Login](../03-infraestrutura-web/paineis-de-login.md). Veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Sistema de NMS por caminho — 8 variações

```text
inurl:/librenms/
inurl:/observium/
inurl:/icingaweb2/
inurl:/check_mk/
inurl:/smokeping/
inurl:/ntopng/
inurl:/weathermap/
inurl:/netdata/
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Netdata exposto (`:19999`) mostra métricas em tempo real **sem login** por padrão — revela hostnames, serviços e carga.
- `cacti/graph_view.php` e `Network Weathermap` entregam o **dado** (tráfego, enlaces), não só o login — por isso ficam aqui, enquanto a **tela de login** do Cacti está na [03](../03-infraestrutura-web/paineis-de-login.md).
- Smokeping/MRTG são, muitas vezes, públicos de propósito (NOC de provedor) — confirme o contexto.
- Um NMS é o melhor mapa de rede que existe para recon — cruze com [07 · Recon de Organização](../07-recon-de-organizacao/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [📡 Wi-Fi, Redes & VPN](README.md) · [← Credenciais Wi-Fi](credenciais-wifi-expostas.md)

</div>
