<div align="center">

[🏠 Hub](../../README.md)

# 🏛 Setores Regulados & Nichos

*Exposição de **sistemas e portais** por setor — saúde, educação, governo local/ONGs, imobiliário/automotivo e outros nichos. O foco é o sistema exposto, nunca varrer dados sensíveis.*

</div>

---

> [!CAUTION]
> Esta categoria identifica **sistemas e portais** de um setor expostos — não os dados que eles guardam. Dado de saúde é **categoria especial** sob a LGPD/GDPR: nada aqui serve para acessar prontuários, exames ou cadastros de pacientes. Ao encontrar um sistema exposto, **reporte ao responsável**; não acesse os dados. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🏥 Saúde & Médico](saude-e-medico.md) | DICOM/PACS, portais de clínica (⚠ dado de saúde) | 🔴 |
| 2 | [🎓 Educação & EAD](educacao-e-ead.md) | Moodle, Canvas, Blackboard, Chamilo | 🟡 |
| 3 | [🏛 Governo Local & ONGs](governo-local-e-ongs.md) | Portais de transparência, ERP municipal, CiviCRM | 🟡 |
| 4 | [🏠 Imobiliário & Automotivo](imobiliario-e-automotivo.md) | CRMs do setor, portais de imóveis/veículos | 🟡 |
| 5 | [🔆 Outros Nichos](outros-nichos.md) | Energia, agro, turismo/hospitalidade | 🟡 |

## 🧭 Como usar esta categoria

1. Identifique o **sistema** do setor (produto + versão) — pivô para CVEs em [09 · Vulnerabilidades](../09-vulnerabilidades/README.md).
2. Pare no nível do **portal/sistema**: a existência exposta é o achado a reportar.
3. Não prossiga para dados — sobretudo em saúde, onde isso é dado sensível sob regime especial.

## 🚧 Fronteira desta categoria

- **`*.gov.br` / `*.edu.br` brasileiros** → [10 · Brasil](../10-brasil/README.md). Aqui, o **sistema do setor** de forma geral (inclui internacional e software específico).
- **Dados pessoais em arquivo** (planilhas, dumps, prontuários) → [01](../01-exposicao-de-arquivos/README.md)/[02](../02-credenciais-e-segredos/README.md). Aqui, só o **portal/sistema**.
- **Dispositivos médicos físicos / IoT hospitalar** → [06 · IoT & ICS/SCADA](../06-iot-ics-scada/README.md). Aqui, o **software/portal** do setor.

## 🔗 Categorias relacionadas

- Sistemas BR (gov/edu) → [10 · Brasil](../10-brasil/README.md)
- Dispositivos médicos/IoT → [06 · IoT & ICS/SCADA](../06-iot-ics-scada/README.md)
- CVEs por produto → [09 · Vulnerabilidades](../09-vulnerabilidades/README.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
