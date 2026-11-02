<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [← Roteadores & Rede](roteadores-e-rede.md) · [Próximo: ICS/SCADA & PLC →](ics-scada-plc.md)

# 🖨 Impressoras & NAS

*Impressoras/MFP e armazenamento em rede (NAS) com interface web exposta.*

</div>

---

> [!CAUTION]
> Impressoras vazam documentos e credenciais; NAS expõe arquivos inteiros. Mapear é passivo; acessar/baixar sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Impressoras e multifuncionais

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"HP LaserJet" inurl:/hp/device/` | Impressoras HP LaserJet | Google | 🟡 |
| `intitle:"Brother" inurl:/general/status.html` | Impressoras Brother | Google | 🟡 |
| `intitle:"Xerox" "WorkCentre"` | Multifuncionais Xerox | Google | 🟡 |
| `intitle:"RICOH" inurl:/web/guest/` | Impressoras Ricoh | Google | 🟡 |
| `inurl:hp/device/this.LCDispatcher` | Painel HP embutido | Google | 🟡 |
| `intitle:"Lexmark" inurl:/cgi-bin/` | Impressoras Lexmark | Google | 🟡 |

### NAS e armazenamento

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Synology" inurl:/webman/` | Synology DSM | Google | 🔴 |
| `intitle:"QNAP" inurl:/cgi-bin/` | QNAP QTS | Google | 🔴 |
| `intitle:"TrueNAS"` | TrueNAS/FreeNAS | Google | 🔴 |
| `intitle:"Western Digital" "My Cloud"` | WD My Cloud | Google | 🔴 |
| `intitle:"ReadyNAS"` | Netgear ReadyNAS | Google | 🟡 |
| `intitle:"openmediavault"` | OpenMediaVault | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Intenção | Shodan | Censys | FOFA |
|---|---|---|---|
| Synology | `http.title:"Synology"` | `web.endpoints.http.title:"Synology"` | `title="Synology"` |
| QNAP | `http.title:"QNAP"` | `web.endpoints.http.title:"QNAP"` | `title="QNAP"` |
| Impressora (IPP/9100) | `port:631 OR port:9100` | `host.services.port:631` | `port="9100"` |
| HP printer | `http.title:"HP LaserJet"` | `web.endpoints.http.title:"HP LaserJet"` | `title="HP LaserJet"` |
| WD My Cloud | `http.title:"My Cloud"` | `web.endpoints.http.title:"My Cloud"` | `title="My Cloud"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Impressora por título — 14 variações

```text
intitle:"HP LaserJet"
intitle:"Brother"
intitle:"Xerox WorkCentre"
intitle:"RICOH"
intitle:"Lexmark"
intitle:"KYOCERA"
intitle:"Canon iR"
intitle:"Epson"
intitle:"Sharp"
intitle:"Konica Minolta"
intitle:"OKI"
intitle:"Toshiba e-STUDIO"
intitle:"Samsung CLX"
intitle:"Dell Laser"
```

> **Padrão:** NAS por título — 9 variações

```text
intitle:"Synology"
intitle:"QNAP"
intitle:"My Cloud"
intitle:"Asustor"
intitle:"Terramaster"
intitle:"Buffalo LinkStation"
intitle:"Drobo"
intitle:"Zyxel NAS"
intitle:"WD My Book Live"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- NAS (Synology/QNAP/WD) sem auth são 🔴: dão acesso a arquivos; apenas confirme a exposição.
- Impressoras expõem catálogos de endereços e trabalhos de impressão — úteis para engenharia social, mas não interaja.
- Portas 9100 (RAW), 631 (IPP) e 515 (LPD) identificam impressoras em Shodan/FOFA.
- Interfaces de NAS que são "painel de hospedagem" genérico ficam em [03 · Interfaces de Gerenciamento](../03-infraestrutura-web/interfaces-de-gerenciamento.md).

<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [← Roteadores & Rede](roteadores-e-rede.md) · [Próximo: ICS/SCADA & PLC →](ics-scada-plc.md)

</div>
