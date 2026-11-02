<div align="center">

[🏠 Hub](../../README.md) · [🏛 Setores Regulados & Nichos](README.md) · [← Imobiliário & Automotivo](imobiliario-e-automotivo.md)

# 🔆 Outros Nichos

*Energia (monitoramento solar/usinas), agronegócio e turismo/hospitalidade — sistemas e portais setoriais expostos.*

</div>

---

> [!CAUTION]
> Sistemas setoriais podem controlar ativos físicos (usinas) ou guardar dados de hóspedes/produtores. Identificar o sistema é recon; operar ativos ou acessar dados sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Energia & monitoramento

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Solar-Log"` | Monitoramento fotovoltaico Solar-Log | Google | 🟡 |
| `intitle:"Sunny WebBox"` | Datalogger solar SMA | Google | 🔴 |
| `intitle:"photovoltaic" inurl:/portal` | Portal de usina fotovoltaica | Google | 🟡 |
| `intitle:"Fronius" inurl:/status` | Inversor solar Fronius | Google | 🟡 |
| `inurl:/energy intitle:"dashboard" intext:"kWh"` | Dashboard de energia | Google | 🟡 |

### Agro & turismo/hospitalidade

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" intext:"fazenda" intext:"talhao"` | Dados de gestão agrícola em pasta aberta | Google | 🟡 |
| `inurl:/agro intitle:"painel" inurl:/login` | Painel de gestão agro | Google | 🟡 |
| `inurl:/OPERA intitle:"OPERA" intext:"PMS"` | Oracle OPERA PMS (hotelaria) | Google | 🔴 |
| `intitle:"booking engine" inurl:/admin` | Motor de reservas de hotel | Google | 🟡 |
| `inurl:/pms intitle:"login" intext:"reservas"` | PMS de hospitalidade | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | FOFA |
|---|---|---|
| `intitle:"Solar-Log"` | `http.title:"Solar-Log"` | `title="Solar-Log"` |
| `intitle:"Sunny WebBox"` | `http.title:"Sunny WebBox"` | `title="Sunny WebBox"` |
| `intitle:"Fronius"` | `http.title:"Fronius"` | `title="Fronius"` |
| `inurl:/OPERA intitle:"OPERA"` | `http.html:"OPERA"` | `body="OPERA"` |

> **Infraestrutura:** dataloggers solares (`Sunny WebBox`, `Solar-Log`) muitas vezes controlam ativos — se houver controle físico, cruze com [06 · IoT & ICS/SCADA](../06-iot-ics-scada/README.md). Aqui priorizamos o **portal/sistema**.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Sistema de nicho (energia/agro/hotelaria) por título — 4 variações

```text
intitle:"Fronius"
intitle:"SolarEdge"
intitle:"Enphase Enlighten"
intitle:"OPERA PMS"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `Sunny WebBox`/`Solar-Log` já apareceram em incidentes de rede elétrica; se o sistema **controla** a usina, é ICS → trate com o cuidado de [06 · IoT & ICS/SCADA](../06-iot-ics-scada/README.md).
- OPERA PMS e motores de reserva guardam dados de hóspedes (inclusive pagamento) — pare no nível do sistema.
- Gestão agro exposta revela talhões, produção e, às vezes, localização de propriedades — dado de negócio sensível.
- Este arquivo é o "guarda-chuva" de nichos; nichos que crescerem podem virar subcategoria própria no futuro.

<div align="center">

[🏠 Hub](../../README.md) · [🏛 Setores Regulados & Nichos](README.md) · [← Imobiliário & Automotivo](imobiliario-e-automotivo.md)

</div>
