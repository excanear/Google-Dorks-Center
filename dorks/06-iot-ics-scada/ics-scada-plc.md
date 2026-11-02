<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [← Impressoras & NAS](impressoras-e-nas.md) · [Próximo: Outros Dispositivos →](outros-dispositivos.md)

# 🏭 ICS/SCADA & PLC

*Sistemas de controle industrial expostos — CLPs, HMIs e protocolos industriais. Zona de risco máximo.*

</div>

---

> [!CAUTION]
> **Zona vermelha.** Sistemas de controle industrial operam infraestrutura física (energia, água, indústria). **Qualquer** interação — até um pacote de protocolo — pode causar dano físico e é crime sem autorização expressa. Aqui **apenas se confirma a exposição** por consulta passiva ao índice de um buscador, e se reporta ao CERT/responsável. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### HMIs e interfaces web industriais

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Niagara Web Server"` | Tridium Niagara (BAS) | Google | 🔴 |
| `inurl:/Portal/Portal.mwsl` | HMI Siemens WinCC | Google | 🔴 |
| `intitle:"Simatic" "S7"` | Siemens SIMATIC S7 | Google | 🔴 |
| `intitle:"CIMPLICITY"` | GE CIMPLICITY SCADA | Google | 🔴 |
| `intitle:"PowerLogic" "ION"` | Schneider PowerLogic | Google | 🔴 |
| `intitle:"Modbus" inurl:/mbrtu` | Gateway Modbus | Google | 🔴 |
| `inurl:/scada/ intitle:"login"` | Portais SCADA genéricos | Google | 🔴 |

### Automação predial e energia

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"BACnet" inurl:/bacnet/` | Dispositivos BACnet | Google | 🔴 |
| `intitle:"Carel" "pCOWeb"` | Controladores Carel (HVAC) | Google | 🔴 |
| `intitle:"SolarEdge" inurl:/web/` | Inversores solares SolarEdge | Google | 🟡 |
| `intitle:"Fronius" "Solar.web"` | Inversores Fronius | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

> ICS é identificado por **porta de protocolo + banner** nos buscadores de infraestrutura — o caminho mais eficaz e o mais perigoso de usar mal.

| Protocolo/Sistema | Shodan | Censys | FOFA |
|---|---|---|---|
| Modbus (502) | `port:502` | `host.services.port:502` | `port="502" && protocol="modbus"` |
| Siemens S7 (102) | `port:102` | `host.services.port:102` | `port="102"` |
| BACnet (47808) | `port:47808` | `host.services.service_name="BACNET"` | `port="47808"` |
| DNP3 (20000) | `port:20000 product:DNP3` | `host.services.port:20000` | `port="20000"` |
| EtherNet/IP (44818) | `port:44818` | `host.services.port:44818` | `port="44818"` |
| Niagara Fox (1911) | `port:1911 product:"Niagara"` | `host.services.port:1911` | `app="Niagara"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Sistema industrial/HMI por título — 16 variações

```text
intitle:"Simatic"
intitle:"PowerLogic"
intitle:"pCOWeb"
intitle:"BACnet"
intitle:"Modbus"
intitle:"Tridium"
intitle:"WAGO"
intitle:"Moxa"
intitle:"Schneider Electric"
intitle:"Allen-Bradley"
intitle:"KEPServerEX"
intitle:"Ignition Gateway"
intitle:"Lantronix"
intitle:"Advantech WebAccess"
intitle:"Yokogawa"
intitle:"Honeywell"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Repito:** não envie nenhum pacote de protocolo industrial a um alvo não autorizado. Mesmo uma leitura Modbus é interação.
- A identificação é feita por **porta + banner** nos buscadores de infraestrutura; os dorks Google cobrem HMIs web.
- Muitos resultados são **honeypots** (Conpot etc.) — valioso para pesquisa, mas confirme antes de concluir exposição real.
- Encontrou ICS real exposto? Acione o **CERT** nacional/responsável — é questão de segurança pública.

<div align="center">

[🏠 Hub](../../README.md) · [📡 IoT & ICS/SCADA](README.md) · [← Impressoras & NAS](impressoras-e-nas.md) · [Próximo: Outros Dispositivos →](outros-dispositivos.md)

</div>
